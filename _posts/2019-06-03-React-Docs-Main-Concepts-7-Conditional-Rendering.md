---
layout: post
title: "React - Docs - Main Concepts - 7. Conditional Rendering"
date: 2019-06-03 17:00
---
조건부 렌더링
https://ko.reactjs.org/docs/conditional-rendering.html
이 예시는 isLoggedIn prop에 따라서 다른 인사말을 렌더링 합니다.

index.js
{% highlight react %}
import React from 'react';
import ReactDOM from 'react-dom';

function UserGreeting(props) {
    return <h1>Welcome back!</h1>;
}

function GuestGreeting(props) {
    return <h1>Please sign up.</h1>;
}

function Greeting(props) {
    const isLoggedIn = props.isLoggedIn;
    if (isLoggedIn) {
        return <UserGreeting />;
    }
    return <GuestGreeting />;
}

ReactDOM.render(
    // Try changing to isLoggedIn={true}
    <Greeting isLoggedIn={false} />,
    document.getElementById('root')
);
{% endhighlight %}

엘리먼트 변수

{% highlight react %}
import React from 'react';
import ReactDOM from 'react-dom';

function UserGreeting(props) {
    return <h1>Welcome back!</h1>;
}

function GuestGreeting(props) {
    return <h1>Please sign up.</h1>;
}

function Greeting(props) {
    const isLoggedIn = props.isLoggedIn;
    if (isLoggedIn) {
        return <UserGreeting />;
    }
    return <GuestGreeting />;
}
/*
ReactDOM.render(
    // Try changing to isLoggedIn={true}
    <Greeting isLoggedIn={false} />,
    document.getElementById('root')
);
*/

function LoginButton(props) {
    return (
        <button onClick={props.onClick}>
            Login
        </button>
    );
}

function LogoutButton(props) {
    return (
        <button onClick={props.onClick}>
            Logout
        </button>
    );
}

class LoginControl extends React.Component {
    constructor(props) {
        super(props);
        this.handleLoginClick = this.handleLoginClick.bind(this);
        this.handleLogoutClick = this.handleLogoutClick.bind(this);
        this.state = {isLoggedIn: false};
    }

    handleLoginClick() {
        this.setState({isLoggedIn: true});
    }

    handleLogoutClick() {
        this.setState({isLoggedIn: false});
    }

    render() {
        const isLoggedIn = this.state.isLoggedIn;
        let button;

        if (isLoggedIn) {
            button = <LogoutButton onClick={this.handleLogoutClick} />;
        } else {
            button = <LoginButton onClick={this.handleLoginClick} />;
        }

        return (
            <div>
                <Greeting isLoggedIn={isLoggedIn} />
                {button}
            </div>
        );
    }
}

ReactDOM.render(
    <LoginControl />,
    document.getElementById('root')
);
{% endhighlight %}
