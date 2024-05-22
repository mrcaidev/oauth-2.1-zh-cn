# 概述

原生应用是在资源所有者使用的设备上安装和运行的客户端（即桌面端应用和移动端应用）。原生应用需要特别考虑安全性、平台功能和终端用户的整体体验。

授权端点需要客户端与资源所有者的用户代理交互。当前的最佳实践是，在外部用户代理（通常是浏览器），而不是嵌入式用户代理（例如使用 Web View 实现的用户代理）中，进行 OAuth 授权请求。

原生应用可以使用重定向 URI 捕获授权服务器的响应。该重定向 URI 采用的方案是在操作系统中注册以调用客户端作为处理程序、手动复制粘贴凭据、运行本地网络服务器、安装用户代理扩展，或者提供重定向 URI 以识别由客户端控制的服务器资源，进而将响应提供给原生应用。

以前，原生应用经常使用嵌入式用户代理（通常使用 Web View 实现）处理 OAuth 授权请求。这种方法有很多缺点，包括主机上的应用可以复制用户凭据和 cookies，以及用户需要在每个应用中从头开始验证。有关使用嵌入式用户代理实现 OAuth 的缺点的深入分析，见第 8.5.1 节。

使用系统浏览器的原生应用授权请求更安全，而且可以利用设备上的用户认证状态。使用浏览器中现有的认证会话可实现单点登录，因为用户无需在每次使用新应用时都与授权服务器进行认证（除非授权服务器的策略要求这样做）。

即使不更改 OAuth 协议本身，也能够支持原生应用和浏览器之间的授权流程，因为 OAuth 授权的请求和响应已经以 URI 的形式定义，其中包括用于应用间通信的 URI。有些 OAuth 服务器的实现假定了所有客户端都是机密的网络客户端，这些服务器需要进一步了解公共的原生应用客户端，以及它们使用的重定向 URI 的类型，以支持这一最佳实践。