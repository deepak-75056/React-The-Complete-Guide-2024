# React - The Complete Guide 2024 (incl. React Router & Redux) 🚀
Welcome to my Git repository for **React - The Complete Guide!** <img height=20px src="https://skillicons.dev/icons?i=react"> This 68 hours Udemy course has equipped me with comprehensive knowledge and practical experience in React development, including components, props, React-hooks, forms, Redux, Routing, states + responses, Next.js. 🧾

<div align=center>
  <img height="350px" src="https://github.com/shanibider/React---The-Complete-Guide-2024/assets/72359805/3d5c195b-4177-4da2-ae13-5234de5ed3cd">
</div> <br>

### 🏆 Course Overview -

# ◻ Section 2: JavaScript Refresher:
### ◻ Arrow Function: 
```javascript
default function (){
  console.log('hello');
}
// equal to:
default (userName, message) => {
  return userName + message;
}

// More on the Arrow Function Syntax:
// 1) If takes exactly one parameter, you may omit the wrapping parentheses.
default userName => {
  return userName + message;
}

// 2) If your arrow function contains no other logic but a return statement, you may omit the curly braces and the return keyword.
number => number * 3;
// equal to:
number => { 
  return number * 3;
}

// 3) Special case: Just returning an object
// If you go for the shorter alternative explained in 2) and you're trying to return a JavaScript object,
// you may end up with the following, invalid code: number => { age: number }; // trying to return an object
// This code would be invalid because JavaScript treats the curly braces as function body wrappers
// (not as code that creates a JS object).
// To "tell" JavaScript that an object should be created (and returned) instead,
// the code would need to be adjusted like this:
number => ({ age: number }); // wrapping the object in extra parentheses
```

### ◻ objects:
```javascript
const user = {
name: "Shani",
hobby: "fitness",
greet(){
  console.log ("Hello");
  console.log (this.hobby);
}
};
console.log (user.name);
user.greet();



Class User{
  constructor(name,age){
    this.name = name;
    this.hobby = hobby;
}

greet(){
  console.log ("Hi");
}

const user1 = new User("Shai", "painting");
user1.greet();
```


### ◻ Arrays:
```javascript
const hobbies = ["sport", "cooking", "reading"];
  console.log (hobbies[0]);

hobbies.push("working");

const index = hobbies.findIndex((item) => {
  return item === 'sport';  
});
console.log(index); //0
//equal to:
const index = hobbies.findIndex((item) => item === 'sport');

const editedHobbies = hobbies.map((item) => item = "!");


// Array Methods
function transformToObjects(numberArray) {
    // transform a list of numbers into a list of JavaScript objects. And return an array of objects    
    const newArray = numberArray.map ((item) => ({val:item}))
    return newArray;
}
// For example, for the provided input [1, 2, 3] the function should return [{val: 1}, {val: 2}, {val: 3}].


// Destructing
// To destruct an array we add '[]' 
const [firstName, lastName] = ["Shani", "Bider"];
  console.log (firstName);
  console.log (lastName);

// To destruct an object we add '{}'. Must use the same property name.
// Could also use alias
const { name: userName, hobby } = {
name: "Shani",
hobby: "fitness",
};
  console.log (usertName);
  console.log (hobby);
```


#### The Spread Operator `...`
```javascript
const hobbies = ["sport", "cooking", "reading"];

const user = {
name: "Shani",
hobby: "fitness"
}

const newHobbies = ["reading"];

const mergedHobbies = [...hobbies,...newHobbies];

const extendedUser = {
  isAdmin: true,
  ...user    //here ... will pull out all the 'key,value' pairs from the user object, and add them to that object here
}
/*
will log:
isAdmin: true
name: "Shani"
hobby: "fitness"
*/
```



```javascript
const password = prompt("your password");

if (password === "Hello"){
  console.log("Hello works");
} else if (password === "hello"){
  console.log("hello works");
} else {
  console.log("access failed");
}
```



