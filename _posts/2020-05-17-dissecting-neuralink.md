---
layout: post
title:  "A Walkthrough of Neuralink's paper"
date:   2020-05-17 00:00:00 -0500
categories: tech
---

I want to be able to feel my extra virtual limb proprioceptively as I flex it in the virtual space, say inside the screen of the laptop. I can hold on to the icons of files, folders, hyperlinks, buttons, and I can feel their tactile structure. I can select them by squeezing them. One day I want to be able to do this.

There is so much dexterity, to the point of elegance, in human's ability to control and coordinate muscle movement. Imagine a chef's hands. Imagine a pianist's fingers. Imagine a dancer's arms, legs and torso. But all we have in direct control is our body, our own locomotion, while machines can manipulate atoms and bits alike in all dimensions. A higher level of human-machine symbiosis will bring elegance into the connotation of the word *robot*, something that has hitherto been depicted in sci-fi films.

To achieve this we need to push our human-machine symbiosis to a much higher level. Considering the bi-directionality of the human-machine bridge (M->H and H->M):

- M->H enjoys the auditory and visual bandwidth of human. Consumer-grade machines are largely limited to these 2 modalities for communication with human.
  - The bandwidth of information transmission of the human retina is estimated to be 10 Mb/s (UPenn School of Medicine).
  - The bandwidth of the human auditory system is roughly estimated to be 800 Kb/s (*Principles of Neural Coding*).


- H->M bandwidth is utterly terrible.
  - Typing: 41 wpm at 50th percentile, 100 wpm at 95th percentile. Average word length is 4.7 characters. Using ascii encoding, we have 25.7 b/s at 50th percentile and 62.6 b/s at 95th percentile. In comparison, a skilled morse code operator can type in 21 b/s, and a modem built by Bell Lab in 1959 has a data rate of 110 b/s.
  - Voice: chatbots are still limited by vocabulary size and contextual information. Very few people would agree that voice is an established way of human's communicating with machines.

Think about this: machines can communicate to one another faster than our communication with them 60 years ago. Not to mention on-chip bandwidth — DDR4 has ~20 GB/s within a modern SoC. That is a billion times faster than our ability to communicate with them.

The focus on human's outbound bandwidth leads to Neuralink. Here I attempt to walk through the [paper](https://www.biorxiv.org/content/10.1101/703801v1.full.pdf) published by the Neuralink team in July 2019 in order to grasp where we are now in this quest. The paper mentioned on page 10 that *"we designed the Neuralink ASIC to be capable of electrical stimulation on every channel, although we have not demonstrated these capabilities here."* So I will focus on achieving the increase in outbound bandwidth only.

***

The overarching goal here is to transmit spiking information at high bandwidth out from the human brain without tethering human to any stationary equipment.

Neuralink achieves the 3 following things:
1. An array of flexible electrode threads.
2. A neurosurgical robot.
3. An ASIC for amplification and A/D conversion.

Known constraints in brain-machine interface:
- At surgery: complexity / level of invasive-ness (risk), precision, speed.
- After surgery: biocompatibility, safety, longevity.

### 1. An array of flexible electrode threads

Dimensions:
- 32 electrodes/thread x 96 threads/array = 3072 electrodes/array.
- thread thickness ~5 um, including up to 3 layers of insulation and 2 layers of conductor.
- thread length ~20 mm (20,000 um).

Most BMI we use now is based on arrays of stiff needles made of metal, where one needle is one electrode. Its inability to stretch and bend hurts its biocompatibility and longevity. Above all, the mere image of sticking an array of needles into the brain would dissuade most healthy people.

An alternative approach is to use multi-electrode polymer probes that are thin and flexible. Furthermore, each thread could be inserted into the brain individually, as opposed to the rigid form factor of the metal needle array. Its drawback: not stiff enough to penetrate meninges and insert into the brain tissue. The insertion process, via stiffener and injection, has been slow. At surgery it's also crucial to not penetrate surface vasculature of the brain, because breaking the blood-brain barrier triggers inflammatory response. This naturally calls for a surgery robot, or more generally a production line to allow for high precision and high throughput thread insertion. I will cover Neuralink's neurosurgical robot in the next section.

<div align="center">
<img src="/assets/neuralink_1.png"/>
</div>
The above photos show 2 of the 20+ different thread-electrode configurations the Nueralink team experimented with. Photo A shows the "linear edge" probes, while photo B shows the "tree" probes. The suction cup-like endpoints are the gold electrodes. The probe is a long polyimide thread enclosing a thin-film gold trace serving as wire. On the left side of the photos you can see loops at the end of the thread. Those loops (16x50 um^2 each) are for needle threading by the surgical robot. The right side of the threads are connected to the sensor ASIC.

<div align="center">
<img src="/assets/neuralink_2.png"/>
</div>
Photo C zooms in on the electrodes. They are quite small, meaning their impedance could be huge. To increase its charge-carrying capacity, the surface of the electrode undergoes surface modification with electrically conductive polymer. PEDOT:PSS promises lower impedance but its biocompatibility is less well established.

### 2. A neurosurgical robot

