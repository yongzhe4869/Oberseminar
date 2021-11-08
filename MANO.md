## NFV structure
If we want to research MEC MANO framework, we need know NFV structure first. The following figure shows the whole NFV structure defined by ESTI. It is divided into 4 parts and each part have its subclasses:
* VNF (Virtualized Network Function) is basic block in NFV architecture and can be inserted MEC function.
* EM (Element Management) is responsible for the functional management of VNF i.e. FCAPS ( Fault, Configuration, Accounting, Performance and Security Management). One EMS can manage one VNF or multi-VNF.
* VNF Manager (VNFM) manages one VFN or multi-VNF in virtual part, it does the life cycle management of VNF instances. Life cycle management means setting up/ maintaining and tearing down VNFs.
* NFVI (Network Functions Virtualization Infrastructure)
  * physical part: Compute, Memory and Networking Resources
  * virtual part: Compute, Memory and Networking Resources
  * Virtualization Layer(Hypervisor) is responsible for abstracting physical resources into virtual resources and can be virtualized using SDN layer.  
* VIM (Virtualized Infrastructure Manager)  is responsible for controlling and managing the NFVI elements. It is also responsible for collection of performance measurements and events.
* NFV Orchestrator(NFVO) is also responsible for global resource management of NFVI resources. It can connect to VNF indirectly through VIM and VNFM.  
* OSS/BSS(Operation Support System/Business Support System)
    * OSS deals with network management, fault management, configuration management and service management. 
    * BSS deals with customer management, product management and order management etc.
    * It can be integrated with NFV MANO.   
![](https://github.com/yongzhe4869/Oberseminar/blob/main/Figures/NFV.PNG)  

## NFV Orchestration framework
Nowadays there are many open sourse NFV Orchestration frameworks supported by different platform. Our work is to find gap between different MANO frameworks and design a solution to integrate two different framework together. One framework OPNFV is supported by my supervisor and another MANO is Open sourse MANO.
#### OPNFV 
OPNFV is an open source project hosted by the Linux Foundation and establishes NFV platform. OPNFV focuses on building NFVI and VIM by integrating components from upstream projects such as OpenDaylight, OVN, OpenStack, Kubernetes, Ceph Storage, KVM, Open vSwitch, Linux, DPDK and FD.io. The main basic language is python.
#### Open sourse MANO(OSM)
OSM is an ESTI hosted open sourse project. It focuses on almost all parts of NFV and different part is supportrd by different drivers. SDN controller is possible to be used in NFV structure and basic language is python.
* resource orchestrator (Telefonica OpenMANO)
*  VNF conﬁguration component (Canonical Juju)
*  network service orchestrator (RIFT.io), GUI (RIFT.io)
*  virtualized infrastructure based on Intel architecture
*  virtual infrastructure manager (OpenVIM and Openstack) 
*  ﬁnally service VNFs (Metaswitch and 6wind). 
