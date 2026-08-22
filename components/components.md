
Haan 👍 Agar tum GitHub par React + JavaScript Interview Notes ka proper repository banana chahte ho, to notes ko usi structure ke according rakhna better hai.

Tumhare recent topics ke hisaab se structure aisa rakho:

Frontend-Interview-Notes/
│
├── README.md
│
├── JavaScript/
│   ├── 01-Variables.md
│   ├── 02-Data-Types.md
│   ├── 03-Functions.md
│   ├── 04-Scope.md
│   ├── 05-Hoisting.md
│   ├── 06-Array-Methods.md
│   ├── 07-Destructuring.md
│   ├── 08-Spread-Operator.md
│   ├── 09-Rest-Operator.md
│   └── 10-ES6-Features.md
│
└── React/
    ├── 01-Components.md
    ├── 02-Props.md
    ├── 03-State.md
    ├── 04-Events.md
    ├── 05-Conditional-Rendering.md
    ├── 06-Lists-and-Keys.md
    ├── 07-Forms.md
    ├── 08-Hooks.md
    ├── 09-useState.md
    ├── 10-useEffect.md
    ├── 11-useContext.md
    ├── 12-useRef.md
    └── 13-React-Router.md
Abhi jo Components wala note hai
Iska naam rakho:

React/01-Components.md
Aur GitHub par ye sequence maintain karo:

JavaScript

Variables

Data Types

Functions

Scope

Hoisting

Array Methods

Destructuring

Spread

Rest

ES6 Features

React

Components

Props

State

Events

Conditional Rendering

Lists & Keys

Forms

Hooks

useState

useEffect

useContext

useRef

React Router

Is tarah tumhara GitHub random notes ka collection nahi, balki proper Frontend Interview Preparation Repository lagega.


componets noted do

Bilkul. GitHub ke liye React/01-Components.md me ye notes rakho:

# React Components

## 1. What is a Component?

A **Component** is a reusable and independent piece of UI in React.

Examples:

- Navbar
- Button
- Card
- Login Form
- Sidebar
- Footer

### Example

