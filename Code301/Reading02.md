# React Lifecycle

1. Based off the diagram, what happens first, the ‘render’ or the ‘componentDidMount’?

    The render, the only you can get to the componentDidMount is is you pass through render anyway.

2. What is the very first thing to happen in the lifecycle of React?

    The constructor in the mounting stage of the React lifestyle.

3. Put the following things in the order that they happen: componentDidMount, render, constructor, componentWillUnmount, React Update.

    Constructor, Render, React Update, componentDidMount, componentWillUpdate

4. What does componentDidMount do?

    It's called after the component is rendered and runs statements that require the component be rendered, so that's one of the big reasons on why it's rendered here.

## React State vs Props

1. What types of things can you pass in the props?

   All data types, objects arrays etc.

2. What is the big difference between props and state?

State is internal and props is external.

3.When do we re-render our application?

By changing the state you can re render the app.

4.What are some examples of things that we could store in state?

You could use numbers, strings, and objects.
