# 1.8. 与 OAuth 2.0 的兼容性

OAuth 2.1 在兼容 OAuth 2.0 的基础上，采用了当前已知最佳实践中的一系列扩展和限制。具体来说，OAuth 2.0 核心中未提及的一些功能，例如 PKCE，在 OAuth 2.1 中是必需的。此外，OAuth 2.0 中可用的一些功能，例如隐式或资源所有者凭据许可类型，在 OAuth 2.1 中不再提及。另外，OAuth 2.0 中允许的一些行为，在 OAuth 2.1 中得到了限制，例如 OAuth 2.1 要求重定向 URI 字符串必须严格匹配。

更多和 OAuth 2.0 的区别的细节见第 10 节。
