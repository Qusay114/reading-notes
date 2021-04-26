# What is state and lifcycle in react ? 
 React web apps are actually a collection of independent components that run according to the interactions made with them. Every React Component has a lifecycle of its own, lifecycle of a component can be defined as the series of methods that are invoked in different stages of the component’s existence.

 A React Component can go through four stages of its life as follows. 
 

Initialization: This is the stage where the component is constructed with the given Props and default state. This is done in the constructor of a Component Class.
Mounting: Mounting is the stage of rendering the JSX returned by the render method itself.
Updating: Updating is the stage when the state of a component is updated and the application is repainted.
Unmounting: As the name suggests Unmounting is the final step of the component lifecycle where the component is removed from the page.



# Handling events in react :
the events in react elements is similar to handling events on DOM elements , but there are some syntax differences:

*React events are named using camelCase, rather than lowercase.

*With JSX you pass a function as the event handler, rather than a string.

Example on react elements :

	<button onClick=	{activateLasers}>
 	 Activate Lasers
	</button>

# Conditional Rendering :
as we know in react we render html elements using javaScript , so we can add conditions and according to those conditions it will render .
Example :

    function Greeting(props) {
    const isLoggedIn = props.isLoggedIn;
    if (isLoggedIn) {
        return <UserGreeting />;
    }
    return <GuestGreeting />;
    }

    ReactDOM.render(
    // Try changing to isLoggedIn={true}:
    <Greeting isLoggedIn={false} />,
    document.getElementById('root')
    );

