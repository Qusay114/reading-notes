# Lists and keys :
we use map function which it return array to create our lists where we can put the return values inside the list items using JSX , so each list item it will have a unique value . 

Example :

        function NumberList(props) {
        const numbers = props.numbers;
        const listItems = numbers.map((number) =>
            <li>{number}</li>
        );
        return (
            <ul>{listItems}</ul>
        );
        }

        const numbers = [1, 2, 3, 4, 5];
        ReactDOM.render(
        <NumberList numbers={numbers} />,
        document.getElementById('root')
        );


# Spread operator :
The spread operator ... is used to expand or spread an iterable or an array.

Example : 

        const arrValue = ['My', 'name', 'is', 'Jack'];

        console.log(arrValue);   // ["My", "name", "is", "Jack"]
        console.log(...arrValue); // My name is Jack


The … spread operator is useful for many different routine tasks in JavaScript, including the following:

* Copying an array
* Concatenating or combining arrays
* Using Math functions
* Using an array as arguments
* Adding an item to a list
* Adding to state in React
* Combining objects
* Converting NodeList to an array
