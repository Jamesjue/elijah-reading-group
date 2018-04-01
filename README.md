# Overview Paper

#### Edge Computing: Vision and Challenges
  * Benefits of edge computing: latency, b/w, energy, data safety and privacy
  * Challenges: programmability, naming, data abstraction, service management, security and privacy, optimization metrics

#### A Survey of Fog Computing: Concepts, Applications and Issues
  * Fog computing benefits: mobility support, geo-distribution, location-awareness, and low latency
  * Applications: 
     * AR and real-time video analytics
     * content delivery and caching
     * mobile big data analytics
  * Issues: 
     * fog networking with heterogeneous devices
     * QoS(connectivity, reliability, capacity, delay)
     * programmability
     * computation offloading (dynamic nodes, dynamic wireless network, dynamic resources in the fog)
     * accouting and monitoring
     * provisioning and management
     * security and privacy

#### A Brief History of Cloud Offload: A Personal Journey from Odyssey Through Cyber Foraging to Cloudlets

# Applications

#### The Design and Implementation of a Wireless Video Surveillance System (Vigil) (Mobicom)*
  * Divide processing between edge and the cloud
  * Key frame selection among a cluster of cameras(Early discard)
  * Content-aware traffic scheduling: new metric of ops(object per second)
  * Hybrid surveillance-access network: use edge nodes as access points to counter-costs

#### Glimpse: Continuous, Real-Time Object Recognition on Mobile Devices (SenSys)
  * Key frame detection, called **Trigger frame** in the work
  * Active Cache: use tracking on the mobile device and oject detection on a backend server to achieve real-time object recognition 

#### Rhema: A Real-Time In-Situ Intelligent Interface to Help People with Public Speaking (IUI)
  * Use Google Glass to detect volume and speaking rates in public speaking to provide feedback in real-time
  * Find users more pleased with sparse delivery of recommendation of words than continuous streams of information presented with bars and plots.
  * Use a computational offload approach as well. Audio is transmitted and processed on a backend server.

#### MarkIt: Privacy Markers for Protecting Visual Secrets (Ubicomp)
  * Remove sensitive information from camera feeds with user-drawn and gesture-based region
  
#### FlashBack: Immersive Virtual Reality on Mobile Devices via Rendering Memoization (Mobisys)
  * Doesn't use computational offload
  * HMD VR that eschews all real-time scene rendering
  * Aggresively precomputes and caches all possible images

#### Personalized, Wearable Control of a Head-mounted Display for Users with Upper Body Motor Impairments (CHI)

#### Designing Conversation Cues on a Head-Worn Display to Support Persons with Aphasia (CHI)
  * Investigated how to use wearables to provide unobtrusive, always-available, and glanceable vocabulary support for people with aphasia 

#### A google glass app to help the blind in small talk (ASSETS)
  * Used Google glass and computational offload to identify # of people, age, and gender distribution to help the visually impaired do small talk.

#### Sensor-assisted face recognition system on smart glass via multi-view sparse representation classification (IPSN)
  * On-device face recognition using both the camera and IMUs

# Mobile Hardware and Software

#### Draining our glass: an energy and heat characterization of Google Glass (APsys)

#### RedEye: analog ConvNet image sensor architecture for continuous mobile vision (ISCA)
  * Analog convolutional image sensor that performs layers of a convolutional neural network in the analog domain before quantization

#### ZOE: A Cloud-less Dialog-enabled Continuous Sensing Wearable Exploiting Heterogeneous Computation (MobiSys)
  * A custom-built wearable device that supports deep sensor inferences on continuously sensed data
  * A speech dialog system to interface with user
  * Without cloud or smartphone support
  * Heterogeneous platform to realize a three-tier low-power processor hierarchy

#### DeepSense: A GPU-based Deep Convolutional Neural Network Framework on Commodity Mobile Devices (WearSys)

#### DeepMon: Mobile GPU-based Deep Learning Framework for Continuous Vision Applications (MobiSys)

#### Starfish: Efficient Concurrency Support for Computer Vision Applications (MobiSys)

# Edge Computing Platform
#### ParaDrop: Enabling Lightweight Multi-tenancy at the Network’s Extreme Edge (SEC)

# Computation and Storage Offload
## Computation Offload Platform
#### Maui

#### Clone Cloud

#### Comet

#### MOCHA

## Storage Offload
#### WearDrive: Fast and Energy-Efficient Storage for Wearables (ATC)

## Wireless
#### Application-aware traffic scheduling for workload offloading in mobile clouds (INFOCOMM)

#### ACACIA: Context-aware Edge Computing for Continuous Interactive Applications over Mobile Networks (CoNext)
