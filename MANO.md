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

### MEC with NFV 
The VNFM does the life cycle management of VNFs ( creation, deletion, maintenance)Now that MEC functions are converted into VNFs, we would naturally need corresponding VNFMs. This is done by two VNFMs as following.
* VNFM to manage life cycle of MEC Apps. 
* VNFM to mange life cycle of MEC Platfrom 
* MEC platform Element Management and MEC App rules & requirements management??? becomes a VNF labeled
* MEC App life cycle management??? is mapped to VNFM 
* MEC orchestration is the most important component that is missing in NFV
![](https://github.com/yongzhe4869/Oberseminar/blob/main/Figures/inter.PNG)

## NFV Orchestration framework
Nowadays there are many open sourse NFV Orchestration frameworks supported by different platform. Our work is to find gap between different MANO frameworks and design a solution to integrate two different framework together. One framework OPNFV is supported by my supervisor and another MANO is Open sourse MANO.
#### OPNFV 
OPNFV is an open source project hosted by the Linux Foundation and establishes NFV platform. OPNFV focuses on building NFVI and VIM by integrating components from upstream projects such as OpenDaylight, OVN, OpenStack, Kubernetes, Ceph Storage, KVM, Open vSwitch, Linux, DPDK and FD.io. The main basic language is python.
#### Open sourse MANO(OSM)
OSM is an ESTI hosted open sourse project. It focuses on almost all parts of NFV and different part is supportrd by different drivers. SDN controller is possible to be used in NFV structure and basic language is python. OSM leverages OpenMANO for Resource Orchestration(RO), and Juju for VNF configuration and management, but OSM also introduces a component for Service Orchestration(SO), provided by Rift.io Riftware which is beyond the ETSI NFV current scope.
* resource orchestrator (Telefonica OpenMANO)
*  VNF con???guration component (Canonical Juju)
*  network service orchestrator (RIFT.io), GUI (RIFT.io)
*  virtualized infrastructure based on Intel architecture
*  virtual infrastructure manager (OpenVIM and Openstack) 
*  ???nally service VNFs (Metaswitch and 6wind).   
#### Open Baton
Open Baton is an opensource project led by Fraunhofer Focus and TU Berlin. It is now being used by a few European projects and is available under GitHub and apache 2.0 license. Open Baton is also based on ETSI NFV phase 1 reference architectural framework and MANO specifications. 
* It is not aligned yet with the IFA interface specifications. 
* It provides an NFVO building block, a Generic VNFM, a component for EMS, a dashboard, supports multiple OpenStack VIM and provides a plug-in mechanism for other VIM. 
* It also supports specific VNFM. 
* It is implemented in java with the spring.io framework which supports VNF Package defined with json to include the VNF descriptors, scripts and metadata, and a link to the image   
#### Cloudify
Cloudify is another open source framework supported by Gigaspaces Technology. The original focus of the Cloudify platform was orchestration of application deployment in a cloud.  This platform combines both NFVO and generic VNFM components of the MANO defined entities
* It provides compute, network, storage for application provisioning and deployment. 
* Cloudify offers interoperability among diverse cloud platforms (e.g., VMware, Cloudstack, Amazon, and Azure) and reduces multi-vendor lock-in.
* some interfaces and actions specified by the NFV IFA subgroup are not present or considered as out of scope for the Cloudify platform. 
* Cloudify is aligned with the MANO reference architecture but not fully compliant.
