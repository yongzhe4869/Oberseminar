# Multi-access edge computing(MEC)
Multi-access edge computing is a development of Mobile edge computing, and provided a new solution to converge IT services and telecommunication at the edge of network.
However, diffierent with Mobile edge computing, Multi-access edge computing can creat cloud platform nearby Base station and get closer to end devices.
Hence, the main advantage of MEC is ultra-low latency which meets the requirement of 5G and becomes an essential technology for next generation communication.
## Application
* Internet of Thing(IoT) and Big Data   
MEC provides more cloud platform nearby end devices which can save more data, and low latency make signal transmission of IoT easier and more efficient.
* Smart City and Industry 4.0   
Smart City include several services such as energy saving, Video analyze and monitoring, traffic control. These Services require a huge amount of data and MEC can storge data.
* Autonomous Car   
According to MEC server nearby each BS vehicle can adjust its moving angle and receive traffic congestion information.
## MEC enabling Technology  
* Software Deﬁned Network(SDN)   
SDN advocates replacing standardized network protocols with software applications. And SDN also provides possibility to program network which faciliates connections between MEC service. 
* Network Function Virtualization(NFV)  
NEV advocates replacing hardware elements using software running on COTS computers. SDN structure can be insert into NFV structure, most MEC components can regard as Virtualized Network Function(VNF). But NFV cannot provide MEC orchestration part and CFS portal, Device App, Use App LCM proxy.  
* Network slicing  
Network slicing can divided one network into different instances. By different slices MEC can improve more services and capacity. And the combination of SDN and NFV is necessary for network slicing service.
## challenges
*  UE Mobility  
It is difficult to ensure continous connection between MEC server and high speed devices. Consideration of multi-path in MEC server is also a big challenge.
* Security and Privacy  
Because additional MEC cloud platform locate beside BS it is easier to attact and reveal personal information. 
## MEC Structure   
![](https://github.com/yongzhe4869/Oberseminar/blob/main/Figures/MEC.PNG)    
Three parts: MEC Host, MEC Platform Manager and MEC Orchestrator.    
Data plane is located in MEC host, it is responsible for allocating, maintaining, and releasing virtual resources of the “virtualization infrastructure”. MEC APPs will run in this MEC host and ME Platform will provide some local services. The network-related APIs are exposed by MEC service to MEC Apps through reference point Mp1. The MEC service include at least three types:
* Radio Network conditions
* Location information (for example, location of a User Equipment(UE))
* Bandwidth Manager- The Bandwidth Manager service
MEC Platform manager performs same functions or a little more then the VNFM in NFV, It includes the following functions:  
* MEC Apps’ Life-cycle management: instantiating, maintaining and tearing down MEC Apps on VMs
* Element Management: FCAPS ( Fault, Configuration, Accounting, Performance, Security) management for the MEC platform
* managing the application rules, traffic rules, DNS configuration  
There should be a layer above MEC platform manager that can coordinate between different MEC platform managers. That is where MEC orchestrator comes into the picture and this effectively completes our ETSI architecture. It has following functions:   
* Lifecycle management of MEC Apps ( Compare this with MEC Platform manager, which can do a similar function). The Orchestrator achieves this function by talking to the application through the MEC platform manager.
* on-boarding of application packages, including checking the integrity and authenticity of the packages.
* Last but not the least, selecting appropriate MEC host(s) for application instantiation based on constraints, such as latency, available resources, and available services  
literatur: [here](https://telcocloudbridge.com/blog/beginners-guide-to-mec-architecture-multi-access-edge-computing/)
