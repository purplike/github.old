---
layout: post
title: "Spring Boot Web JSP 1"
date: 2019-06-13
---
완전간단스프링부트jsp1
simple spring boot + jsp

localhost:8080 가면 index.jsp 페이지가 뜬다.

jsp1
#pom.xml: tomcat만 넣어도 돌아는 간다. 근데 진짜 jsp 사용을 위해선 jstl을 추가해야지
{% highlight xml %}
    <!-- JSP -->
		<dependency>
			<groupId>org.apache.tomcat.embed</groupId>
			<artifactId>tomcat-embed-jasper</artifactId>
		</dependency>
{% endhighlight %}

jsp2
#pom.xml
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

#application.properties
{% highlight %}
spring.mvc.view.prefix=/WEB-INF/views/
spring.mvc.view.suffix=.jsp
{% endhighlight %}

#src/main/webapp/WEB-INF/views/index.jsp
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

#JspController.java
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

#sts로그 STS Console
1. Run
{% highlight %}

  .   ____          _            __ _ _
 /\\ / ___'_ __ _ _(_)_ __  __ _ \ \ \ \
( ( )\___ | '_ | '_| | '_ \/ _` | \ \ \ \
 \\/  ___)| |_)| | | | | || (_| |  ) ) ) )
  '  |____| .__|_| |_|_| |_\__, | / / / /
 =========|_|==============|___/=/_/_/_/
 :: Spring Boot ::        (v2.1.5.RELEASE)

2019-06-13 11:16:37.796  INFO 11924 --- [           main] com.example.demo.JspApplication          : Starting JspApplication on DESKTOP-G1M4NJ8 with PID 11924 (D:\workspaces\sb\workspace\jsp\target\classes started by Maria in D:\workspaces\sb\workspace\jsp)
2019-06-13 11:16:37.800  INFO 11924 --- [           main] com.example.demo.JspApplication          : No active profile set, falling back to default profiles: default
2019-06-13 11:16:38.700  INFO 11924 --- [           main] o.s.b.w.embedded.tomcat.TomcatWebServer  : Tomcat initialized with port(s): 8080 (http)
2019-06-13 11:16:38.723  INFO 11924 --- [           main] o.apache.catalina.core.StandardService   : Starting service [Tomcat]
2019-06-13 11:16:38.723  INFO 11924 --- [           main] org.apache.catalina.core.StandardEngine  : Starting Servlet engine: [Apache Tomcat/9.0.19]
2019-06-13 11:16:38.916  INFO 11924 --- [           main] org.apache.jasper.servlet.TldScanner     : At least one JAR was scanned for TLDs yet contained no TLDs. Enable debug logging for this logger for a complete list of JARs that were scanned but no TLDs were found in them. Skipping unneeded JARs during scanning can improve startup time and JSP compilation time.
2019-06-13 11:16:38.932  INFO 11924 --- [           main] o.a.c.c.C.[Tomcat].[localhost].[/]       : Initializing Spring embedded WebApplicationContext
2019-06-13 11:16:38.932  INFO 11924 --- [           main] o.s.web.context.ContextLoader            : Root WebApplicationContext: initialization completed in 1089 ms
2019-06-13 11:16:39.143  INFO 11924 --- [           main] o.s.s.concurrent.ThreadPoolTaskExecutor  : Initializing ExecutorService 'applicationTaskExecutor'
2019-06-13 11:16:39.216  INFO 11924 --- [           main] o.s.b.a.w.s.WelcomePageHandlerMapping    : Adding welcome page template: index
2019-06-13 11:16:39.305  INFO 11924 --- [           main] o.s.b.w.embedded.tomcat.TomcatWebServer  : Tomcat started on port(s): 8080 (http) with context path ''
2019-06-13 11:16:39.310  INFO 11924 --- [           main] com.example.demo.JspApplication          : Started JspApplication in 1.92 seconds (JVM running for 3.046)
2019-06-13 11:17:45.257  INFO 11924 --- [nio-8080-exec-1] o.a.c.c.C.[Tomcat].[localhost].[/]       : Initializing Spring DispatcherServlet 'dispatcherServlet'
2019-06-13 11:17:45.258  INFO 11924 --- [nio-8080-exec-1] o.s.web.servlet.DispatcherServlet        : Initializing Servlet 'dispatcherServlet'
2019-06-13 11:17:45.267  INFO 11924 --- [nio-8080-exec-1] o.s.web.servlet.DispatcherServlet        : Completed initialization in 9 ms
2019-06-13 11:17:45.951  WARN 11924 --- [nio-8080-exec-1] o.a.c.util.SessionIdGeneratorBase        : Creation of SecureRandom instance for session ID generation using [SHA1PRNG] took [248] milliseconds.
{% endhighlight %}
