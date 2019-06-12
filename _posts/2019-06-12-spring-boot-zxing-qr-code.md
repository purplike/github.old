---
layout: post
title: "Spring Boot ZXing QR Code encode"
date: 2019-06-12 
---
파일이 날라가서 기억에 의존하여 소스 써놈. 실행안해봄.
https://github.com/zxing/zxing

pom.xml: core, javase 추가 (둘다 다 해야하는지 하나만 해도 되는진 모름)
{% highlight xml %}
      <dependency>
        <groupId>com.google.zxing</groupId>
        <artifactId>android-core</artifactId>
        <version>${zxing.version}</version>
      </dependency>
      <dependency>
        <groupId>com.google.zxing</groupId>
        <artifactId>javase</artifactId>
        <version>3.1.0</version>
      </dependency>
{% endhighlight %}

QR Code Encode 생성 Generate 부분
{% highlight java %}
QRCodeWriter qrCodeWriter = new QRCodeWriter();
Bitmap bitmap = toBitmap(qrCodeWriter.encode(contents, BarcodeFormat.QR_CODE, 100, 100));
{% endhighlight %}

QrController.java 대략.. 파일 날라가서 실행은 못해봄
{% highlight java %}
package com.example.demo;

import org.springframework.stereotype.Controller;
// zxing 임포트해야징

@Controller
public class QrCodeController {

	public void index() {
    try {
      // 앞뒤로 먼가더잇엇음
      QRCodeWriter qrCodeWriter = new QRCodeWriter();
      Bitmap bitmap = toBitmap(qrCodeWriter.encode(contents, BarcodeFormat.QR_CODE, 100, 100));
      // 앞뒤로 먼가더잇엇음
    } catch (Exception e) {
      e.printStackTrace();
    }
	}
}
{% endhighlight %}

참고사이트 검색해본 사이트
[Android] 안드로이드 QR코드 적용하기 https://dwfox.tistory.com/79
https://hellogk.tistory.com/38