Performance:
- ~6 threads (192 electrodes combined) inserted per minute, or ~29.6 electrodes per minute
- 87.1 ± 12.6 % (mean ± s.d.) insertion success rate over 19 surgeries. <== unless Neuralink achieves ~100% success rate, average healthy human won't consider trying this.
- Total insertion time averaged ~45 minutes.

<div align="center">
<img src="/assets/neuralink_3.png"/>
</div>

The above photo shows the part of the neurosurgical robot that carries the needle that carries the threads and goes into the brain.
- part C is the Needle Pincher Cartridge (NPC). NPC is replaceable mid-surgery under 10 minutes.
- part A is the needle of diameter 24 um. During the surgery, the robot moves the NPC to pick up the thread's loop with the needle, moves to the designated brain region, stick the thread into the brain at preset depth, and retract the needle with acceleration up to 30,000 mm s^-2.
- part B is the pincher, driven both axially and rotationally. It serves as the thread support and guide for the needle.

<div align="center">
<img src="/assets/neuralink_4.png"/>
</div>

The above photo shows the rest of the neurosurgical robot.
- part F is a camera with a wide angle view over the surgical field.
- part G are stereoscopic cameras. Together with depth of field calculation by software, the robot can locate precisely the cortical surface for individual thread insertion.
- part A is the NPC.
- part B is a low-force contact sensor.
- part C are lighting modules of different wavelengths (405nm, 525nm, 650nm, or white light). Each wavelength serves a different purpose: 405nm excites the fluorescence from the polyimide thread; 650nm helps with vision-based robot control; 525nm helps with positioning on the cortical surface.
- part D is the motor that drives the NPC.
- part E is a camera that focuses on the needle during insertion.

Additional software helps with optimal routing of NPC's trips between threads and their insertion locations to minimize tangling and strain on the threads.

<div align="center">
<img src="/assets/neuralink_5.png"/>
</div>

The photos above shows how NPC approaches the agarose brain tissue proxy (bottom of the photos), touches down on the tissue surface, penetrates the tissue and advances the needle to the desired depth, retracts and leaves the thread behind in the tissue.

### 3. An ASIC for amplification and A/D conversion

Routing all 96 threads of an array out of the skull without any signal processing would render those signals useless, given the SNR of the signal. Cable spec and connector spec would be prohibitive.

Which means, we need to amplify and filter the signals, digitize the signals and stream them out of the skull.

<div align="center">
<img src="/assets/neuralink_6.png"/>
</div>

Neuralink built an ASIC consists of:
- 256 individually tunable amplifiers (each one dedicated to an electrode; Neuralink calls the amplifiers "analog pixels")
- ADC sampling at 19.3kHz with 10-bit resolution.
- serializer circuit

The entire recording platform PCB consists of:
- 12 ASICS (12 x 256 = 3072 amplifiers to account for all the electrodes)
- an FPGA
- real-time temperature, accelerometer, and magnetometer sensors
- USB-C connector
- the entire system is packaged in titanium case and coated in parylene-c for protection.

The gain and filter parameters of the amplifiers can be tuned programmatically to cancel out process variations and electrophysiological environment idiosyncrasies.

Each amplifier consumes ~5.2 uW, and every ASIC consumes ~6 mW.

<div align="center">
<img src="/assets/neuralink_7.png"/>
</div>

As the above shows, 2 system specs were implemented: System A and System B. System B maximizes electrode/channel density. System A has less electrodes/channels, but System B can be manufactured 5 times faster than System A and with better yield.

According to Neuralink, it is conceivable to plug a ethernet base station into the USB-C connector, allowing for real-time high-bandwidth neural data streaming.

### Result and discussion

<div align="center">
<img src="/assets/neuralink_8.png"/>
</div>

Both System A and System B were tested in male Long-Evans rats.

<div align="center">
<img src="/assets/neuralink_9.png"/>
</div>

A threshold of >0.35 Hz was set to quantify the number of electrodes that recorded spiking units. No spike-sorting was performed. The above chart was from System A, where:
- 40 out of 44 attempted insertions were successful (90% rate)
- 1020 electrodes out of 1280 electrodes were recorded simultaenously.
- the spiking yields was 53.4% of channels, where many spikes appear on multiple neighboring channels (like a signpost passing through a series of train windows)

Both spiking activity and local field potential were recorded. Across 19 surgeries, the spiking yields were 59.10 ± 5.74 % (mean ± s.e.m.), and maximum spiking yield of 85.5 %.

Neuralink explained that this system serves as a research platform, so wired connection was used for maximizing data streaming. For human clinical use, the device will feature:
- fully implantable with hermetic packaging
- on-board signal compression
- data and power telemetry

<div align="center">
<img src="/assets/neuralink_10.png"/>
</div>

The above chart shows neural activity recorded across multiple brain regions and cortical layers and plotted as rasters of spikes.

Finally, Neuralink stated:
> It is plausible to imagine that a patient with spinal cord injury could dexterously control a digital mouse and keyboard. When combined with rapidly improving spinal stimulation techniques, in the future this approach could conceivably restore motor function. High-bandwidth neural interfaces should enable a variety of novel therapeutic possibilities.
