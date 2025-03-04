
# 云边端融合计算
演讲者：欧阳智勇 2022065205，宋癸军 2022065229



## 定义云边端融合计算的核心概念
云边端融合计算是一种结合了云计算、边缘计算和终端设备的协同工作模式，旨在实现更高效的数据处理和系统运行。

物联网等边缘计算设备具有架构上的灵活性与海量数据采集能力的优点，但是受限于设备规模与功耗，自身的算力非常有限，无法在本地深度处理海量的数据，例如在树莓派上运行简单的计算机视觉深度学习模型虽然具有一定的可行性，但是受限于算力，模型无法在规定的有限时间内得出分析结果，从工程实践上考虑这是是不符合要求的

云端具有强大算力，稳定的网络与服务提供能力，缺点是规模巨大，无法灵活移动

通过网络将二者进行连接，实现互补，整体系统具有强大的灵活性与可拓展性，从工程上来看，凡是对数据延迟的需求宽松于云端与物联网之间的通信延迟的体系都可以应用这种结构。例如智慧农业。
云边端融合计算的优势：

1.提高效率：  通过在云端、边缘端和终端设备之间分配和协调数据处理任务，可以提高系统整体的效率和稳定性。

2.减轻云端压力：  将部分计算任务从云端分配到边缘计算节点，可以减轻云端的负载，避免瓶颈和过载情况的发生。

3.快速响应：  边缘计算能够提供更快的响应时间，对于需要即时反馈的场景尤为重要，如自动驾驶、智能制造等。

###### 4.支持AI加速：  在边缘计算场景下进行AI加速，可以实现云端训练、边缘推理的模式，提高AI应用的实时性和可靠性。


## 分析云边端融合计算的本质



## 云计算
云计算是一种计算资源的共享模式，其中数据和应用程序在远程服务器上运行，而不是在本地计算机或设备上。通过这种方式，用户可以从任何地方访问这些资源，只需要一个互联网连接。云计算的核心概念是将计算能力从本地设备转移到云端，使用户能够轻松地访问和管理资源，并根据需要进行扩展。它还可以帮助降低硬件和软件成本，提高效率和生产力，并促进创新和数字化转型。



## 云计算服务的分类
IaaS（基础架构即服务）、PaaS（平台即服务）和 SaaS（软件即服务）是三种最常见的云服务模式，组织使用这三种模式的情况非常普遍。



## SaaS（软件即服务）
SaaS（也称为基于云的软件或云应用程序）是托管在云中的应用程序软件，用户可以通过 Web 浏览器、专用桌面客户端或与桌面或移动操作系统集成的 API 进行访问。大多数情况下，SaaS 用户支付月费或年费；有些可能会根据您的实际使用情况提供“即用即付”定价。

除了云的成本节约、实现价值时间和可扩展性优势之外，SaaS 还提供以下优势：
- 自动升级：用户可以在提供商添加新功能后立即利用这些功能，而无需协调内部升级。
- 防止数据丢失：由于 SaaS 将应用程序数据与应用程序一起存储在云中，因此用户在设备崩溃或损坏时不会丢失数据。

SaaS 是当今大多数商业软件的主要交付模式，有成千上万种 SaaS 解决方案可供选择，从最集中的行业和部门应用程序，到功能强大的企业软件数据库和 AI（人工智能）软件。
![[Pasted image 20240426100633.png]]


## PaaS（平台即服务）
PaaS 为软件开发人员提供按需平台（硬件、完整的软件堆栈、基础架构，甚至开发工具），用于运行、开发和管理应用程序，而无需在本地维护该平台，从而降低了成本和复杂性，并提升了灵活性。

借助 PaaS，云提供商可以在其数据中心托管所有内容（服务器、网络、存储器、操作系统软件、中间件、数据库）。开发人员只需从菜单中选择，就能“启动”运行、构建、测试、部署、维护、更新和扩展应用程序所需的服务器和环境。

如今，PaaS 通常是围绕容器构建的，这是一种与虚拟服务器仅一步之遥的虚拟化计算模型。容器将操作系统虚拟化，使开发人员只需将应用程序与所需的操作系统服务打包，即可在任何平台上运行，无需修改，也无需中间件。



## IaaS（基础架构即服务）
IaaS 以即用即付的方式，通过互联网提供对基本计算资源（物理和虚拟服务器、网络和存储）的按需访问。IaaS 使最终用户能够按需扩展和缩减资源，从而减少了对高额前期资本支出或不必要的本地部署或“自有”基础架构的需求，也减少了为适应周期性使用高峰而过度购买资源的需求。

与 SaaS 和 PaaS（甚至是容器和无服务器等较新的 PaaS 计算模型）相比，IaaS 为用户提供了对云中计算资源的最底层的控制。

IaaS 在 2010 年代初出现时是最受欢迎的云计算模式。虽然它仍然是许多类型工作负载的云模型，但 SaaS 和 PaaS 的使用正以更快的速度增长。



