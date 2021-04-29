# Thinking in React : 

The princible of the react app is to break your app into components(parents & children ) , and then combine pass data between them and finally render the parent . 

* I can  break a mock into a component heirarchy by defining each component what the task will handle and wich it will pass data to another component or receive them .

* Single responsibility principle: it means the component should do only one specific task .

* Static version of the application : it means the app is not interactive with the user .

* What are the three questions you can ask to determine if something is state?

1. Is it passed in from a parent via props? If so, it probably isn’t state.

2. Does it remain unchanged over time? If so, it probably isn’t state.

3. Can you compute it based on any other state or props in your component? If so, it isn’t state.

* How can you identify where state needs to live?

1. Identify every component that renders something based on that state.

2. Find a common owner component (a single component above all the components that need the state in the hierarchy).

3. Either the common owner or another component higher up in the hierarchy should own the state.

4. If you can’t find a component where it makes sense to own the state, create a new component solely for holding the state and add it somewhere in the hierarchy above the common owner component.