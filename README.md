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

## 💙 PROPS - properties

💤 **Extra -** In JSX how to use varibales value
```
function any()
{
    const var = 5 ;

    return (
    <p> {var} </p>
    );

}
```
➖➖➖➖➖➖➖➖➖➖➖➖➖➖➖<br/>
➖➖➖➖➖➖➖➖➖➖➖➖➖➖➖<br/>
<br/>
✔️ ➔ here we have to send properties from `App.js` file like this
```
function App()
{
  const itemTwoName = "patel" ;                                       //⚠️ here we are doing PARENT to CHILD communcation using props matlab parent kuch value send kar rha hai child ko

  return (
    <div>
         //one way
         <item name = "parhu" > </item>

         //second way
         <item name ="{ itemTwoName } " > </item>

         //children of prop
         <item> i am children which is between and inside the component </item>
    </div>
 );
}
```

✔️ ➔ in `Item.js` we have to change things like

```
function Item(props)
{

 const pname = props.name ;

  return(
         <div>                                    // IMP = if there are more than one html line then put them into <div> TAG

             <p> {pname} </p>                          
             { props.children }                   // here we can acces " i am children..."

          </div>
  );
}
```

➖➖➖➖➖➖➖➖➖➖➖➖➖➖➖<br/>
➖➖➖➖➖➖➖➖➖➖➖➖➖➖➖<br/>

## 💛 PROPS as Event handling

```
function clickHandlerFunction()
{
  //anything that you want to perform
}

// Event Handling
<button onClick={clickHandlerFunction} > xxxx </button>
```

⚠️ *always remeber that while using `callbackFuntion` avoid to write this `callbackFuntion()` beacuse `()` means that automatically calls the function without any Event done*

➖➖➖➖➖➖➖➖➖➖➖➖➖➖➖<br/>
➖➖➖➖➖➖➖➖➖➖➖➖➖➖➖<br/>

## ❤️ State (useState Hook
➔ for Re-Rendering purpose <br/>
➔ like i want to change innerText / value updation of any element when i click on the button but to do this i have to do Re-Rendering <br/>
<br/>
➔ Before state
```
function clickedBtn()
{
  const title = "oldValue" ;

  function cbFunc()
  {
    title = "newValue" ;
  }

  return(

  <div>
       <h2> {title} </h2>
       <button onClick={cbFunc} > xxxx </button>
  </div>
  
  );
}

// 📝 here first react render the whole DOM so the value of title = "oldValue" and it print "oldValue" in <h2> tag  but when we clicked on
// <button> tag that time the value of title = "newValue" changed so that time again Render is not possible and the again print is not possible so NOT any CHANGES in <h2> tag output

```
<br/>
<br/>
➔ ✔️ After state

```
import React, {useState} from 'react';               // first import {useState} which is react-Hook(utility function)

function clickedBtn()
{
  const [title,valueUpdateFunc] =useState("oldValue");             //useState returns 2 things as array form first is newValue of variable and function for updating value (using destructing js method)

                                                        // syntax = const [variableName , valueUpdateFunc] = useState("oldValue");
  function cbFunc()
  {
    valueUpdateFunc("newValue");
  }

  return(

  <div>
       <h2> {title} </h2>
       <button onClick={cbFunc} > xxxx </button>
  </div>
  
  );
}

// 📝 after clicked on <button> there is also re-Redering and the value of <h2> updated to new value on UI
```

<br/>

📑 HomeWork = <br/>

