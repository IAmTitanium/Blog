---
title: Http状态码
date: 2018-03-11 17:00:37
categories: JS
tags: 前后端交互篇
cover: /img/httplogo.jpg
---

### 状态码

* 100    Continue    继续。客户端应继续其请求

* 101    Switching Protocols    切换协议。服务器根据客户端的请求切换协议。只能切换到更高级的协议，例如，切换到HTTP的新版本协议

* 200    OK    请求成功。一般用于GET与POST请求

* 201    Created    已创建。成功请求并创建了新的资源
 
* 202    Accepted    已接受。已经接受请求，但未处理完成
 
* 203    Non-Authoritative Information    非授权信息。请求成功。但返回的meta信息不在原始的服务器，而是一个副本
 
* 204    No Content    无内容。服务器成功处理，但未返回内容。在未更新网页的情况下，可确保浏览器继续显示当前文档
 
* 205    Reset Content    重置内容。服务器处理成功，用户终端（例如：浏览器）应重置文档视图。可通过此返回码清除浏览器的表单域
 
* 206    Partial Content    部分内容。服务器成功处理了部分GET请求
 
* 300    Multiple Choices    多种选择。请求的资源可包括多个位置，相应可返回一个资源特征与地址的列表用于用户终端（例如：浏览器）选择
 
* 301    Moved Permanently    永久移动。请求的资源已被永久的移动到新URI，返回信息会包括新的URI，浏览器会自动定向到新URI。今后任何新的请求都应使用新的URI代替
 
* 302    Found    临时移动。与301类似。但资源只是临时被移动。客户端应继续使用原有URI
 
* 303    See Other    查看其它地址。与301类似。使用GET和POST请求查看

* 304    Not Modified    未修改。所请求的资源未修改，服务器返回此状态码时，不会返回任何资源。客户端通常会缓存访问过的资源，通过提供一个头信息指出客户端希望只返回在指定日期之后修改的资源
 
* 305    Use Proxy    使用代理。所请求的资源必须通过代理访问
 
* 306    Unused    已经被废弃的HTTP状态码
 
* 307    Temporary Redirect    临时重定向。与302类似。使用GET请求重定向
 
* 400    Bad Request    客户端请求的语法错误，服务器无法理解
 
* 401    Unauthorized    请求要求用户的身份认证
 
* 402    Payment Required    保留，将来使用
 
* 403    Forbidden    服务器理解请求客户端的请求，但是拒绝执行此请求
 
* 404    Not Found    服务器无法根据客户端的请求找到资源（网页）。通过此代码，网站设计人员可设置"您所请求的资源无法找到"的个性页面

* 500    Internal Server Error    服务器内部错误，无法完成请求
 
* 501    Not Implemented    服务器不支持请求的功能，无法完成请求

* 502    Bad Gateway    作为网关或者代理工作的服务器尝试执行请求时，从远程服务器接收到了一个无效的响应
 
* 503    Service Unavailable    由于超载或系统维护，服务器暂时的无法处理客户端的请求。延时的长度可包含在服务器的Retry-After头信息中

* 504    Gateway Time-out    充当网关或代理的服务器，未及时从远端服务器获取请求
 
* 505    HTTP Version not supported    服务器不支持请求的HTTP协议的版本，无法完成处理

