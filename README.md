# calculator-vuejs

## User stories

-   [ ] User can see a display showing the current number entered or the
result of the last operation.
-   [ ] User can see an entry pad containing buttons for the digits 0-9, 
operations - '+', '-', '/', and '=', a 'C' button (for clear), and an 'AC'
button (for clear all).
-   [ ] User can enter numbers as sequences up to 8 digits long by clicking on
digits in the entry pad. Entry of any digits more than 8 will be ignored.
-   [ ] User can click on an operation button to display the result of that
operation on:
    * the result of the preceding operation and the last number entered OR
    * the last two numbers entered OR
    * the last number entered
-   [ ] User can click the 'C' button to clear the last number or the last
operation. If the users last entry was an operation the display will be
updated to the value that preceded it.

## Comments about the structure of the app

This application is my first project in Vue. Its purpose is to help me understand the fundamentals in this framework. This is the reason why I decided to go with 2 components, to practice the passing of props between parents and childs components. I believe the app would have been more readable in a single component app, but I decided to stay with the original idea because of learning purposes.
