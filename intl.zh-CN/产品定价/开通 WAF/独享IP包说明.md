# 独享IP包说明 {#concept_qp5_k5n_42b .concept}

## 什么是独享IP包 {#section_zcb_n5n_42b .section}

您购买或开通Web应用防火墙（WAF）后，每个WAF实例会被分配一个WAF IP，该WAF IP可以用于接入多个域名进行防护。通过购买独享IP包，您当前的WAF实例可以获得额外的独享IP，用于接入单个域名实现独享防护。

**说明：** 一个独享 IP仅可以绑定一个域名。

通过独享IP包为域名实现独享防护，可以帮助您解决以下问题：

-   避免一个域名遭受大流量DDoS攻击导致其他域名也无法访问。

    默认情况下，接入WAF实例防护的所有域名都使用同一个WAF IP。因此，当其中一个域名遭受大流量DDoS攻击而导致WAF IP进入黑洞时，该WAF实例所防护的其他域名也无法访问。

    通过购买额外的独享IP包，您可以为重要域名分配独享IP，避免重要域名的访问因其他域名的WAF IP进入黑洞时受到影响。

-   实现多区域源站就近访问。

    WAF在国内多个地域都部署有节点。如果您的网站业务位于不同地域（例如，域名A的源站服务器在北京，域名B的源站服务器在深圳），默认情况下不同地域的业务都只能通过同一个WAF节点进行防护。WAF根据第一个配置在该WAF实例上的域名源站服务器所在的区域就近分配节点。

    通过购买额外的独享IP包，您可以为源站在其它地域的域名分配就近的WAF节点。

    **说明：** WAF将自动根据您的独享IP包绑定的域名源站服务器的所在地域，自动就近分配WAF节点。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/15542/15331808177432_zh-CN.png)


## 如何购买独享IP包 {#section_kpn_55n_42b .section}

对于按照包年包月模式开通的Web应用防火墙实例，您可以在购买实例时选购额外的域名独享资源包（独享IP包）。

**说明：** 对于已经购买的Web应用防火墙实例，您可以通过[升级该WAF实例](intl.zh-CN/产品定价/续费与升级.md#ol_ut4_hdn_42b)来选购额外的域名独享资源包（独享IP包）。

## 如何分配和启用独享IP包 {#section_fdb_n5n_42b .section}

登录[云盾Web应用防火墙控制台](https://yundun.console.aliyun.com/?p=waf)，定位到**管理** \> **网站配置**页面，找到需要分配独享IP的域名，单击打开该域名的**独享IP**开关即可。

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/15542/15331808177433_zh-CN.png)

启用独享IP后，该域名的CNAME将自动解析至新的独享IP。您可以通过Ping该域名的CNAME确认该域名是否已自动解析到新的WAF IP。

**说明：** 如果域名是通过A记录的方式而不是CNAME进行解析，该域名的解析无法完成自动切换。您需要通过Ping该域名的CNAME获得新的WAF IP，并尽快将该域名的DNS手动解析至新的独享IP。

