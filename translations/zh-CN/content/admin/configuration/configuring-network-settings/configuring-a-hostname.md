---
title: 配置主机名
intro: 我们建议为您的设备设置主机名，不建议使用硬编码 IP 地址。
redirect_from:
  - /enterprise/admin/guides/installation/configuring-hostnames
  - /enterprise/admin/installation/configuring-a-hostname
  - /enterprise/admin/configuration/configuring-a-hostname
  - /admin/configuration/configuring-a-hostname
versions:
  ghes: '*'
type: how_to
topics:
  - Enterprise
  - Fundamentals
  - Infrastructure
---

如果配置的是主机名，而不是硬编码 IP 地址，您将能够更改运行 {% data variables.product.product_location %} 的物理硬件，而不会影响用户或客户端软件。

{% data variables.enterprise.management_console %} 中的主机名设置应设置为合适的完全限定域名 (FQDN)，此域名可在互联网上或您的内部网络内解析。 例如，您的主机名设置可能是 `github.companyname.com。` Web 和 API 请求将自动重定向到 {% data variables.enterprise.management_console %} 中配置的主机名。 请注意，`localhost` 不是有效的主机名设置。

Hostnames must be less than 63 characters in length per [Section 2.3.4 of the Domain Names Specification RFC](https://datatracker.ietf.org/doc/html/rfc1035#section-2.3.4).

配置主机名后，可以启用子域隔离以进一步提高 {% data variables.product.product_location %} 的安全性。 更多信息请参阅“[启用子域隔离](/enterprise/admin/guides/installation/enabling-subdomain-isolation/)”。

有关支持的主机名类型的详细信息，请参阅 [HTTP RFC 2.1 节](https://tools.ietf.org/html/rfc1123#section-2)。

{% data reusables.enterprise_installation.changing-hostname-not-supported %}

{% data reusables.enterprise_site_admin_settings.access-settings %}
{% data reusables.enterprise_site_admin_settings.management-console %}
{% data reusables.enterprise_management_console.hostname-menu-item %}
4. 输入想要为 {% data variables.product.product_location %} 设置的主机名。 ![用于设置主机名的字段](/assets/images/enterprise/management-console/hostname-field.png)
5. 要测试新主机名的 DNS 和 SSL 设置，请单击 **Test domain settings**。 ![测试域设置按钮](/assets/images/enterprise/management-console/test-domain-settings.png)
{% data reusables.enterprise_management_console.test-domain-settings-failure %}
{% data reusables.enterprise_management_console.save-settings %}

为了帮助缓解各种跨站点脚本漏洞，我们建议您在配置主机名后为 {% data variables.product.product_location %} 启用子域隔离。 更多信息请参阅“[启用子域隔离](/enterprise/admin/guides/installation/enabling-subdomain-isolation/)”。
