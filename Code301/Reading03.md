# React Lists, and Keys

1. What does .map() return?

This function can take an array of numbers and double them, logging them in a new array.

2. If I want to loop through an array and display each value in JSX, how do I do that in React?

By using curly braces, and specifying which element you want to be displayed in JSX.

3. Each list item needs a unique ____.

Key , every list item needs a unique key, which are basically unique string items.

4. What is the purpose of a key?

Keys help React know what's being changed.added, and removed.

## The Spread Operator

1. What is the spread operator?

The spread operator passes in array elements as function parameters.

2. List 4 things that the spread operator can do.

Copying an Array. Concantinating an array, using math functions, and using an array as an argument.

3. Give an example of using the spread operator to combine two arrays.

        const array1 = [1, 2];
        const array2 = [3, 4];
        const array3 = [5, 6];

        const combinedArray = [...array1, ...array2, ...array3];

4. Give an example of using the spread operator to add a new item to an array.

            const oldArray = [1, 2, 3];
            const newItem = 4;

            const newArray = [...oldArray, newItem];

            console.log(newArray); // [1, 2, 3, 4]

     Or, you can add multiple things like this

            const oldArray = [1, 2, 3];
            const newItems = [4, 5];

            const newArray = [...oldArray, ...newItems];

             console.log(newArray); // [1, 2, 3, 4, 5]


5. Give an example of using the spread operator to combine two objects into one.

            const obj1 = { name: 'John', age: 30 };
            const obj2 = { occupation: 'Developer', city: 'New York' };

            const combinedObj = { ...obj1, ...obj2 };

            console.log(combinedObj);
            // Output: { name: 'John', age: 30, occupation: 'Developer', city: 'New York' }


## How to Pass Functions between Components

1. The increment function is used to increase the count value in the state by one every time it is called.

2. The increment function is used to increase the count value in the state by one.

3. To pass a method from a parent component to a child component, you can do the following: Define the method in the parent component. Pass the method as a prop to the child component. In the child component, use the prop to invoke the method.

4. To invoke a method that was passed to a child component from a parent component, the child component needs to call the method using the prop that was passed to it.
