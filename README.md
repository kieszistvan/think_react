#React Workshop

## Motivation
- created by Facebook engineers (@jordwalke)
- reason: upredictable data flow, performance problems. Check out [this](https://www.youtube.com/watch?v=nYkdrAPrdcw) video by @petehunt and @jingc

## Comparison

### JQuery
> jQuery is a fast, small, and feature-rich JavaScript library. It makes things like HTML document traversal and manipulation, event handling, animation, and Ajax much simpler with an easy-to-use API that works across a multitude of browsers. With a combination of versatility and extensibility, jQuery has changed the way that millions of people write JavaScript.

### Backbone (unopionated on rendering though)
> Backbone.js gives structure to web applications by providing models with key-value binding and custom events, collections with a rich API of enumerable functions, views with declarative event handling, and connects it all to your existing API over a RESTful JSON interface.

### Angular
> uhhhh

### WebComponents
> Web Components consists of several separate technologies. You can think of Web Components as reusable user interface widgets that are created using open Web technology. They are part of the browser and so they do not need external libraries like jQuery or Dojo. An existing Web Component can be used without writing code, simply by adding an import statement to an HTML page. Web Components use new or still-developing standard browser capabilities.

## React (V)

### Seperation of concerns (coupling and cohesion)
- loose coupling is hard to be achieved: View Model changed -> update HTML node || Action on HTML -> update View Model
- strong cohesion throughout your application between HTML and logic

### Components
- loose coupling between _components_ 
- your concern is narrowed down to components
- composing components over composing templates
- state machines
 
```javascript
class MyComponent extends React.Component {
  constructor(props) {
    super(props);
  }
  render() {
    return (
      <div className='main'>
        <MySubComponent name={ this.state.name }/>
      </div>
    )
  }
}

export default MyComponent;

class MySubComponent extends React.Component {
  static get defaultProps() {
    return {
      name: 'YOLO'
    }
  }
  constructor(props) {
    super(props);
  }
  render() {
    return (
      <p>Hello {{ this.props.name }}</p>
    )
  }
}

export default MySubComponent;
```

#### JSX
- supports HTML attributes (class => className, for => htmlFor)
- compile-to-JS
```javascript
React.createElement('a', {href: 'https://facebook.github.io/react/'}, 'Hello!')
```
```html
<a href='https://facebook.github.io/react/'>Hello!</a>
```

#### [Lifecycle](https://facebook.github.io/react/docs/component-specs.html) (mount, update, unmount)
- component gets rendered
- hook up on events with functions
  - render()
  - componentWillMount()
  - componentDidMount()
  - shouldComponentUpdate()

#### Data flow
- goes from parent to child
- props are immutable
- changes are propagated back via callbacks

#### Virtual DOM
- no direct updates to the actual DOM
- minimizing reflow
- batched updates (minimizes changes in time)
- updates only a minimum of elements

#### [Synthetic Events](https://facebook.github.io/react/docs/events.html)
- event handlers works accros browser

#### Component children
- propagation of childs via ```this.props.children```
- it's an Array if component wraps multiple nodes, it is an Object when component wraps just one node
