# What is React-EventSystem

 A very simple react POC for event propagation. I recommend using mitt should you need real event emitting. 
 
# How do I use it?

Simply import the package.

```js
  import EventSystem from 'eventsystem';
```

Here is how you publish an event.

```js
  componentDidMount() {
    EventSystem.publish('testPublishEvent', { id: 1, message: 'This is an object' });
  }
```	
	
Here is how you subscribe to the event. Dont forget to unsubscribe!

```js
  componentDidMount() {
    EventSystem.subscribe('testPublishEvent', (obj) => {
      this.setState({ data: obj });
    });
  }

  componentWillUnmount() {
    EventSystem.unsubscribe('testPublishEvent');
  }
```	

That's it, more features are planned but this is the first release.
