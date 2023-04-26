# React Forms
1. What is a ‘Controlled Component’?

A component whose state is solely controlled by React.

2. Should we wait to store the users responses from the form into state when they submit the form OR should we update the state with their responses as soon as they enter them?

As soon as they enter them, since handleChange updates with every keystroke it makes more since to do it this way.

3. How do we target what the user is entering if we have an event handler on an input field?

You can use the event object that is passed as a paremeter in a `handleInput` function.

## Ternary Operators

1. Why should we use a ternary operator?

To make an if statement shorthand and more concise.

2. Rewrite the following code as a ternary statement.

        if(x===y){
         console.log(true);
        } else {
        console.log(false);
        }

    Like this:
        
        x===y = "True": "False"
