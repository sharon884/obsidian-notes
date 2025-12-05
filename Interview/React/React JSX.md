
JSX stands for JavaScript XML, and it is a special syntax used in React to simplify building user interfaces. JSX allows you to write HTML-like code directly inside JavaScript, enabling you to create UI components more efficiently. Although JSX looks like regular HTML, it’s actually a syntax extension for JavaScript.

![react_jsx-1](https://media.geeksforgeeks.org/wp-content/uploads/20250813142958772966/react_jsx-1.webp)


How JSX Works

When React processes this JSX code, it converts it into JavaScript using Babel. This JavaScript code then creates real HTML elements in the browser’s DOM . which is how your web page gets displayed.


> Note: Babel acts as a ****translator**** for your React code. It takes modern JavaScript (like JSX) that browsers don't understand directly. Finally, it converts it into older, compatible JavaScript so your application runs everywhere.



## Uses of JSX

Here are some significant uses of JSX:

### 1. Embedding Expressions

JSX allows you to embed [JavaScript](https://www.geeksforgeeks.org/javascript/javascript-tutorial/) expressions directly within the HTML-like syntax. You can use curly braces {} to insert JavaScript expressions.

`const name = 'Jonny'; const greeting = <h1>Hello, {name}!</h1>;`

****In this code****

- {name} in JSX dynamically inserts the value of the name variable into the rendered output.

### ****2. Using Attributes in JSX****

In JSX, attributes are specified similarly to [HTML](https://www.geeksforgeeks.org/html/html-tutorial/), but with some differences. Since JavaScript is used alongside JSX, certain attribute names are written in camelCase instead of the lowercase syntax used in HTML.

`const element = <img src="" alt="A description" />;`

- CamelCase for Attribute Names: In JSX, some HTML attributes are written in camelCase.
- For example, class becomes className, for becomes htmlFor, and style is an object. This is because class and for are reserved words in JavaScript.

### 3. Passing Children in JSX

In JSX, components or elements can accept children just like HTML elements. Children are nested elements or content that are passed into a component. This allows for flexible and reusable components.

`const Welcome = (props) => {   return <div>{props.children}</div>; };  const App = () => {   return (     <Welcome>       <h1>Hello, World!</h1>       <p>Welcome to React.</p>     </Welcome>   ); };`

****In this code****

- ****Children as Props:**** The Welcome component does not explicitly define the content inside it. Instead, it uses {props.children} to render any child elements that are passed between the opening and closing tags of the component when it is used.
- ****Flexibility:**** The App component passes two child elements (<h1> and <p>) to Welcome. By using {props.children}, the Welcome component can render any child content, making it reusable with different content each time it’s used.

4. JSX Represents Objects

[JSX](https://www.geeksforgeeks.org/reactjs/reactjs-jsx-introduction/) is not directly rendered as HTML by React; instead, it gets compiled into JavaScript objects representing [virtual DOM](https://www.geeksforgeeks.org/reactjs/reactjs-virtual-dom/) elements. These objects are later used by React to efficiently update the real DOM.

`const element = React.createElement(   "button",   {     className: "btn",     onClick: () => alert("Clicked!"),   },   "Click Me" );`

The JSX code is converted into a JavaScript object

{

  type: 'button',                 

  props: {                        

    className: 'btn',             

    onClick: () => alert('Clicked!'), 

    children: ['Click Me']        

  }

}

****In this code****

- type: 'button': Defines the element type (button).
- props: Contains attributes like:
- className: 'btn': For styling.
- onClick: () => alert('Clicked!'): Event handler for click.
- children: ['Click Me']: Content inside the button.
- React converts JSX into a JavaScript object to efficiently render and manage the UI.