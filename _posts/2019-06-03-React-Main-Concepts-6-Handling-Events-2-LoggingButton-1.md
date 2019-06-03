/*
 * React - Main Concepts - 6. Handling Events - 2. LoggingButton 1
 * https://reactjs.org/docs/handling-events.html
 */

import React from 'react';
import ReactDOM from 'react-dom';

class LoggingButton extends React.Component {
    
    // This synatx ensures `this` is bound within handleClick
    // Warning: this is *experimental* syntax.
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
