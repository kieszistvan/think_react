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
- livecycle events
 
```javascript
class Drawer extends React.Component {
  render() {
   return (
     <div className='drawer'>
      <ul className='drawer__items'>
       <li className='drawer__item'>Item 1</li>
       <li className='drawer__item'>Item 2</li>
       <li className='drawer__item'>Item 3</li>
      </ul>
     </div>
   )
  }
}

export default Drawer;
```

