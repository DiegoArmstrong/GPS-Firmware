# UBC Solar GPS Firmware - Brightside 

This project is designed to use GPS technology to provide precise positioning, velocity, time information, etc. that are essential for efficient navigation and data analysis during competition and testing. The firmware will be integrated with Sunlink, UBC Solar's telemetry system for analyzing vehicle data.

![GNSS_front](https://github.com/DiegoArmstrong/GPS-Firmware/assets/74511707/58fa7d6a-aa2b-4945-8e1a-1dd1c97b2ddd)
![GNSS_back](https://github.com/DiegoArmstrong/GPS-Firmware/assets/74511707/0d5142d2-1b39-4cae-b55a-1a5bbd6c8bcd)
![nucleo_gnss](https://github.com/DiegoArmstrong/GPS-Firmware/assets/74511707/89d7f227-803a-4e77-8573-d2530ffd0070)

#### _Notice_

_This repo will primarily serve as a how-to guide and technical overview for Brightside's GPS board firmware. For a more conceptual overlook of the GPS board, relevant documentation, and the troubleshooting that occurred along the way, click the link in the "About" section of this repo to access the google docs file that was updated throughout the progress of this project._

## Important Context

### GPS Technology

GPS, which stands for Global Positioning System, operates using a network of satellites known as the Global Navigation Satellite System (GNSS). GNSS receivers, work by receiving signals from multiple satellites in orbit around the Earth. Each satellite broadcasts its precise location and the time the signal was transmitted. The receiver uses the time it takes for the signals to reach it from different satellites to calculate the distance from each satellite. By combining this information from at least four satellites, the receiver can determine its own three-dimensional position (latitude, longitude, and altitude) through a process called trilateration. This enables accurate and real-time positioning, navigation, and timing information.

### NMEA Sentences

The GPS module used in Brightside V3 communicates using NMEA (National Marine Electronics Association) sentences. These ASCII-based sentences provide internationally standardized data formats for GNSS receivers. Our firmware parses NMEA sentences to extract essential information, such as latitude, longitude, and velocity. By decoding these sentences, we can transform raw GPS data into meaningful information for our team.

### I2C Communication

To interface with the GPS module, we utilize the Inter-Integrated Circuit (I2C) protocol. I2C is a popular communication interface for embedded systems, allowing efficient and reliable data exchange between the microcontroller and peripheral devices. Our firmware implements I2C communication to configure the GPS module and retrieve GPS data efficiently.

## Getting Started

### Prerequisites

#### Hardware

* MAX-M10S GNSS receiver by Sparkfun
* L1 or L2 GPS antenna (preferably L1 as this is the North-American Standard)
* STM32 Microcontroller

#### Software

* STM32 Cube IDE