### ◻ Functions as values
```javascript
function handleTimeout(){
  console.log("Timed out");
}

function handleTimeout2 = () => {
  console.log("Timed out");
}

setTimeout(handleTimeout,2000);  // setTimeout is default js function
setTimeout(handleTimeout2,3000);
setTimeout( () =>{
  console.log("Timed out");
}, 4000);



// Functions inside of functions
function init() {
  function greet() {
    console.log(“Hi!“);
  }

  greet();
}
init();


const hobbies = ["Sports", "Cooking"];
hobbies = [];
hobbies.push("Working");
console.log(hobbies);


// let
// The let declaration declares re-assignable, block-scoped local variables, optionally initializing each to a value.
let x = 1;

if (x === 1) {
  let x = 2;
  console.log(x);  // Expected output: 2
}
console.log(x);// Expected output: 1


// const
// The const declaration declares block-scoped local variables.
// The value of a constant can't be changed through reassignment using the assignment operator,
// but if a constant is an object, its properties can be added, updated, or removed.
const number = 42;

try {
  number = 99;
} catch (err) {
  console.log(err);
  // Expected output: TypeError: invalid assignment to const 'number'
  // (Note: the exact output may be browser-dependent)
}
console.log(number);// Expected output: 42


// ES6 Arrow Functions
// Arrow functions are a different way of creating functions in JavaScript. Besides a shorter syntax, they offer advantages when it comes to keeping the scope of the this  keyword (see here).
// Arrow function syntax may look strange but it's actually simple.

function callMe(name) { 
    console.log(name);
}

// which you could also write as:
const callMe = function(name) { 
    console.log(name);
}

// becomes: 
const callMe = (name) => { 
    console.log(name);
}


// Important: 
// When having no arguments, you have to use empty parentheses in the function declaration:
const callMe = () => { 
    console.log('Max!');
}

// When having exactly one argument, you may omit the parentheses:
const callMe = name => { 
    console.log(name);
}

// When just returning a value, you can use the following shortcut:
const returnMe = name => name

// That's equal to:
const returnMe = name => { 
    return name;
}


// Exports & Imports
// In React projects (and actually in all modern JavaScript projects),
// you split your code across multiple JavaScript files - so-called modules.
// You do this, to keep each file/ module focused and manageable.
// To still access functionality in another file, you need export  (to make it available) and import  (to get access) statements.

// You got two different types of exports: default (unnamed) and named exports:

default => export default ...; 

named => export const someData = ...; 

// You can import default exports like this:
import someNameOfYourChoice from './path/to/file.js'; 

// Surprisingly, someNameOfYourChoice  is totally up to you.

// Named exports have to be imported by their name:
import { someData } from './path/to/file.js'; 

// A file can only contain one default and an unlimited amount of named exports.
// You can also mix the one default with any amount of named exports in one and the same file.
// When importing named exports, you can also import all named exports at once with the following syntax:
import * as upToYou from './path/to/file.js'; 

// `upToYou`  is - well - up to you and simply bundles all exported variables/functions in one JavaScript object.
// For example, if you export const someData = ...  (/path/to/file.js ) you can access it on upToYou  like this: upToYou.someData .


// Classes
// Classes are a feature which basically replace constructor functions and prototypes. You can define blueprints for JavaScript objects with them. 

// Like this:
class Person {
    constructor () {
        this.name = 'Max';
    }
}
 
const person = new Person();
console.log(person.name); // prints 'Max'

/* In the above example, not only the class but also a property of that class (=> name ) is defined. The syntax you see there, is the "old" syntax for defining properties. In modern JavaScript projects (as the one used in this course), you can use the following, more convenient way of defining class properties: */
class Person {
    name = 'Max';
}
 
const person = new Person();
console.log(person.name); // prints 'Max'

// You can also define methods. Either like this:
class Person {
    name = 'Max';
    printMyName () {
        console.log(this.name); // this is required to refer to the class!
    }
}
 
const person = new Person();
person.printMyName();

// Or like this:
class Person {
    name = 'Max';
    printMyName = () => {
        console.log(this.name);
    }
}
 
const person = new Person();
person.printMyName();

// The second approach has the same advantage as all arrow functions have: The this  keyword doesn't change its reference.

// You can also use inheritance when using classes:
class Human {
    species = 'human';
}
 
class Person extends Human {
    name = 'Max';
    printMyName = () => {
        console.log(this.name);
    }
}
 
const person = new Person();
person.printMyName();
console.log(person.species); // prints 'human'



// Spread & Rest Operator
// The spread and rest operators actually use the same syntax: `... `
// It's usage determines whether you're using it as the spread or rest operator.

// Using the Spread Operator:
// The spread operator allows you to pull elements out of an array (=> split the array into a list of its elements) or pull the properties out of an object. Here are two examples:

const oldArray = [1, 2, 3];
const newArray = [...oldArray, 4, 5]; // This now is [1, 2, 3, 4, 5];

// Here's the spread operator used on an object:
const oldObject = {
    name: 'Max'
};
const newObject = {
    ...oldObject,
    age: 28
};

// newObject  would then be
{
    name: 'Max',
    age: 28
}

/* The spread operator is extremely useful for cloning arrays and objects. Since both are reference types (and not primitives), copying them safely (i.e. preventing future mutation of the copied original) can be tricky. With the spread operator you have an easy way of creating a (shallow!) clone of the object or array.*/



// Destructuring
// Destructuring allows you to easily access the values of arrays or objects and assign them to variables.

// Here's an example for an array:

const array = [1, 2, 3];
const [a, b] = array;
console.log(a); // prints 1
console.log(b); // prints 2
console.log(array); // prints [1, 2, 3]


// And here for an object:
const myObj = {
    name: 'Max',
    age: 28
}
const {name} = myObj;
console.log(name); // prints 'Max'
console.log(age); // prints undefined
console.log(myObj); // prints {name: 'Max', age: 28}


// Destructuring is very useful when working with function arguments. Consider this example:
const printName = (personObj) => {
    console.log(personObj.name);
}
printName({name: 'Max', age: 28}); // prints 'Max'

// Here, we only want to print the name in the function but we pass a complete person object to the function.
// Of course this is no issue but it forces us to call personObj.name inside of our function.
// We can condense this code with destructuring:
const printName = ({name}) => {
    console.log(name);
}
printName({name: 'Max', age: 28}); // prints 'Max')

// We get the same result as above but we save some code.
// By destructuring, we simply pull out the name  property and store it in a variable/ argument named name  which we then can use in the function body.
```


