---
layout: post
title: "React - Main Concepts - 6. Handling Events - 1. Toggle"
date: 2019-06-03 15:00:00 -0000
---
https://reactjs.org/docs/handling-events.html

{% highlight react %}
/*
React - Main Concepts - 6. Handling Events - 1. Toggle
https://ko.reactjs.org/docs/handling-events.html
ES6 클래스를 사용하여 컴포넌트를 정의할 때, 일반적인 패턴은 이벤트 핸들러를 클래스의 메서드로 만드는 것입니다. 예를 들어, 다음 Toggle 컴포넌트는 사용자가 “ON”과 “OFF” 상태를 토글 할 수 있는 버튼을 렌더링합니다.
*/

import React from 'react';
import ReactDOM from 'react-dom';

class Toggle extends React.Component {
    constructor(props) {
        super(props);
        this.state = {isToggleOn: true};

        // This binding is necessary to make `this` work in the callback
        // 콜백에서 `this`가 작동하려면 아래와 같이 바인딩 해주어야 합니다.
        this.handleClick = this.handleClick.bind(this);
    }

    handleClick() {
        this.setState(state => ({
            isToggleOn: !state.isToggleOn
        }));
    }

    render() {
        return (
        <button onClick={this.handleClick}>
            {this.state.isToggleOn ? 'ON' : 'OFF'}
        </button>
        );
    }
}

ReactDOM.render(<Toggle />, document.getElementById('root'));
{% endhighlight %}
