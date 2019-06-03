---
title: "React - Main Concepts - 6. Handling Events - 2. LoggingButton 1"
date: 2019-06-03 15:50:00 -0400
---
https://ko.reactjs.org/docs/handling-events.html
만약 bind를 호출하는 것이 불편하다면, 이를 해결할 수 있는 두 가지 방법이 있습니다. 실험적인 퍼블릭 클래스 필드 문법을 사용하고 있다면, 클래스 필드를 사용하여 콜백을 올바르게 바인딩할 수 있습니다.

{% highlight react %}
import React from 'react';
import ReactDOM from 'react-dom';

class LoggingButton extends React.Component {
    
    // This synatx ensures `this` is bound within handleClick
    // Warning: this is *experimental* syntax.
    // 이 문법은 `this`가 handleClick 내에서 바인딩되도록 합니다.
    // 주의: 이 문법은 *실험적인* 문법입니다.
    handleClick = () => {
        console.log('this is:', this);
    }

    render() {
        return (
        <button onClick={this.handleClick}>
            Click me
        </button>
        );
    }
}

ReactDOM.render(<LoggingButton />, document.getElementById('root'));
{% endhighlight %}
