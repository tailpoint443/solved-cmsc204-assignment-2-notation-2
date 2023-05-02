Download Link: https://assignmentchef.com/product/solved-cmsc204-assignment-2-notation-2
<br>
<strong>Infix notation</strong> is the <strong>notation</strong> commonly used in arithmetical and logical formulae and statements. It is characterized by the placement of operators between operands – “infixed operators” – such as the plus sign in “2 + 2”.

<strong>Postfix notation</strong> is a <strong>notation</strong> for writing arithmetic expressions in which the operands appear before their operators. There are no precedence rules to learn, and parentheses are never needed.

<strong>You will be creating a utility class that converts an infix expression to a postfix expression, a postfix expression to an infix expression and evaluates a postfix expression.</strong>

The GUI is provided.

<strong> Concepts tested:</strong>

Generic Queue

Generic Stack

Exception handling

<strong>Data Element</strong>

<strong>      </strong>String

<strong>Data Structures</strong>

<ol>

 <li>Create a generic queue class called <em>NotationQueue</em>. <em>NotationQueue</em> will implement the <em>QueueInterface</em> given you. You will be creating NotationQueue from scratch (do not use an internal object of the Queue class from java.util)</li>

 <li>Create a generic stack class called <em>NotationStack</em>. <em>NotationStack</em> will implement the <em>Stack Interface</em> given you. You will be creating NotationStack from scratch (do not use an internal object of the Stack class from java.util)</li>

</ol>

<strong>Utility Class</strong>The <em>Notation </em>class will have a method infixToPostfix to convert infix notation to postfix notation that will take in a string and return a string, a method postfixToInfix to convert postfix notation to infix notation that will take in a string and return a string, and a method to evaluatePostfix to evaluate the postfix expression. It will take in a string and return a double.

<strong>      In the infixToPostfix method, you MUST use a queue for the internal structure that holds the postfix solution. Then use the toString method of the Queue to return the solution as a string.</strong>

For simplicity sake:

<ol>

 <li>operands will be single digit numbers</li>

 <li>the following arithmetic operations will be allowed in an expression:</li>

</ol>

+          addition

–           subtraction

*          multiplication

/           division

<strong>Exception Classes</strong>

Provide the following exception classes:

<ol>

 <li>InvalidNotationFormatException – occurs when a Notation format is incorrect</li>

 <li>StackOverflowException – occurs when a top or pop method is called on an empty stack.</li>

 <li>StackUnderflowException – occurs when a push method is called on a full stack.</li>

 <li>QueueOverflowException – occurs when a dequeue method is called on an empty queue.</li>

 <li>QueueUnderflowException – occurs when a enqueue method is called on a full queue.</li>

</ol>




<strong>GUI Driver (provided)</strong>




<ol>

 <li>Initially neither radio button for notation is selected. When a radio button is selected, the Convert button is enabled and the appropriate label and field are visible for the user input.</li>

 <li>When the user selects the Convert button, the appropriate label and field with the conversion will be displayed.</li>

 <li>When the user selects the Evaluate button, the “answer” to the expression will be displayed.</li>

 <li>When the Exit button is selected, the application will close.</li>

</ol>

<strong>ALGORITHMS</strong>

<strong><em><u>Infix expression to postfix expression:</u></em></strong>

Read the infix expression from left to right and do the following:

If the current character in the infix is a space, ignore it.

If the current character in the infix is a digit, copy it to the postfix solution queue

If the current character in the infix is a left parenthesis, push it onto the stack

If the current character in the infix is an operator,

<ol>

 <li>Pop operators (if there are any) at the top of the stack while they have</li>

</ol>

equal or higher precedence than the current operator, and insert the                                     popped operators in postfix solution queue

<ol start="2">

 <li>Push the current character in the infix onto the stack</li>

</ol>

If the current character in the infix is a right parenthesis

<ol>

 <li>Pop operators from the top of the stack and insert them in postfix solution queue until a left parenthesis is at the top of the stack, if no left parenthesis-throw an error</li>

 <li>Pop (and discard) the left parenthesis from the stack</li>

</ol>

When the infix expression has been read, Pop any remaining operators and insert them in postfix solution queue.

<strong><em><u>Postfix expression to infix expression</u></em></strong><strong><em>:</em></strong>

Read the postfix expression from left to right and to the following:

If the current character in the postfix is a space, ignore it.

If the current character is an operand, push it on the stack

If the current character is an operator,

<ol>

 <li>Pop the top 2 values from the stack. If there are fewer than 2 values throw an error</li>

 <li>Create a string with 1<sup>st</sup> value and then the operator and then the 2<sup>nd</sup></li>

 <li>Encapsulate the resulting string within parenthesis</li>

 <li>Push the resulting string back to the stack</li>

</ol>

When the postfix expression has been read:

If there is only one value in the stack – it is the infix string, if more than one

value, throw an error

<strong><em><u>Evaluating a postfix expression</u></em></strong>

Read the postfix expression from left to right and to the following:

If the current character in the postfix expression is a space, ignore it.

If the current character is an operand or left parenthesis, push on the stack

If the current character is an operator,

<ol>

 <li>Pop the top 2 values from the stack. If there are fewer than 2 values throw an error</li>

 <li>Perform the arithmetic calculation of the operator with the first popped value as the right operand and the second popped value as the left operand</li>

 <li>Push the resulting value onto the stack</li>

</ol>

When the postfix expression has been read:

If there is only one value in the stack – it is the result of the postfix expression, if

more than one value, throw an error

<strong>Examples:</strong>

At startup

After selecting Infix to Postfix                                                        After selecting Postfix to Infix

After selecting Convert Button

After selecting Evaluate button