1 = [Why React Hook useState uses const and not let](https://stackoverflow.com/questions/58860021/why-react-hook-usestate-uses-const-and-not-let#:~:text=useState%20is%20simply%20a%20state,for%20you%20by%20calling%20useState.&text=After%20calling%20setCount%20the%20component,useState%20returns%20the%20new%20value.)  <br/>

2 = [what is immutable react js - combined with useState que ]()  <br/>

3 = [React setState/useState happens instantly or takes time](https://linguinecode.com/post/why-react-setstate-usestate-does-not-update-immediately)<br/>

<br/>
<br/>

🚨 EROORS=<br/>
➔ img is a void element tag and must neither have `children` nor use `dangerouslySetInnerHTML`. ==> then write `<img />` in just single closing

<br/>
<br/>

📑 Extra for FORM = <br/>
➔ *get the value of input field that inserted by user using (event) and `event.target.value` word* <br/>
➔ *how to set value of any text field `value = { xyz }` it can set value as "xyz" in inputfield* <br/>
<br/>
<br/>
⚠️ Communicate from CHILD to PARENT ( matlab child value send krega parent ko ) <br/>

➔ `app.js` means PARENT looks like this <br/>

<br/>

```
function App() {

  function ParentValue(data)
  {
     console.log(data);
  }

  return (

    <div>
      <Child ParentValueFunc={ParentValue}></Child>          //here using props we are sending function to the Child
    </div>
    
  );
}
```

<br/>

➔ `Child.js` means CHILD looks like

```

function Child(props){

    props.ParentValueFunc("dataaa Inside secreate");             //here ParentValueFunc get the parameter as data = "dataaa Inside secreate" 
    
    return(<p>hell insider here</p>);
}
```

*so we can send the value from CHILD to PARENT using function with parameter like above*


➖➖➖➖➖➖➖➖➖➖➖➖➖➖➖<br/>
➖➖➖➖➖➖➖➖➖➖➖➖➖➖➖<br/>


## 💜  useEffect ( raect hook )
➔ manage side-effects (if i do any action at one component then there is also some changes on another component - ex.changing doc title, modifying state of parent component,api calls,changes in DOM ) <br/>
➔ every RENDER of UI useEffect will excecute <br/>
➔ agar aap kuch kaam karwane chahte ho UI render means UI me changes hone k baad tab aap useEffect use kar sakte ho

```
import {useEffect, useState} from "react";           // first import

function App()
{

   const [text,setText] = useState('') ;

//------------------------------------------
  // VARIATION-1️⃣ (every render)

  useEffect( () => {
    console.log("UI render Done");} 
  );

//------------------------------------------
  // VARIATION-2️⃣  (first render - when app.js fully renderd for first time)

  useEffect( ()=>{
    console.log("UI rendere done");
  },[] );

//------------------------------------------
  //VARIATION-3️⃣ (first render + whenever dependency changes)                  // firts render + whenever variable "text" changes this useEffect runs

  useEffect(()=>{
    console.log(" text changed observed");
  } , [text] )

//------------------------------------------
  //VARIATION-4️⃣ (to handle unmounting of components)

  useEffect(()=>{
    //add event listener
    console.log("listener added");

    return ()=>{ console.log("listener removed"); }
  })                                                                            //IMP= first run "listener removed" then run "listener added"


//---------------------------------------------------------------------------------

  function changeHandler(event){
    setText(event.target.value)
    console.log(text);
  }

  return (
    <div className="App">
      <input type="text" onChange={changeHandler} />
    </div>
  );

}


```

➖➖➖➖➖➖➖➖➖➖➖➖➖➖➖<br/>
➖➖➖➖➖➖➖➖➖➖➖➖➖➖➖<br/>
## 💙 Array methods
➔ using array , if we want to create multiple components at a time then use `array.map( callBackFunc )` <br/>
➔ if we want to do filter then use `array.filter (callBackFunc)` <br/>

```
items.map( (item)=> { return (<div>{item}</div>) } );
```

➖➖➖➖➖➖➖➖➖➖➖➖➖➖➖<br/>
➖➖➖➖➖➖➖➖➖➖➖➖➖➖➖<br/>
## ❤️ React Forms
➔ form handleing is difficult in js because everytime we have to create different functions to save the value of all fields in form

```

function App() 
{

  const [formData,setFormData] = useState(
    {
      firstName : "" ,
      lastName : "",
    }
  );

  function changeHandler(event){
    setFormData( (prevFormData)=>{
      return {
        ...prevFormData,
        [event.target.name] : event.target.value 
      }
    } )
  }

  return (
    <div>
      <form>
        
        <input type="text" placeholder="first name" onChange={changeHandler} name="firstName" ></input>
        
        <input type="text" placeholder="last name" onChange={changeHandler} name="lastName"></input>
        
      </form>
    </div>
  );
}


// here every changes on <input> tag , the changeHandler function will run
// and in function setFormData will take return the object with value which is already named as `formData`
// the under process in return => it take previousObject with all changed properties and then access that property using the `name` that given in html element
// means 1) previous state copy 2) element trigger and value update
```

➔ JS topic= [referance link of spread operator with object](https://www.javascripttutorial.net/es-next/javascript-object-spread/)

➖➖➖➖➖➖➖➖➖➖➖➖➖➖➖<br/>
### 💛 Controlled Components
➔ maintain state inside component

```
 <input type="text" placeholder="first name" onChange={changeHandler} name="firstName" value={formData.firstName}></input>
        
 <input type="text" placeholder="last name" onChange={changeHandler} name="lastName" value={formData.lastName} ></input>

// here we are also re-rendering values from formData object in the components
// matalab jab bhi formData ki state change hogi then tab har ek components jisme value={formData.something} dali hui hai uski value b re-render hogi
// bascially formData me jo bhi value aarhi hai usko hum uske original components me update kar rhe hai

```