#### JS Array Functions
```javascript
Particularly important in this course are:

map()  => https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map
find()  => https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/find
findIndex()  => https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/findIndex
filter()  => https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter
reduce()  => https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/Reduce?v=b
concat()  => https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/concat?v=b
slice()  => https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/slice
splice()  => https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/splice
```

<br>

---
<br>




# ◻ Section 3: React Essentials - Components, JSX, Props, State & more:

###  ◻ Coding Exercise 3 - Building & Using a Component
```javascript
// create a new MainGoal component which outputs a paragraph of text that describes your main course goal,
// and then use it inside the App component's JSX code.
import React from 'react';
// DEFINE YOUR COMPONENT HERE
export function MainGoal() {
    <p>My main goal: Become React expert</p>;
}

function App() {
  return (
    <div id="app">
      <h1>Time to Practice!</h1>
      <p>
        Build a <code>&lt;MainGoal&gt;</code> component and insert it below this
        text.
      </p>
      <p>
        Your <code>&lt;MainGoal&gt;</code> component should simply output some
        text that describes your main course goal (e.g., &quot;My main goal:
        Learn React in great detail&quot;).
      </p>
      <p>
        <strong>Important:</strong> You custom component must contain the text
        &quot;My main goal:&quot;
      </p>
      <p>
        <strong>Also important:</strong> For the automatic checks to succeed,
        you <strong>must export</strong> your custom component function! Not as
        a default but simply by adding the <code>export</code> keyword in front
        of your function (e.g., <code>export function YOUR_COMPONENT_NAME</code>
        ).
      </p>
      {/* OUTPUT YOUR COMPONENT HERE */}     
      <MainGoal />
    </div>
  );
}
export default App;
```


<br>

---
<br>

