# react-try-catch-render

Utility which wraps your react components render method and renders an ErrorHandler component in place of the faulty one.
It is inspired by Dan Abramov's [react-transform-catch-errors](https://github.com/gaearon/react-transform-catch-errors)

## Installation

```
npm install --save-dev react-try-catch-render
```


## Usage

```
import wrapWithTryCatch from 'react-try-catch-render'

class MyErrorHandler extends React.Component {
    render(){
        return (
            <div className="terrible-error">{this.props.error}</div>
        );
    }
}

class MyComponent extends React.Component {

  render(){

    throw new Error('Something went terribly worng inside this render');

    return <div>Hello</div>;
  }
}


wrapWithTryCatch(React, MyErrorHandler, {error: "Some custom error message!"})(MyComponent);
```

## License

MIT