### 常用请求头
| 协议头| 说明| 示例| 状态 |
| :----- | :----- | :----- | :----- |
Accept |可接受的响应内容类型（Content-Types）|	Accept: text/plain	|固定
Accept-Charset|可接受的字符集	|Accept-Charset: utf-8	|固定
Accept-Encoding|	可接受的响应内容的编码方式。	|Accept-Encoding: gzip, deflate	|固定
Accept-Language	|可接受的响应内容语言列表。	|Accept-Language: en-US	|固定
Accept-Datetime	|可接受的按照时间来表示的响应内容版本	|Accept-Datetime: Sat, 26 Dec 2015 17:30:00 GMT	|临时
Authorization	|用于表示HTTP协议中需要认证资源的认证信息	|Authorization: Basic OSdjJGRpbjpvcGVuIANlc2SdDE==	|固定
Cache-Control	|用来指定当前的请求/回复中的，是否使用缓存机制。	|Cache-Control: no-cache	|固定
Connection	|客户端（浏览器）想要优先使用的连接类型	|Connection: keep-alive
Connection: |Upgrade |固定
Cookie	|由之前服务器通过Set-Cookie（见下文）设置的一个HTTP协议 |Cookie	Cookie: $Version=1; Skin=new;	|固定：标准
Content-Length|以8进制表示的请求体的长度	|Content-Length: 348	|固定
Content-MD5	|请求体的内容的二进制 MD5 散列值（数字签名），以 Base64 编码的结果	|Content-MD5: oD8dH2sgSW50ZWdyaIEd9D==	|废弃
Content-Type	|请求体的MIME类型 （用于POST和PUT请求中）	|Content-Type: application/x-www-form-urlencoded	|固定
Date	|发送该消息的日期和时间（以RFC 7231中定义的"HTTP日期"格式来发送）	|Date: Dec, 26 Dec 2015 17:30:00 GMT	|固定
Expect	|表示客户端要求服务器做出特定的行为	| Expect: 100-continue	|固定
From	|发起此请求的用户的邮件地址	|From: user@itbilu.com	|固定
Host	|表示服务器的域名以及服务器所监听的端口号。如果所请求的端口是对应的服务的标准端口（80），则端口号可以省略。	|Host: www.itbilu.com:80
Host: |www.itbilu.com ||固定
If-Match|	仅当客户端提供的实体与服务器上对应的实体相匹配时，才进行对应的操作。主要用于像 PUT 这样的方法中，仅当从用户上次更新某个资源后，该资源未被修改的情况下，才更新该资源。	|If-Match: "9jd00cdj34pss9ejqiw39d82f20d0ikd"	|固定
If-Modified-Since|	允许在对应的资源未被修改的情况下返回304未修改	| If-Modified-Since: Dec, 26 Dec 2015 17:30:00 GMT	|固定
If-None-Match	|允许在对应的内容未被修改的情况下返回304未修改（ 304 Not Modified ），参考 超文本传输协议 的实体标记	|If-None-Match: "9jd00cdj34pss9ejqiw39d82f20d0ikd"	|固定
If-Range	|如果该实体未被修改过，则向返回所缺少的那一个或多个部分。否则，返回整个新的实体	|If-Range: "9jd00cdj34pss9ejqiw39d82f20d0ikd"	|固定
If-Unmodified-Since|	仅当该实体自某个特定时间以来未被修改的情况下，才发送回应。	|If-Unmodified-Since: Dec, 26 Dec 2015 17:30:00 GMT	|固定
Max-Forwards	|限制该消息可被代理及网关转发的次数。	|Max-Forwards: 10	|固定
Origin	|发起一个针对跨域资源共享的请求（该请求要求服务器在响应中加入一个Access-Control-Allow-Origin的消息头，表示访问控制所允许的来源）。	|Origin: http://www.itbilu.com	|固定: 标准
Pragma	|与具体的实现相关，这些字段可能在请求/回应链中的任何时候产生。	|Pragma: no-cache	|固定
Proxy-Authorization	|用于向代理进行认证的认证信息。	|Proxy-Authorization: Basic IOoDZRgDOi0vcGVuIHNlNidJi2==	|固定
Range	|表示请求某个实体的一部分，字节偏移以0开始。	|Range: bytes=500-999	|固定
Referer	|表示浏览器所访问的前一个页面，可以认为是之前访问页面的链接将浏览器带到了当前页面。Referer其实是Referrer这个单词，但RFC制作标准时给拼错了，后来也就将错就错使用Referer了。	|Referer: http://itbilu.com/nodejs	|固定
TE	|浏览器预期接受的传输时的编码方式：可使用回应协议头Transfer-Encoding中的值（还可以使用"trailers"表示数据传输时的分块方式）用来表示浏览器希望在最后一个大小为0的块之后还接收到一些额外的字段。	|TE: trailers,deflate	|固定
User-Agent|	浏览器的身份标识字符串	|User-Agent: Mozilla/……	|固定
Upgrade	|要求服务器升级到一个高版本协议。	|Upgrade: HTTP/2.0, SHTTP/1.3, IRC/6.9, RTA/x11	|固定
Via	|告诉服务器，这个请求是由哪些代理发出的。	|Via: 1.0 fred, 1.1 itbilu.com.com (Apache/1.1)	|固定
Warning|	一个一般性的警告，表示在实体内容体中可能存在错误。	|Warning: 199 Miscellaneous warning	|固定