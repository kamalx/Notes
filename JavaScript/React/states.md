# States and Props

Every serious applications need to represent states *over time*.

State flows down the components, and events flow up. While properties should never be changed, state is mutable.

Properties can't be changed because they are inherited every time the component is rendered, so any changes will be lost.

There's a deeper reason why it's so important to make data flow clear and simple: it encourages you to keep state in as few places as possible and make most of your components stateless.

* [Communicate between components](http://facebook.github.io/react/tips/communicate-between-components.html)
* [Expose component functions](http://facebook.github.io/react/tips/expose-component-functions.html)

**Warning**: The worst thing you can do is call `setState` right after a `render()` in `componentDidMount()` or `componentDidUpdate()`. It means most `render()` will be called twice!

You can have instance properties for state that do not control how a component renders like `this._timer`

**Note**: Data flow down the component hierarchy. Event typically flow upstream to the owner component so they can make the decision to re-render child components.

## PropTypes

```javascript
model: React.PropTypes.instanceOf(Backbone.Model).isRequired
```