```jsx
function Header() {
  return <h1>My Website</h1>;
}
Here, Header is a React Component.

Use it like:

function App() {
  return (
    <div>
      <Header />
    </div>
  );
}
2. Types of Components
React me mainly two types ke components hote hain:

Functional Component

Class Component

3. Functional Component
Functional Component ek normal JavaScript function hota hai jo JSX return karta hai.

function Welcome() {
  return <h1>Hello Ritesh</h1>;
}
Arrow Function
const Welcome = () => {
  return <h1>Hello Ritesh</h1>;
};
Modern React applications me Functional Components mostly use hote hain.

4. Class Component
Class Components React ke older applications me commonly use hote the.

class Welcome extends React.Component {
  render() {
    return <h1>Hello Ritesh</h1>;
  }
}
Modern React me Functional Components + Hooks preferred hain.

5. Why do we use Components?
Components ke main benefits:

Reusability

Maintainability

Readability

Separation of concerns

Easy testing

Example:

function Button() {
  return <button>Login</button>;
}
Ab same component ko multiple places par use kar sakte hain:

<Button />
<Button />
<Button />
6. Component Naming
Component ka naam generally Capital Letter se start hona chahiye.

Correct
function Header() {
  return <h1>Header</h1>;
}
Incorrect
function header() {
  return <h1>Header</h1>;
}
React capitalization se user-defined components aur HTML elements ko distinguish karta hai.

7. JSX in Components
Components usually JSX return karte hain.

function User() {
  return (
    <div>
      <h2>Ritesh</h2>
      <p>Full Stack Developer</p>
    </div>
  );
}
JSX JavaScript ke andar HTML-like syntax likhne deta hai.

8. Reusable Components
Component ka main advantage hai ki same UI ko multiple times reuse kar sakte hain.

function UserCard() {
  return (
    <div>
      <h2>User</h2>
      <button>View</button>
    </div>
  );
}
Use:

<UserCard />
<UserCard />
<UserCard />
Same component multiple times use ho raha hai.

Props in Components
9. What are Props?
Props = Properties

Props ka use parent component se child component ko data bhejne ke liye hota hai.

function User({ name }) {
  return <h2>Hello {name}</h2>;
}
Parent component:

function App() {
  return <User name="Ritesh" />;
}
Output:

Hello Ritesh
Here:

name="Ritesh"
is a prop.

10. Multiple Props
function User({ name, age, city }) {
  return (
    <div>
      <h2>{name}</h2>
      <p>{age}</p>
      <p>{city}</p>
    </div>
  );
}
Use:

<User
  name="Ritesh"
  age={22}
  city="Delhi"
/>
11. Props are Read-Only
Props ko child component directly modify nahi kar sakta.

function User({ name }) {
  // Don't do this
  // name = "Rahul";

  return <h2>{name}</h2>;
}
Props are read-only.

State in Components
12. What is State?
State component ka internal data hota hai jo time ke saath change ho sakta hai.

React me state manage karne ke liye useState use karte hain.

import { useState } from "react";

function Counter() {
  const [count, setCount] = useState(0);

  return (
    <div>
      <h2>{count}</h2>

      <button onClick={() => setCount(count + 1)}>
        Increase
      </button>
    </div>
  );
}
Here:

count
Current state hai.

setCount
State update karne ka function hai.

useState(0)
Initial value 0 hai.

Props vs State
13. Difference Between Props and State
Props	State
Parent se data aata hai	Component ka internal data
Read-only hota hai	Update ho sakta hai
Parent → Child data passing	Dynamic data manage karne ke liye
Child directly modify nahi karta	Setter function se update hota hai
Example of Props:

<User name="Ritesh" />
Example of State:

const [count, setCount] = useState(0);
Parent and Child Components
14. Parent to Child Communication
Props ke through parent se child ko data bhejte hain.

function Parent() {
  return <Child name="Ritesh" />;
}

function Child({ name }) {
  return <h2>Hello {name}</h2>;
}
Flow:

Parent
   ↓
Props
   ↓
Child
15. Child to Parent Communication
Child directly parent ki state ko modify nahi karta.

Parent ek function child ko prop ke through deta hai.

function Parent() {
  const handleMessage = (message) => {
    console.log(message);
  };

  return <Child sendMessage={handleMessage} />;
}

function Child({ sendMessage }) {
  return (
    <button onClick={() => sendMessage("Hello Parent")}>
      Send
    </button>
  );
}
Flow:

Parent
   ↓
Function as Prop
   ↓
Child
   ↓
Function Call
   ↓
Parent
Component Composition
16. What is Component Composition?
Ek component ke andar doosre components ko use karna Component Composition kehlata hai.

function Navbar() {
  return <nav>Navbar</nav>;
}

function Footer() {
  return <footer>Footer</footer>;
}

function App() {
  return (
    <>
      <Navbar />
      <main>Content</main>
      <Footer />
    </>
  );
}
Here:

App
 ├── Navbar
 └── Footer
Conditional Rendering
17. Conditional Rendering
Condition ke according UI render karna Conditional Rendering hai.

function User({ isLoggedIn }) {
  return (
    <div>
      {isLoggedIn ? (
        <h2>Welcome User</h2>
      ) : (
        <h2>Please Login</h2>
      )}
    </div>
  );
}
Lists and Keys
18. Rendering Lists
Array ke data ko render karne ke liye map() use karte hain.

function Users() {
  const users = ["Ritesh", "Rahul", "Aman"];

  return (
    <ul>
      {users.map((user) => (
        <li key={user}>{user}</li>
      ))}
    </ul>
  );
}
19. Why is key used?
key React ko identify karne me help karta hai ki list me kaunsa item:

Add hua

Remove hua

Update hua

Reorder hua

Example:

{users.map((user) => (
  <li key={user}>{user}</li>
))}
Controlled Component
20. What is a Controlled Component?
Jab form input ki value React state se control hoti hai, use Controlled Component kehte hain.

import { useState } from "react";

function Form() {
  const [name, setName] = useState("");

  return (
    <input
      value={name}
      onChange={(e) => setName(e.target.value)}
    />
  );
}
Here React state input ki value ko control kar rahi hai.

Component Lifecycle
21. Component Lifecycle
Component ki basic lifecycle stages:

Mount
  ↓
Update
  ↓
Unmount
Mount
Component first time DOM me render hota hai.

Update
Props ya state change hone par component re-render ho sakta hai.

Unmount
Component DOM se remove ho jata hai.

Functional Components me lifecycle-related behavior ke liye Hooks, especially useEffect, use kiya jata hai.

Component File Structure
22. Recommended Folder Structure
src/
│
├── components/
│   ├── Navbar.jsx
│   ├── Button.jsx
│   ├── Card.jsx
│   └── Footer.jsx
│
├── pages/
│   ├── Home.jsx
│   ├── Login.jsx
│   └── Dashboard.jsx
│
└── App.jsx
Components folder me reusable UI components rakh sakte hain.

Component vs Element
23. Component vs React Element
Component
function Button() {
  return <button>Click</button>;
}
Button ek component hai.

Element
<Button />
<Button /> ek React element hai jo Button component ko represent karta hai.

Important Interview Questions
Q1. What is a React Component?
Answer:

A React Component is a reusable and independent piece of UI that returns JSX and can receive data through props and manage data using state.

Q2. What are the types of React Components?
Answer:

Mainly two types:

Functional Components

Class Components

Modern React mostly uses Functional Components with Hooks.

Q3. What are Props?
Answer:

Props are read-only inputs passed from a parent component to a child component.

Q4. Can we modify Props?
Answer:

No. Props are read-only. If data needs to change, we generally use state.

Q5. What is State?
Answer:

State is data managed inside a component that can change over time and cause the component to re-render.

Q6. Props vs State?
Answer:

Props are passed from parent to child and are read-only, while state is managed inside a component and can be updated.

Q7. How do you pass data from Parent to Child?
Answer:

Using props.

<Child name="Ritesh" />
Q8. How do you communicate from Child to Parent?
Answer:

By passing a callback function from the parent to the child as a prop.

Q9. Why should component names start with a capital letter?
Answer:

React uses capitalization to distinguish user-defined components from built-in HTML elements.

Q10. Why are keys used in React lists?
Answer:

Keys help React identify list items efficiently when items are added, removed, or reordered.

Quick Revision
Component
   ↓
Reusable UI

Props
   ↓
Parent → Child Data

State
   ↓
Component's Dynamic Data

Callback Props
   ↓
Child → Parent Communication

useState
   ↓
Manage State

useEffect
   ↓
Side Effects

map()
   ↓
Render Lists

key
   ↓
Identify List Items
One-Line Interview Definition
A React Component is a reusable and independent piece of UI that accepts data through props, can manage state, and returns JSX describing what should be rendered.


**GitHub path:**

```text
Frontend-Interview-Notes/
└── React/
    └── 01-Components.md
