---
layout: post
title:      "JavaScript basics"
date:       2019-03-04 19:00:10 +0000
permalink:  javascript_basics
---

![](https://cdn-images-1.medium.com/max/1754/1*uLdDWIVkbIkYNQOnkQRD8Q.jpeg)

Let’s talk about JavaScript basics.

**Lexical structure**

JavaScript is a case-sensitive language. 
`var helloworld` and `var helloWorld` are not the same. Because “World” in the second variable starts with a capital W, they are considered two different variables. 

JavaScript uses camelCase. There are other styles such as “CamelCase”, “my_variable” and etc. 
`var helloWorld` in JavaScript is a right way of using camelCase. 

To print or write a data, we use console.log method. 
```
console.log(“Hello World”);
var greeting = “Hello!”;
consol.log(greeting)
```
We wrapped “Hello Word” in the first console.log with quotation marks, because “Hello World” is a string, which is a data type in JavaScript. Strings need to be wrapped with either `“”` or `‘’`. Then we created a variable, a kind of a container to hold our “Hello!” string. When we want to write it out, we can just call the variable name `greeting` which in turn prints out its content, which is our string “Hello!”.

**Comments**

Comments are used to explain actions taken or leave instructions in programming. Comments are not treated to be executable in programming languages. In JavaScript, we can use two different ways of commenting. 
The first way is called inline commenting. Any text in a line that follows two forward slash signs `//` is commented out. 
```
console.log(“The below line is a comment”)
//This is an inline comment and it will be ignored by JavaScript
```
The second way is called block commenting. Any text in the lines between `*/ and /* `are block comments. The difference between inline commenting and block commenting is that in inline commenting we can comment out only one line at a time. If our comments are continued in the second line or the next, we have to use` //` in the beginning of every line. It is preferable to use `//` for one line or a few lines of commenting. On the contrary, when we have a comment that takes up several lines or consist of a block of code, it is better to use `*/ … /*` block commenting. This way we do not have to type the comment sign to every line. 
```
console.log(“The below block is a comment”)
*/ 
* This is the first line of a block comment
*This is the second line of a block comment
* This is the last line of a block comment
*/
```
Most programming languages use a semicolon ; at the end of a statement. JavaScript also uses `;` after each statement to separate statements from each other. In JavaScript, you can skip `; `if each statement uses a new line, and your code still works. But it is recommended to use a semicolon after each statement, because it makes the meaning of the code clear.

