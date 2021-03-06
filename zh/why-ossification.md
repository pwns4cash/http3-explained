# 协议僵化(Ossification)

互联网，是多个网络互联之网。为了保证互联网工作正常，我们需要在互联网各处搭建各种设备。这些在互联网上分布式架设的设备被称为中间设备（middle-box）。两个端点之间的设备将参与网络数据传输过程。

这些设备用途各异，但是我觉得，我们可以这样想，这些设备，都是为了实现把它们放在这里的人的特定目的。

这些目的包括：转发数据包、挡住恶意流量、地址转换、增进效率、监视流量，等等。

为了完成这些目的，这些设备必须了解他们监视或者修改的数据包的协议。这是靠一些软件实现的，而这些软件的更新并不是那么频繁。

这些设备是把互联网“粘”在一起的关键元素，但是他们经常跟不上最新的技术。网络的核心与边缘（客户端、服务器）相比更新很慢。

所以这些设备决定通过他们的流量OK不OK的时候就会有问题了，在这些设备部署之后的一段时间，协议有了新的特性。在引入了这些新特性的时候，这些设备会觉得这种特性是非法、恶意的。它们会把这种流量直接扔掉，或者放慢到用户不想用这些新特性为止。

这就是“协议僵化”。

协议僵化也会影响TCP的更新：客户端和远程服务器端之间的中间设备会检测对于它们未知的TCP选项，然后拦截这些流量，因为它们不知道这些选项是干什么的。如果中间设备监测协议的细节，这些设备将会学习到协议典型的行为，经过一段时间后，这些行为将无法被更改。

尽可能将通信过程加密是对抗僵化的唯一有效手段。因为加密可以防止中间设备对通过流量的检测。