### Learning react *again*

All information is here 

https://legacy.reactjs.org/tutorial/tutorial.html
# Check Comments for general notes along the code

# Extra notes are typed up here. 

//When you call setState in a component, React automatically updates the child components inside of it too.

// In JavaScript classes, you need to always call super when defining the constructor of a subclass.

```
  constructor(props) {
    super(props); 
    this.state = {
      value: null,
    };
  }
```


After creating the state value for each square, since state is considered to be private to a component that defines it, we cannot update the Board’s state directly from Square.

# Event listeners
When a Square is clicked, the onClick function provided by the Board is called. Here’s a review of how this is achieved:

-> The onClick prop on the built-in DOM <button> component tells React to set up a click event listener.
-> When the button is clicked, React will call the onClick event handler that is defined in Square’s render() method.
-> This event handler calls this.props.onClick(). The Square’s onClick prop was specified by the Board.
->Since the Board passed onClick={() => this.handleClick(i)} to Square, the Square calls the Board’s handleClick(i) when clicked.
-> We have not defined the handleClick() method yet, so our code crashes. If you click a square now, you should see a red error screen saying something like “this.handleClick is not a function”.

## After HandleClick implementation in class Board ()

We’re again able to click on the Squares to fill them, the same as we had before. However, now the state is stored in the Board component instead of the individual Square components. When the Board’s state changes, the Square components re-render automatically. Keeping the state of all squares in the Board component will allow it to determine the winner in the future.