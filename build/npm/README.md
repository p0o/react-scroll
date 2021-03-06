## React Scroll

Directive for basic scrolling and smooth scrolling.
I love contributions, just make sure your test passes. 
I've started writing the tests for all the elements, contribute if you'd like to learn it.

### Install
```js
$ npm install react-scroll
```

### Run
```js
$ npm install
$ npm test
$ npm run examples
```

### Examples
Checkout examples
> Basic
>> [Live](http://fisshy.github.io/react-scroll-example/basic/index.html)
>> Or
>> [Code](https://github.com/fisshy/react-scroll/blob/master/examples/basic/app.js)

### Usage
```js

var React = require('react');
var Scroll = require('react-scroll'); 

var Link = Scroll.Link;
var Element = Scroll.Element;

var Section = React.createClass({
  render: function () {
  	return (
  		<Link to="test1" spy={true} smooth={true} offset={50} duration={500} >Test 1</Link>
		  <Button className="btn" type="submit" value="Test 2" to="test2" spy={true} smooth={true} offset={50} duration={500} >Test 2</Button>

  		<Element name="test1" className="element">
  		  test 1
  		</Element>

  		<Element name="test2" className="element">
  		  test 2
  		</Element>
	);
  }
});

React.render(
  <Section />,
  document.getElementById('example')
);

```

#### Create your own Link/Element
> Simply just include the mixins!

```js
var React = require('react');
var Scroll = require('react-scroll'); 
var Helpers = Scroll.Helpers;

var Element = React.createClass({
  mixins: [Helpers.Element],
  render: function () {
    return (
      <div>
        {this.props.children}
      </div>
    );
  }
});

var Link = React.createClass({
  mixins: [Helpers.Scroll],
  render: function () {
    return (
      <a onClick={this.onClick}>
        {this.props.children}
      </a>
    );
  }
});

```