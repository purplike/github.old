---
layout: post
title: "NodeJS Textbook 3.2 JS 파일 실행하기"
date: 2019-06-11 17:00
---
{% highlight js %}
function helloWorld() {
    console.log('Hello World');
    helloNode();
}
{% endhighlight %}
function helloNode() {
    console.log('Hello Node');
}
helloWorld();

>node helloWorld
Hello World
Hello Node
