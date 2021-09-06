---
title: "MESH Environmental Wireless Sensor Network"
excerpt: "Low-cost node to periodically collect environmental data, wirelessly aggregate it through nearby nodes, and upload it to the internet<br/><img src='/images/MESH_Logo_v2.png' height='400' width='400'>"
collection: portfolio
---

In 2019, while taking a course in Wireless Sensor Networks (WSNs) at UMD, I was discussing limitations in conducting field research in ecology with David Klinges, who has just begun his PhD studies in that field. He described what sounded to me like a very antiquated process of collecting environmental data from the field, whereby researchers have to wire in to each individual sensor, which are often located deep in the rainforest and up in the trees, to collect any data off of them. This proves a hassle not only because it means the researchers need to return to their remote sites to collect data, but also because the researchers have no indication during the study as to the quality of the data or even whether the sensor is still on. 

This seemed like a perfect application of WSNs, and indeed many academic labs had developed and deployed environmental WSNs in the early 2000's. While this research provided a great starting point for designing my own network, I also decided to cater the additional long-term requirements of low cost and minimal required technical knowledge to operate. As far as I can tell, none of the academic solutions turned into commercially viable products for the lower-cost end of the market.

Starting with an [open-source sensor developed by James Mickley](https://github.com/mickley/EMU) that already included a WiFi chip, I designed and implemented a network in Lua using the NodeMCU framework. I iteratively modified the hardware, upgrading the microcontroller to the ESP32, which has more RAM, and adding a LoRa chip to extend the communication range. Natalie Greenlee and Robert Halvorsen designed a ruggedized case for the node, and I continued developing the software to robustly aggregate data and upload it to the internet via a WiFi access point. 

After developing an initial prototype, I deemed it was necessary to create a second iteration of the node to address fundamental limitations of component reliability and access to software libraries by completely revamping the hardware. For their final ENGS89/90 project, a team of Dartmouth engineering students, composed of Ted Northup, Max Lindemann, Ricardo Serrano-Smith, and Luc Kharey, conducted this initial redesign and simultaneously improved the case and sensor. They programmed the node in Arduino and focused on point-to-point communication, with the condition that afterwards I would be able to program it in C to more effectively design the entire network based on a simplified TCP/IP model.

<img src='/images/MESHThayerCase.png' height='400' width='400' caption='test'>

As of September 2021, I am designing and coding the full network for this second node iteration, as well as working with Shane Dennis and Robert Halvorsen to build a webserver and website to upload and display the data. Simultaneously, I am implementing higher-gain, directional LoRa antennas to simplify the connection to the internet and integrating a satellite transceiver from Swarm to provide a second means of accessing the internet.

The COVID-19 pandemic has delayed the Madagascar deployment, but I continue to test the network in the forests in the Maryland/D.C. area and am planning a full scale test for the winter of 2021/22. Eventually, we plan to expand the WSN into fields related to ecology, such as meteorology and climate science.

At this time, we are not making the design and code public to maximize our number of business options going forward. I'm still happy to talk in further detail about the network to anyone who reaches out. I'm always open to new ideas and directions for the network.