## ✔ Starting Project:
I build over the starting project with each module learned.
![3 React essential](https://github.com/shanibider/React-The-Complete-Guide-2024/assets/72359805/763a1d38-51bd-4cc5-afc1-1e86aa790778)


```javascript
// starting project
function App() {
  return (
    <div>
      <header>
        <img src="src/assets/react-core-concepts.png" alt="Stylized atom" />
        <h1>React Essentials</h1>
        <p>
          Fundamental React concepts you will need for almost any app you are
          going to build!
        </p>
      </header>
      <main>
        <h2>Time to get started!</h2>
      </main>
    </div>
  );
}
export default App;
```


###  ◻ Making Components Reusable with Props -
```javascript
/* 2. Merge into Object.
React merges all props into a single object.
{
   title= 'Components'
   description= 'The core UI...'
}
*/

// 3. Receive Props as an argument.
// Props are passed to the component function as the first argument by React.
// This object has this custom <key, value> pairs: { title: '...', description: '...', image: '...' }
function CoreConcept(props) {
  return (
    <li>
      {/* Can access props.image to get hold of the value that's set on the image key below */}
      <img src={props.image} alt={props.title} />
      <h3>{props.title}</h3>
      <p>{props.description}</p>
    </li>
  );
}

function App() {
  return (
    <div>
      {/* Rendering the Header component (can be reused) */}
      <Header />
      <main>
        <section id="core-concepts">
          <h2>Core Concepts</h2>
          <ul>
          {/* 1. Set props (can be: String, Number, Object, Array).
          Props are passed as an object, and are "custom HTML attributes" set on component. */}
            <CoreConcept
              title="Components"
              description="The core UI building block."
              image={componentsImg}
            />
            <CoreConcept title="Props" />
            <CoreConcept />
            <CoreConcept />
          </ul>
        </section>
      </main>
    </div>
  );
}
export default App;
```




##  ◻ Coding Exercise 4 - Outputting Dynamic Content:
```javascript
// the user's first name, last name and title is output dynamically by using JSX' "curly brace" syntax.
// For example, { userData.title } is replaced with the actual string value stored in userData.title
// when the component is rendered to the screen.
import React from 'react';

export const userData = {
  firstName: 'Shani', 
  lastName: 'Bider', 
  title: 'Developer',
};

// Edit the User component code to output the userData data
export function User() {
  return (
    <div id="user" data-testid="user">
      <h2>
     {userData.firstName} {userData.lastName}
      </h2>
      <p>{userData.title}</p>
    </div>
  );
}
// DON'T edit the App component code
function App() {
  return (
    <div id="app">
      <h1>Time to Practice</h1>
      <p>Welcome on board of this course! You got this 💪</p>
      <User/>
    </div>
  );
}
export default App;
```
![5](https://github.com/shanibider/React-The-Complete-Guide-2024/assets/72359805/887b4b01-ab98-4345-b08c-2e6911fdae32)





### ◻ Alternative Props Syntax:
```javascript
import { CORE_CONCEPTS } from './data.js';

// Using another js feature: object destructuring. By adding '{}', we can destructure the first parameter of this function.
// I can target the different properties of the incoming object by name (same properties as i set below)
function CoreConcept({ image, title, description }) {
  return (
    <li>
      <img src={image} alt={title} />
      <h3>{title}</h3>
      <p>{description}</p>
    </li>
  );
}

function App() {
  return (
    <div>
      <Header />
      <main>
        <section id="core-concepts">
          <h2>Core Concepts</h2>
          <ul>
            {/* Setting the props */}
            <CoreConcept
              title={CORE_CONCEPTS[0].title}
              description={CORE_CONCEPTS[0].description}
              image={CORE_CONCEPTS[0].image}
            />
            {/* Shortcut to pull out all the 'key,value' pairs of an object  */}
            <CoreConcept {...CORE_CONCEPTS[1]} />
            <CoreConcept {...CORE_CONCEPTS[2]} />
            <CoreConcept {...CORE_CONCEPTS[3]} />
          </ul>
        </section>
      </main>
    </div>
  );
}
export default App;

// data.js:
export const CORE_CONCEPTS = [
  {
    image: componentsImg,
    title: 'Components',
    description:
      'The core UI building block - compose the user interface by combining multiple components.',
  },
...];
```


##  ◻ Coding Exercise 5 - Working with props
```javascript
export function CourseGoal(props) {
  return (
    <li>
      <h2>{props.title}</h2>
      <p>{props.description}</p>
    </li>
  );
}

function App() {
  return (
    <div id="app" data-testid="app">
      <h1>Time to Practice</h1>
      <p>One course, many goals! 🎯</p>
      <ul>
        {/* OUTPUT AT LEAST TWO CourseGoal components here */}
        {/* One of them should have a title of “Learn React” and a description of “In-depth” */}
      <CourseGoal
      title="Learn React"
      description="In-depth"
      />
      <CourseGoal
      title="Practice React"
      description="Practice working with react"
      />
      </ul>
    </div>
  );
}
export default App;
```
![4](https://github.com/shanibider/React-The-Complete-Guide-2024/assets/72359805/ce2da105-bdab-44de-ada9-9e2625101f3c)



##  ◻ Quiz - Dynamic values and Props
- Which values can be output as dynamic values in JSX (i.e., between curly braces)?
    - You could output expressions like "1 + 1", variables / constants that hold values, the result of calling a function etc.

- How should you typically load / use images in React projects?
    - By "importing" the image, a production-safe path gets generated under the hood.

- How can you assign a dynamic value to an HTML element attribute?
    - You simply replace the text value you would normally set for attributes with the dynamic (curly-brace-wrapped) value.

- Which core React concept can increase the reusability of React components?
    - Props are essentially custom attributes that can be set on components.

- How do "props" work in React?
    - React automatically passes a props object as the first argument to the receiving component

- Which of the following four code examples for setting & extracting props would NOT work as intended?
I.e., which example will NOT output the text "Priority: 5" on the screen.

```javascript
<MyComponent priority={5} />
function MyComponent(priority) {
  return <p>Priority: {priority} </p>
```
The error is subtle but this example does NOT use object destructuring. So here, the "priority" prop is not pulled out of the props object. Instead, it's now the entire props object that's named "priority". This wouldn't be a problem since the name is up to you. But it's now the entire object that's output in the paragraph, not the "priority" property. Therefore, the output would not be "Priority: 5" but instead "Priority: [Object object]" (or something like that).


This will be correct answers:
```javascript
<MyComponent priority={5} />
function MyComponent({...props}) {
  return <p>Priority: {priority} </p>

<MyComponent priority={5} />
function MyComponent(props) {
  return <p>Priority: {priority} </p>

<MyComponent priority={5} />
function MyComponent({priority}) {
  return <p>Priority: {priority} </p>
```


### ◻ More props Syntax:
```javascript
import { CORE_CONCEPTS } from './data.js';
import Header from './components/Header.jsx';
import CoreConcept from './components/CoreConcept.jsx';

// Here I move all the components to their folder, and import them here 
function App() {
  return (
    <div>
      <Header />
      <main>
        <section id="core-concepts">
          <h2>Core Concepts</h2>
          <ul>
            <CoreConcept
              title={CORE_CONCEPTS[0].title}
              description={CORE_CONCEPTS[0].description}
              image={CORE_CONCEPTS[0].image}
            />
            <CoreConcept {...CORE_CONCEPTS[1]} />
            <CoreConcept {...CORE_CONCEPTS[2]} />
            <CoreConcept {...CORE_CONCEPTS[3]} />
          </ul>
        </section>
      </main>
    </div>
  );
}
export default App;
```


```javascript
// components/ CoreConcept
export default function CoreConcept({ image, title, description }) {
  return (
    <li>
      <img src={image} alt={title} />
      <h3>{title}</h3>
      <p>{description}</p>
    </li>
  );
}
```


```javascript
// components/ Header
import reactImg from '../assets/react-core-concepts.png';

const reactDescriptions = ['Fundamental', 'Crucial', 'Core'];

function genRandomInt(max) {
  return Math.floor(Math.random() * (max + 1));
}

export default function Header() {
  const description = reactDescriptions[genRandomInt(2)];

  return (
    <header>
      <img src={reactImg} alt="Stylized atom" />
      <h1>React Essentials</h1>
      <p>
        {description} React concepts you will need for almost any app you are
        going to build!
      </p>
    </header>
  );
}
```





### ◻ The special "children" prop 
```javascript
// children prop is used to pass the content to the component.
// This is a prop that set by react.
// This children prop is refer to the content between the opening and closing tags of the component.
// i can output that content by using {children} or {props.children} in the component.
// (i.e. <TabButton>Content</TabButton>)
export default function TabButton({ children }) { // here i use object destructuring to get the children properity
  return (
    <li>
      <button>{children}</button>
    </li>
  );
}
// same as:
export default function TabButton(props) {
  return (
    <li>
      <button>{props.children}</button>
    </li>
  );
}


// "Children" Props vs "Attribute Props"
// Using Attribute:
// for smaller pieces of information
<TabButton label="Components"></TabButton>

function TabButton({ label }) { 
  return <button>{label}</button>;
}

// Using Children:
// for a single piece of renderable content
<TabButton>Components</TabButton>

function TabButton({ children }) { 
  return <button>{children}</button>;
}
```






##  ◻ Coding Exercise 6 - Component Composition
Create a reusable Card component that takes a name prop as an input and, in addition, can be wrapped around any JSX code:
```javascript
import Card from './Card';

function App() {
  return (
    <div id="app">
      <h1>Available Experts</h1>
      <Card name="Anthony Blake">
        <p>
          Blake is a professor of Computer Science at the University of
          Illinois.
        </p>
        <p>
          <a href="mailto:blake@example.com">Email Anthony</a>
        </p>
      </Card>

      <Card name="Maria Miles">
        <p>
          Maria is a professor of Computer Science at the University of
          Illinois.
        </p>
        <p>
          <a href="mailto:blake@example.com">Email Maria</a>
        </p>
      </Card>
    </div>
  );
}
export default App;

// card.js
/* The children prop is a special prop that's automatically provided to every component function. It contains the wrapped content as a value.
    So the children prop's value for this code:
    <Card>
      <p>Hi there</p>
    </Card>
    would be <p>Hi there</p>.
*/

export default function Card({ name, children }) {
    return (
        <article className="card">
        <h2>{name}</h2>
        {children}
        </article>
    );
}


// index.css
@import url('https://fonts.googleapis.com/css2?family=Raleway:wght@400;700&family=Lato:wght@400;700&display=swap');
* {
  box-sizing: border-box;
}
body {
  margin: 0;
  font-family: 'Raleway', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  background: linear-gradient(#dfdee0, #c3c3c4);
  color: #e5d9f1;
  min-height: 100vh;
}
.card {
  margin: 2rem auto;
  padding: 2rem;
  max-width: 30rem;
  border-radius: 6px;
  background: linear-gradient(#254041, #203031);
  box-shadow: 0 0 8px rgba(0,0,0,0.3);
}
.card h2 {
  margin: 0;
  font-family: 'Lato', sans-serif;
  font-weight: bold;
  font-size: 1.5rem;
  color: #e5d9f1;
}
.card p {
  margin: 0.5rem 0;
}
.card a {
  color: #b3f4f6;
  text-decoration: none;
}
```      
![3](https://github.com/shanibider/React-The-Complete-Guide-2024/assets/72359805/f0a3487f-bb42-4b31-b75c-cd27c8d5c871)




###  ◻ Coding Exercise 7 - Racting to Event
```javascript
// Your goal is to change the email, password and loggedIn values when the button in the App component is pressed
// Change them to any values of your choice (except loggedIn => that should be changed to true)
// You DON'T need to fetch the values entered into the <input /> fields
// You'll learn about that later in the course - for the moment, those fields are just there to look good :-)
export const user = {
  email: '',
  password: '',
  loggedIn: false,
};

function handleLogin(){
   user.email = 'test@example.com';
   user.password = 'test';
   user.loggedIn = true;
}

// Please note: The login does not actually work!
// This exercise is just about practicing event handling
// You'll learn how to add user authentication to React apps later in the course!
function App() {
  return (
    <div id="app">
      <h1>User Login</h1>
      <p>
        <label>Email</label>
        {/* You don't need to do anything with those inputs! You'll learn how to handle user input later */}
        <input type="email" />
      </p>

      <p>
        <label>Password</label>
        {/* You don't need to do anything with those inputs! You'll learn how to handle user input later */}
        <input type="password" />
      </p>

      <p id="actions">
        <button onClick={handleLogin}>Login</button>
      </p>
    </div>
  );
}
export default App;
```

![7](https://github.com/shanibider/React-The-Complete-Guide-2024/assets/72359805/97349991-51de-4aad-bae6-681cb3a8cbc3)






###  ◻ Coding Exercise 8 - Event Handlers
```javascript
export const user = {
  name: '',
};

function App() {
  // Your goal: This function should be called WITH A VALUE for name when the <button> is clicked
  function handleCreateUser(name) {
    user.name = name;
  }

  return (
    <div id="app">
      <h1>User Login</h1>
      <p>
        <label>Name</label>
        {/* You don't need to do anything with this input! You'll learn how to handle user input later */}
        <input type="text" />
      </p>

      <p id="actions">
        <button onClick={ () => handleCreateUser('Shani') }>Create User</button>
      </p>
    </div>
  );
}
export default App;
```

![8](https://github.com/shanibider/React-The-Complete-Guide-2024/assets/72359805/6fc6c78b-b1fc-4869-a2e9-abadc6da9091)


##  ◻ Quiz - Event Handling
- How should you typically store your component functions?
Split across multiple files. (One component per file).

- What's the purpose of the special "children" prop?
"children" will receive whichever content you pass between the opening and closing tags of your component.

- How can you handle user events in React projects?
Via the built-in 'onXYZ' props (e.g. onClick).

- To execute code upon events, which value must be passed to event props like onClick?
A pointer to the function that sould be executed (onClick={handleClick}).

- How can you "configure" the execution of an event-dependent function (e.g., define which arguments get passed to it)?
By wrapping the execution of your event handling function with another function, it's that other function that's passed as a value to the event-handling prop. Therefore, your main function (=> handleClick in this example) does NOT get executed too early but instead only when the event occurs. (onClick = { () => handleClick(5)}).









































































<br>

---
<br>


### ◻ Codesandbox Coding Exercise:
#### [👉🏻 First React App](https://codesandbox.io/p/sandbox/first-react-app-zj5cx1?file=%2Fsrc%2FApp.js)

![2](https://github.com/shanibider/React-The-Complete-Guide-2024/assets/72359805/61e6dca9-117e-4f99-8772-48739fde954f)

```javascript
import { useState } from "react";
import "./styles.css";

const content = [
  [
    "React is extremely popular",
    "It makes building complex, interactive UIs a breeze",
    "It's powerful & flexible",
    "It has a very active and versatile ecosystem"
  ],
  [
    "Components, JSX & Props",
    "State",
    "Hooks (e.g., useEffect())",
    "Dynamic rendering"
  ],
  [
    "Official web page (react.dev)",
    "Next.js (Fullstack framework)",
    "React Native (build native mobile apps with React)"
  ],
  [
    "Vanilla JavaScript requires imperative programming",
    "Imperative Programming: You define all the steps needed to achieve a result",
    "React on the other hand embraces declarative programming",
    "With React, you define the goal and React figures out how to get there"
  ]
];

export default function App() {
  const [activeContentIndex, setActiveContentIndex] = useState(0);

  return (
    <div>
      <header>
        <img src="react-logo-xs.png" alt="React logo" />
        <div>
          <h1>React.js</h1>
          <p>i.e., using the React library for rendering the UI</p>
        </div>
      </header>

      <div id="tabs">
        <menu>
          <button
            className={activeContentIndex === 0 ? "active" : ""}
            onClick={() => setActiveContentIndex(0)}
          >
            Why React?
          </button>
          <button
            className={activeContentIndex === 1 ? "active" : ""}
            onClick={() => setActiveContentIndex(1)}
          >
            Core Features
          </button>
          <button
            className={activeContentIndex === 2 ? "active" : ""}
            onClick={() => setActiveContentIndex(2)}
          >
            Related Resources
          </button>
          <button
            className={activeContentIndex === 3 ? "active" : ""}
            onClick={() => setActiveContentIndex(3)}
          >
            React vs JS
          </button>
        </menu>
        <div id="tab-content">
          <ul>
            {content[activeContentIndex].map((item) => (
              <li key={item}>{item}</li>
            ))}
          </ul>
        </div>
      </div>
    </div>
  );
}
```

```css
* {
  box-sizing: border-box;
}

body {
  font-family: sans-serif;
  background-color: #181c1f;
  color: #bdd1d4;
  margin: 2rem;
}

header {
  margin: 2rem 0;
  display: flex;
  gap: 1.5rem;
  align-items: center;
}

header img {
  width: 3rem;
  object-fit: contain;
}

header h1 {
  margin: 0;
  color: #48d9f3;
}

header p {
  margin: 0;
  color: #82c2ce;
}

#tabs {
  max-width: 32rem;
  margin: 2rem 0;
  overflow: hidden;
}

#tabs menu {
  margin: 0;
  padding: 0;
  display: flex;
  gap: 0.25rem;
}

#tabs button {
  font: inherit;
  font-size: 0.85rem;
  background-color: #282f33;
  border: none;
  border-bottom-color: #48d9f3;
  color: #e0eff1;
  border-radius: 4px 4px 0 0;
  padding: 0.75rem 1rem;
  cursor: pointer;
  transition: all 0.2s ease-out;
}

#tabs button:hover,
#tabs button.active {
  background-color: #48d9f3;
  color: #273133;
}

#tab-content {
  background-color: #2d3942;
  border-radius: 0 4px 4px 4px;
  padding: 1rem;
}

#tab-content li {
  margin: 0.75rem 0;
}
```

<br>

---
<br>


## 🥇What I've Learned 
<img height=40px src="https://skillicons.dev/icons?i=react"> <img height=40px src="https://skillicons.dev/icons?i=js"> <img height=40px src="https://skillicons.dev/icons?i=nextjs"> <img height=40px src="https://skillicons.dev/icons?i=redux">

- [x] Mastered `React` from the ground up
- [x] Built multiple high-quality demo apps
- [x] Managed `complex state` efficiently with `React's Context API` & `Redux`
- [x] Implemented `user authentication`
- [x] Gained experience with `React Unit Testing`


## 🎯 Key Topics Covered 

- [x] Introduction to `React.js`
- [x] All the `core basics`: How React works, building components with React & building UIs with React
- [x] Building `components`, working with `props` & dynamic `data binding`
- [x] `React Hooks (in-depth)`
- [x] Working with built-in Hooks and building custom Hooks
- [x] `Styling React` apps with "Styled Components" and "CSS Modules"
- [x] Working with "Fragments" & "Portals"
- [x] Dealing with side effects
- [x] `Class-based components` and `functional components`
- [x] Sending `Http requests` & handling transitional `states + responses`
- [x] Handling `forms` and `user input` (incl. validation)
- [x] `Redux` & Redux Toolkit
- [x] `Routing` with React Router
-[x]  An in-depth introduction into `Next.js`
- [x] `Deploying` React Apps
- [x] Implementing `Authentication`
- [x] `Unit Tests`
- [x] Combining React with TypeScript
- [x] Adding Animations
<br>

---
<br>




> [!TIP]
> Feel free to explore my repositories and see my projects. I'm always open to collaboration and welcome feedback to improve and grow as a developer. Let's code something amazing together! 🚀😊👩‍💻💻


## 📫 Connect with me 😊
[![linkedin](https://img.shields.io/badge/linkedin-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/shani-bider/)
[![portfolio](https://img.shields.io/badge/my_portfolio-000?style=for-the-badge&logo=ko-fi&logoColor=white)](https://shanibider.github.io/Portfolio/)
[![gmail](https://img.shields.io/badge/Gmail-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:shanibider@gmail.com)

<footer>
<p style="float:left; width: 20%;">
Copyright © Shani Bider, 2024
</p>
</footer>