Is format me rakho, phir next 02-Props.md se continue kar sakte ho.


md file me

Ye lo proper GitHub folder structure ke according .md file:

Download 01-Components.md

GitHub me ise yahan rakho:

Frontend-Interview-Notes/
└── React/
    └── 01-Components.md



01-Components.md
Document

Chat paused until usage resets at 3:38 PM
You’ve reached the limit for chats that include data analysis. Start a new text-only chat or upgrade to continue now.

New chat

Upgrade

01-Components.md


React Components
1. What is a Component?
A Component is a reusable and independent piece of UI in React.

Examples:

Navbar

Button

Card

Login Form

Sidebar

Footer

Example
function Header() {
  return <h1>My Website</h1>;
}
Here, Header is a React Component.

Use it:

function App() {
  return (
    <div>
      <Header />
    </div>
  );
}
2. Types of Components
React me mainly two types ke components hote hain:

Functional Component

Class Component

3. Functional Component
Functional Component ek normal JavaScript function hota hai jo JSX return karta hai.

function Welcome() {
  return <h1>Hello Ritesh</h1>;
}
Arrow Function
const Welcome = () => {
  return <h1>Hello Ritesh</h1>;
};
Modern React applications me Functional Components mostly use hote hain.

4. Class Component
Class Components React ke older applications me commonly use hote the.

class Welcome extends React.Component {
  render() {
    return <h1>Hello Ritesh</h1>;
  }
}
Modern React me Functional Components + Hooks preferred hain.

5. Why do we use Components?
Components ke main benefits:

Reusability

Maintainability

Readability

Separation of concerns

Easy testing

Example:

function Button() {
  return <button>Login</button>;
}
Same component multiple times use kar sakte hain:

<Button />
<Button />
<Button />
6. Component Naming
Component ka naam generally Capital Letter se start hona chahiye.

Correct
function Header() {
  return <h1>Header</h1>;
}
Incorrect
function header() {
  return <h1>Header</h1>;
}
React capitalization se user-defined components aur HTML elements ko distinguish karta hai.

Props in Components
7. What are Props?
Props = Properties

Props ka use parent component se child component ko data bhejne ke liye hota hai.

function User({ name }) {
  return <h2>Hello {name}</h2>;
}
Parent:

function App() {
  return <User name="Ritesh" />;
}
Output:

Hello Ritesh
Here name ek prop hai.

Important
Props are read-only.

Child component directly props ko modify nahi karta.

State in Components
8. What is State?
State component ka internal data hota hai jo change ho sakta hai.

React me state ke liye useState hook use karte hain.

import { useState } from "react";

function Counter() {
  const [count, setCount] = useState(0);

  return (
    <div>
      <h2>{count}</h2>

      <button onClick={() => setCount(count + 1)}>
        Increase
      </button>
    </div>
  );
}
Here:

count = current state

setCount = state update function

useState(0) = initial value

Props vs State
9. Difference Between Props and State
Props	State
Parent se data aata hai	Component ka internal data
Read-only hota hai	Update ho sakta hai
Parent → Child data passing	Dynamic data manage karne ke liye
Child directly modify nahi karta	Setter function se update hota hai
Parent and Child Components
10. Parent to Child Communication
Props ke through parent se child ko data bhejte hain.

function Parent() {
  return <Child name="Ritesh" />;
}

