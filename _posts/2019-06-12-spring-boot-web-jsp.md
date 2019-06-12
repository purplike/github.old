---
layout: post
title: "Spring Boot Web JSP"
date: 2019-06-12
---
완전간단스프링부트jsp
simple spring boot + jsp

localhost:8080 가면 index.jsp 페이지가 뜬다.
 
 
pom.xml
{% highlight xml %}
    <!-- JSP -->
		<dependency>
			<groupId>javax.servlet</groupId>
			<artifactId>jstl</artifactId>
		</dependency>
		<dependency>
			<groupId>org.apache.tomcat.embed</groupId>
			<artifactId>tomcat-embed-jasper</artifactId>
		</dependency>
{% endhighlight %}

spring.mvc.view.prefix=/WEB-INF/views/
spring.mvc.view.suffix=.jsp


src/main/webapp/WEB-INF/views/index.jsp
{% highlight jsp %}
<%@ page language="java" contentType="text/html; charset=UTF-8"
    pageEncoding="UTF-8"%>
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>index.jsp</title>
</head>
<body>
index.jsp
</body>
</html>
{% endhighlight %}

JspController.java
{% highlight java %}
package com.example.demo;

import org.springframework.stereotype.Controller;
import org.springframework.web.bind.annotation.GetMapping;

@Controller
public class JspController {

	@GetMapping("/")
	public String index() {
		return "index";
	}
}
{% endhighlight %}

sts로그 STS Console
1. Run

  .   ____          _            __ _ _
 /\\ / ___'_ __ _ _(_)_ __  __ _ \ \ \ \
( ( )\___ | '_ | '_| | '_ \/ _` | \ \ \ \
 \\/  ___)| |_)| | | | | || (_| |  ) ) ) )
  '  |____| .__|_| |_|_| |_\__, | / / / /
 =========|_|==============|___/=/_/_/_/
 :: Spring Boot ::        (v2.1.5.RELEASE)

2019-06-12 18:13:52.354  INFO 14560 --- [           main] com.example.demo.JspApplication          : Starting JspApplication on DESKTOP-G1M4NJ8 with PID 14560 (D:\workspaces\sb\workspace\jsp\target\classes started by Maria in D:\workspaces\sb\workspace\jsp)
2019-06-12 18:13:52.356  INFO 14560 --- [           main] com.example.demo.JspApplication          : No active profile set, falling back to default profiles: default
2019-06-12 18:13:53.115  INFO 14560 --- [           main] o.s.b.w.embedded.tomcat.TomcatWebServer  : Tomcat initialized with port(s): 8080 (http)
2019-06-12 18:13:53.147  INFO 14560 --- [           main] o.apache.catalina.core.StandardService   : Starting service [Tomcat]
2019-06-12 18:13:53.147  INFO 14560 --- [           main] org.apache.catalina.core.StandardEngine  : Starting Servlet engine: [Apache Tomcat/9.0.19]
2019-06-12 18:13:53.358  INFO 14560 --- [           main] org.apache.jasper.servlet.TldScanner     : At least one JAR was scanned for TLDs yet contained no TLDs. Enable debug logging for this logger for a complete list of JARs that were scanned but no TLDs were found in them. Skipping unneeded JARs during scanning can improve startup time and JSP compilation time.
2019-06-12 18:13:53.375  INFO 14560 --- [           main] o.a.c.c.C.[Tomcat].[localhost].[/]       : Initializing Spring embedded WebApplicationContext
2019-06-12 18:13:53.376  INFO 14560 --- [           main] o.s.web.context.ContextLoader            : Root WebApplicationContext: initialization completed in 987 ms
2019-06-12 18:13:53.581  INFO 14560 --- [           main] o.s.s.concurrent.ThreadPoolTaskExecutor  : Initializing ExecutorService 'applicationTaskExecutor'
2019-06-12 18:13:53.664  INFO 14560 --- [           main] o.s.b.a.w.s.WelcomePageHandlerMapping    : Adding welcome page template: index
2019-06-12 18:13:53.754  INFO 14560 --- [           main] o.s.b.w.embedded.tomcat.TomcatWebServer  : Tomcat started on port(s): 8080 (http) with context path ''
2019-06-12 18:13:53.758  INFO 14560 --- [           main] com.example.demo.JspApplication          : Started JspApplication in 1.713 seconds (JVM running for 2.684)


2. 웹브라우저에서 localhost:8080 하고 나면

2019-06-12 18:15:58.583  INFO 14560 --- [nio-8080-exec-1] o.a.c.c.C.[Tomcat].[localhost].[/]       : Initializing Spring DispatcherServlet 'dispatcherServlet'
2019-06-12 18:15:58.584  INFO 14560 --- [nio-8080-exec-1] o.s.web.servlet.DispatcherServlet        : Initializing Servlet 'dispatcherServlet'
2019-06-12 18:15:58.591  INFO 14560 --- [nio-8080-exec-1] o.s.web.servlet.DispatcherServlet        : Completed initialization in 7 ms
2019-06-12 18:15:59.239  WARN 14560 --- [nio-8080-exec-1] o.a.c.util.SessionIdGeneratorBase        : Creation of SecureRandom instance for session ID generation using [SHA1PRNG] took [208] milliseconds.
