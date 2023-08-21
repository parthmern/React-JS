# React-JS

## ❤️ What is React ?
➔ Js library used to create UI <br/>
➔ library = A programming library is a collection of prewritten code that programmers can use to optimize tasks ( in C lang we use the pow(a,b) pre-defined function with using stdlib.h library  <br/>
<br/>
➔ React is all about components so it is component based architecture <br/>

➖➖➖➖➖➖➖➖➖➖➖➖➖➖➖

## 💙 Why we need React ?
➔ JS is based on imparative approach <br/> 
➔ React is based on declarative approach <br/>
<br/>
➔ imparative approach means line by line <br/>
➔ declarative approach means we 
 <br/>
➔ SPA ( single page application ) approach (like netflix ) <br/>
➔ Development is faster than vanilla JS <br/>
<br/>
➔ React alternatives = angularJs , vueJs <br/>
<br/>
1) reusablity (using components)
2) DRY (do not repeate yourself)
3) readability
4) SOC(seperation of concern)
5) maintainability

➖➖➖➖➖➖➖➖➖➖➖➖➖➖➖
 
## 💜 Comopnent
➔ a piece of code that used multiple times - reusable piece of code <br/>
➔ ( like custom html element that we can use multiple times ) <br/>
➔ same work as Function ( create js file and write function )

➖➖➖➖➖➖➖➖➖➖➖➖➖➖➖

## 💛 Installation 
➔ Install node js ( [link](https://youtu.be/mIW_8dMQaUk) and check `node -v` and `npm -v` ) <br/>
➔ Vs code <br/>
<br/>
➔ React installation ( [vidLink]( ) )<br/>
➔ if above is not working then [try this](https://youtu.be/tg73NsiQOUE) <br/>

➖➖➖➖➖➖➖➖➖➖➖➖➖➖➖

## 💙 Direct starter pack

[startert pack](https://github.com/thepranaygupta/react-tailwind-css-starter-pack)  <br/>

➔ package.json = dependencies/version/scripts are avialabe here <br/>
➔ src folder <br/>
src > index.js = first file that excecutes when page load / entry point of js = here react creates 'root' that fetch from index.html <br/>
src > index.css <br/> = file that contains css for index.js file
src > app.js or app.jsx <br/>
➔ public folder  <br/>
public > index.html = contains 'root'   <br/>
➔ nodeModules folder  <br/>

⚠️ firstly excecutes `index.js` file then it goes to `index.html` file to get the `<root>` div and it converts rootDiv to react-root and then it render `<App>` from `App.js` or `App.jsx` and here `App.js` contains html code <br/>

➖➖➖➖➖➖➖➖➖➖➖➖➖➖➖ <br/>
➖➖➖➖➖➖➖➖➖➖➖➖➖➖➖

## 💚 Create Component

✔️ ➔ first create `components` folder in src  <br/>
✔️ ➔ then src > components then create `Item.js` and `Item.css` <br/>
✔️ ➔ `Item.js` looks like <br/>

```
import './Item.css' ;      //here first import .css file

function Item()            //then create function that returns Html code
{
  return(

    // html codes
    <p className="parth"> hello </p>

  );
}

export default Item ;      //then export the function that we can use in App.js

```
*here in `Item.js` we are actually writing JSX (JavaScrpit XML means JS with Html code) code so we cannot define html element class directly because js already have predefined class component so here in jsx we have to use `className='xxxxx'` except `class='xxxxx'`*

━━━━━━━━━━<br/>

✔️ ➔ `Item.css` looks like <br/>
```
.parth
{
  text-align: center;
  background-color: aqua;
}

// same as actual css
```
━━━━━━━━━━<br/>
<br/>

✔️ ➔ use of component in `App.js` file

```
import Item from './components/Item' ;        // here we are importing Item from `Item.js`
                                              //  components > Item(exported)

function App()
{
  return(

    // html codes
    // using Item componenet
    <Item> </Item>

  );                            
}

export default App;                           // exporting `App.js` because we have to use this in `index.js` the first entry point

```

━━━━━━━━━━<br/>
<br/>

✔️ ➔ **EXTRA** `index.js` looks like this

```
import React from "react";
import ReactDOM from "react-dom/client";
import App from "./App";
import "./index.css";

const root = ReactDOM.createRoot(document.getElementById("root"));
root.render( <App /> );
```
➖➖➖➖➖➖➖➖➖➖➖➖➖➖➖<br/>
➖➖➖➖➖➖➖➖➖➖➖➖➖➖➖<br/>
💤 In JSX how to use varibales value
```
function any()
{
    const var = 5 ;

    return (
    <p> {var} </p>
    );

}
```

➖➖➖➖➖➖➖➖➖➖➖➖➖➖➖


## 💙 PROPS - properties