function Child({ name }) {
  return <h2>Hello {name}</h2>;
}
Flow:

Parent
   ↓
Props
   ↓
Child
11. Child to Parent Communication
Child directly parent ki state ko modify nahi karta.

Parent ek function child ko prop ke through deta hai.

function Parent() {
  const handleMessage = (message) => {
    console.log(message);
  };

  return <Child sendMessage={handleMessage} />;
}

function Child({ sendMessage }) {
  return (
    <button onClick={() => sendMessage("Hello Parent")}>
      Send
    </button>
  );
}
Flow:

Parent
   ↓
Function as Prop
   ↓
Child
   ↓
Function Call
   ↓
Parent
Component Composition
12. What is Component Composition?
Ek component ke andar doosre components ko use karna Component Composition kehlata hai.

function Navbar() {
  return <nav>Navbar</nav>;
}

function Footer() {
  return <footer>Footer</footer>;
}

function App() {
  return (
    <>
      <Navbar />
      <main>Content</main>
      <Footer />
    </>
  );
}
Conditional Rendering
13. Conditional Rendering
Condition ke according UI render karna Conditional Rendering hai.

function User({ isLoggedIn }) {
  return (
    <div>
      {isLoggedIn ? (
        <h2>Welcome User</h2>
      ) : (
        <h2>Please Login</h2>
      )}
    </div>
  );
}
Lists and Keys
14. Rendering Lists
Array ke data ko render karne ke liye map() use karte hain.

function Users() {
  const users = ["Ritesh", "Rahul", "Aman"];

  return (
    <ul>
      {users.map((user) => (
        <li key={user}>{user}</li>
      ))}
    </ul>
  );
}
15. Why is key used?
key React ko identify karne me help karta hai ki list me kaunsa item add, remove, update ya reorder hua.

{users.map((user) => (
  <li key={user}>{user}</li>
))}
Controlled Component
16. What is a Controlled Component?
Jab form input ki value React state se control hoti hai, use Controlled Component kehte hain.

import { useState } from "react";

function Form() {
  const [name, setName] = useState("");

  return (
    <input
      value={name}
      onChange={(e) => setName(e.target.value)}
    />
  );
}
Component Lifecycle
17. Component Lifecycle
Component ki basic lifecycle stages:

Mount
  ↓
Update
  ↓
Unmount
Mount
Component first time render hota hai.

Update
Props ya state change hone par component re-render ho sakta hai.

Unmount
Component DOM se remove ho jata hai.

Functional Components me lifecycle-related behavior ke liye Hooks, especially useEffect, use kiya jata hai.

Component File Structure
18. Recommended Folder Structure
src/
│
├── components/
│   ├── Navbar.jsx
│   ├── Button.jsx
│   ├── Card.jsx
│   └── Footer.jsx
│
├── pages/
│   ├── Home.jsx
│   ├── Login.jsx
│   └── Dashboard.jsx
│
└── App.jsx
Component vs Element
19. Component vs React Element
Component
function Button() {
  return <button>Click</button>;
}
Button ek component hai.

Element
<Button />
<Button /> ek React element hai jo Button component ko represent karta hai.

Important Interview Questions
Q1. What is a React Component?
Answer:

A React Component is a reusable and independent piece of UI that returns JSX and can receive data through props and manage data using state.

Q2. What are the types of React Components?
Answer:

Mainly two types:

Functional Components

Class Components

Modern React mostly uses Functional Components with Hooks.

Q3. What are Props?
Answer:

Props are read-only inputs passed from a parent component to a child component.

Q4. Can we modify Props?
Answer:

No. Props are read-only. If data needs to change, we generally use state.

Q5. What is State?
Answer:

State is data managed inside a component that can change over time and cause the component to re-render.

Q6. Props vs State?
Answer:

Props are passed from parent to child and are read-only, while state is managed inside a component and can be updated.

Q7. How do you pass data from Parent to Child?
Answer:

Using props.

<Child name="Ritesh" />
Q8. How do you communicate from Child to Parent?
Answer:

By passing a callback function from the parent to the child as a prop.

Q9. Why should component names start with a capital letter?
Answer:

React uses capitalization to distinguish user-defined components from built-in HTML elements.

Q10. Why are keys used in React lists?
Answer:

Keys help React identify list items efficiently when items are added, removed, or reordered.

Quick Revision
Component
   ↓
Reusable UI

Props
   ↓
Parent → Child Data

State
   ↓
Component's Dynamic Data

Callback Props
   ↓
Child → Parent Communication

useState
   ↓
Manage State

useEffect
   ↓
Side Effects

map()
   ↓
Render Lists

key
   ↓
Identify List Items
One-Line Interview Definition
A React Component is a reusable and independent piece of UI that accepts data through props, can manage state, and returns JSX describing what should be rendered.