## 无服务器计算 //一种新兴的云服务提供模式
无服务器计算（也简称为无服务器）是一种云计算模型，它将所有后端基础架构管理任务（配置、扩展、调度、修补）转移给云提供商，使开发人员能够将所有时间和精力集中在特定于其应用程序的代码和业务逻辑上。

此外，无服务器仅根据每个请求运行应用程序代码，并根据请求数量自动扩展和缩减支持基础架构。利用无服务器，客户只需为应用程序运行时使用的资源付费，而无需为空闲容量付费。

FaaS（即功能即服务）经常与无服务器计算混淆，而事实上，它是无服务器的子集。FaaS 允许开发人员执行部分应用程序代码（称为功能）以响应特定事件。除了代码之外的所有内容（物理硬件、虚拟机操作系统和 Web 服务器软件管理）均由云服务提供商在代码执行时自动实时配置，并在执行完成后立即恢复。计费在执行开始时开始，在执行停止时停止。



## 云计算的类型
### 公有云
公有云是云计算的一种，云服务提供商通过公共互联网向用户提供计算资源，包括 SaaS 应用程序、单个虚拟机 (VM)、裸机计算硬件、完整的企业级基础架构和开发平台等。这些资源可以免费获取，也可以按照订阅或按使用付费的定价模式购买。

客户运行工作负载使用的数据中心、硬件和基础架构，由公有云提供商拥有、管理，并承担所有责任，通常还提供高带宽网络连接，以确保高性能和快速访问应用程序和数据。

公有云是一个多租户环境，云提供商的数据中心基础架构由所有公有云客户共享。在国外像 Amazon Web Services (AWS)、Google Cloud、Microsoft Azure 和 Oracle Cloud 等领先的公有云，其客户的数量可能达到数百万。

国内主要有阿里云，腾讯云，百度智能云等云服务商。

许多企业正在将其部分计算基础架构迁移到公有云，因为公有云服务具有弹性且易于扩展，可以灵活调整以满足不断变化的工作负载需求。其他企业则被更高的效率和更少的资源浪费所吸引，因为客户只需为他们所使用的资源付费。还有一些公司希望减少在硬件和本地基础架构方面的支出。



### 公有云目前存在的一些问题：
- 服务的稳定性问题与安全性问题
  包括云服务故障（如右图所示）与潜在的网络攻击，如DDoS, 窃取服务器管理员权限等（这部分非常复杂，我还是个菜鸟，就不多说了）。
![[Pasted image 20240425195845.png]]


## 边缘计算
### 边缘计算的的概念
边缘计算是为应用开发者和服务提供商在网络的边缘侧提供云服务和IT环境服务；目标是在靠近数据输入或用户的地方提供计算、存储和网络带宽。



## 分析云边端融合计算的优势
云边端融合计算的优势：
- 提高效率：通过在云端、边缘端和终端设备之间分配和协调数据处理任务，可以提高系统整体的效率和稳定性。
- 减轻云端压力：将部分计算任务从云端分配到边缘计算节点，可以减轻云端的负载，避免瓶颈和过载情况的发生。
- 快速响应：边缘计算能够提供更快的响应时间，对于需要即时反馈的场景尤为重要，如自动驾驶、智能制造等。
- 支持AI加速：在边缘计算场景下进行AI加速，可以实现云端训练、边缘推理的模式，提高AI应用的实时性和可靠性。



## 云计算+物联网的一个应用案例
### 自顶向下的描述方式

1. **项目概述**
   从整体上介绍项目，包括云计算与网络技术。

2. **详细介绍项目中采用的云计算技术和相关网络技术**
   如Docker容器技术、微服务架构和HTTP通信。

3. **物联网技术分析**
   对项目中使用的物联网技术进行简要分析，包括云端与物联网设备的通信技术MQTT和其他设备间的通信方式。



### 项目名称：基于云平台的大豆育种智慧温室解决方案

**项目简介：**本项目利用云计算+物联网，实现对大豆温室育种的智能监控。

**项目需求分析：**对于育种工作而言，实时监测并调控育种环境的光照，温度，湿度，二氧化碳浓度，培养液pH值等等参数是至关重要的，这些环境因素对育种质量有很大的影响。然而通过人工24小时不间断检测，非常耗时耗力，人力成本开销巨大。



### 项目系统架构简图
![[Pasted image 20240425201212.png]]


### 简要系统架构介绍
**物联网部分：**安装在温室内的各种传感器单元，如摄像头，温度计，pH计，湿度计，二氧化碳浓度计。以及实时控制，负责与传感器通信，收集传感器数据，与云端通信的arduino,树莓派等低功耗低算力模块。

**云计算部分：**这部分承担了整个项目中需要高算力的模块。包括负责与物联网进行通信的后端服务，数据库服务，大豆生长情况实时分析预警服务（这部分需要运行一个基于深度学习的大豆叶片疾病检测模型和一个温室环境分析预测模型，对算力的需求最高），以及提供前端页面的服务。



### 系统设置原因
- 物联网边缘算力限制
- 云计算与物联网融合优势

