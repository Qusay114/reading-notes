# Forms in React :

HTML form elements work a little bit differently from other DOM elements in React, because form elements naturally keep some internal state. For example, this form in plain HTML accepts a single name:

        <form>
        <label>
            Name:
            <input type="text" name="name" />
        </label>
        <input type="submit" value="Submit" />
        </form>


## Controlled Components :

It's a technique we used in react to create forms and update the input data , which in React mutable state is typically kept in the state property of components, and only updated with setState() .

For example we can write the previous example as a controlled component :

        class NameForm extends React.Component {
        constructor(props) {
            super(props);
            this.state = {value: ''};

            this.handleChange = this.handleChange.bind(this);
            this.handleSubmit = this.handleSubmit.bind(this);
        }

        handleChange(event) {
            this.setState({value: event.target.value});
        }

        handleSubmit(event) {
            alert('A name was submitted: ' + this.state.value);
            event.preventDefault();
        }

        render() {
            return (
            <form onSubmit={this.handleSubmit}>
                <label>
                Name:
                <input type="text" value={this.state.value} onChange={this.handleChange} />
                </label>
                <input type="submit" value="Submit" />
            </form>
            );
        }
        }


# The Conditional (Ternary) Operator :

It's a short way to write the if condition where we need only on line . 

Example using if condition :

        if(x===y){
        console.log(true);
        } else {
        console.log(false);
        }

while using Ternary Operator :

        x===y?console.log(true):console.log(fales) ;