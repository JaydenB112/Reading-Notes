# Expressions and Operators
An Expression is a value of code that resolves a value. There ae two types of expressions, those that have side effects and those that purely evaluate.

The expression x=7 is an example of the first type. This expression x=7 is an example of the first type. It uses the equal sign to assign 7 to the variable x. The expression itself evaluates to 7.

The expression 3+4 is an example of the second type. This expression uses the + operator to add 3 and 4 together and produces seven. If not apart of a bigger construct the result will be discarded immediately. These also show that all complex expressions are joined by operators.

Operators join operands either formed by higher precedence operators or one of the basic expressions. The precedence of operators determines the order they are applied when evaluating an expression. For example
const x = 1 + 2 * 3;
const y = 2 * 3 + 1;

Despite * and + coming in different orders both expressions would result in 7 because * has precedence over +, so the *-joined expression will always be evaluated first. You can override operator precedence by using parenthesis (which creates a group expression) 