由于物联网设备的边缘算力较低，无法满足深度学习的计算需求，因此需要借助云端的大算力进行快速分析。通过将物联网设备与云端进行融合，可以利用云计算的强大算力和存储能力，实现对大规模数据的高效处理和分析。



### Docker容器技术简介
Docker是一种开源的应用容器引擎，它可以让开发者将应用及其依赖打包到一个轻量级、可移植的容器中，然后发布到任何流行的Linux机器或Windows机器上。



 Docker容器在深度学习模型部署中的应用
通过Docker容器技术，我们可以快速部署一个深度学习模型服务，同时利用其网络结构实现模型的高效运行和通信。



### Docker容器与微服务架构的结合
基于Docker容器化技术发展而来的微服务架构，可以实现服务的松耦合连接和通信，提高系统的稳定性，并能够快速恢复故障。



### 容器技术的一点解释
Linux 容器不是模拟一个完整的操作系统，而是对进程进行隔离。对于容器里面的进程来说，它接触到的各种资源都是虚拟的，从而实现与底层系统的隔离。
![[Pasted image 20240426100943.png]]
由于容器是进程级别的，相比虚拟机有很多优势：
1. **启动快**：容器里面的应用，直接就是底层系统的一个进程，启动容器相当于启动本机的一个进程，速度就快很多。
2. **资源占用少**：容器只占用需要的资源，不占用那些没有用到的资源；多个容器可以共享资源，虚拟机都是独享资源。
3. **体积小**：容器只要包含用到的组件即可，而虚拟机是整个操作系统的打包，所以容器文件比虚拟机文件要小很多。

总之，容器有点像轻量级的虚拟机，能够提供虚拟化的环境，但是成本开销小得多。



### Docker 在解决部署环境问题上的便捷性
![[Pasted image 20240426101811.png]]
上图是我在尝试让一个深度学习模型跑起来时，安装python环境这一步时经常碰到的一类报错。以及后来在开发中遇到的管理多版本多项目python的问题，docker容器能够提供一个更好的隔离环境，防止项目之间因为python版本而发生冲突。



### 容器的网络结构
#### Docker容器网络结构
Docker容器通过虚拟网络进行通信，每个容器拥有自己的网络命名空间和IP地址，实现隔离性和安全性。

#### 容器间通信方式
Docker容器之间可以通过容器名、IP地址或者端口号进行通信，常用的通信方式包括容器链接和网络模式。

#### 容器与宿主机通信
Docker容器可以与宿主机进行通信，通过宿主机的IP地址和端口映射，实现容器内外的数据传输和交互。



### Docker网络
Docker的网络功能相对简单，没有过多复杂的配置，Docker默认使用birdge桥接方式与容器通信。启动Docker后，宿主机上会产生docker0这样一个虚拟网络接口，它是一个虚拟的以太网桥，可以为绑定到docker0上面的网络接口自动转发数据包，这样可以使容器与宿主机之间相互通信。



### 一个关于docker与宿主机网络端口映射的小例子
- bridge: 指定映射的端口号。
- host：将容器内部与宿主机的端口进行一一对应的映射，这样存在一定的风险。



### Docker的快速部署实践
实现服务部署只需要简单的两行代码即可：
```bash
docker pull ghcr.io/gethomepage/homepage:latest
docker run -p 3000:3000 -v /path/to/config:/app/config -v /var/run/docker.sock:/var/run/docker.sock ghcr.io/gethomepage/homepage:latest
```
测试部署是否成功：Homepage

这个服务采用了简单的HTTP通信实现。



### 还存在的问题
- 这个简单的网站没有申请域名，也没有任何DNS服务。
- 这个网站也没有任何TLS加密，单纯的使用了HTTP而不是更安全的HTTPS进行传输。
- 这个网站的后端没有网关，没有鉴权，也没有任何能够处理负载均衡的代理服务器，一旦访问流量过大，服务极易崩溃。



### 微服务架构以及容器的自动化编排
#### 微服务架构与传统集成框架的比较
**微服务架构简介**
微服务架构能够提高系统的稳定性和可靠性，因为当一个服务故障时，其他服务不会受到影响，可以快速恢复并继续提供服务。微服务架构是一种基于容器化技术的松耦合的架构模式，通过将应用程序拆分为多个小型服务，实现高可扩展性和灵活性。
![[aca9c801177228fcd1e8acdf3dbb8c93 1.png]]
与传统的集成在一起的服务框架相比，微服务架构具有更好的可维护性和可扩展性，每个服务都可以独立部署和升级，降低了系统的复杂性。



### 云端与物联网设备通信：MQTT通信



### 项目中物联网与云端连接的方式



### 总结
1. **云计算与物联网的融合**：通过将深度学习模型部署在云端，利用云端的大算力进行快速分析，解决了物联网边缘算力低的问题。
2. **Docker容器技术的应用**：使用Docker容器技术在容器中快速部署深度学习模型服务，并通过容器的网络结构实现服务的松耦合连接通信。
3. **MQTT通信在物联网中的应用**：通过MQTT通信技术实现云端与物联网设备之间的通信，为物联网设备的数据传输提供了高效可靠的解决方案。



## Thank You

 
