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
         <item name ={ itemTwoName } > </item>

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

//---------------------------------------

function Item( {name,children} )                 // here "name" that we have sended and "children" is bydefault to access children
{


  return(
         <div>                                    

             <p> {pname} </p>                          
             { children }                   // here we can acces " i am children..."

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
⚠️ **State Lifting UP=** Communicate from CHILD to PARENT ( matlab child value send krega parent ko ) <br/>

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

➔ [some imp of react form handeling with checkBox](https://github.com/parthmern/Web-Development-with-CodeHelp/tree/master/9_React-Intermediate)

➖➖➖➖➖➖➖➖➖➖➖➖➖➖➖<br/>
➖➖➖➖➖➖➖➖➖➖➖➖➖➖➖<br/>
## 💚 React Router
➔ SPA - single page application ( only one html file where changes happens dynamically and if you click anywhere no reloading )<br/>
➔ React Router is a popular library for handling routing in React applications.(route-path)<br/>
➔ it allows you to create single-page applications with multiple views, each represented by a specific URL. <br/>
➔ This makes it possible to navigate between different sections(homepage,about,support section) of your application without triggering a full page reload.<br/>

```
// installation

npm install react-router-dom
```
 
➔ then `index.js` page
```
import { BrowserRouter } from 'react-router-dom';

const root = ReactDOM.createRoot(document.getElementById("root"));
root.render(
    <BrowserRouter>
    <App />
    </BrowserRouter>
);
```
➔ then creates different Components like Home,Support,NotFound <br/>
➔ then in `app.js` 

```
import { Routes, Route, Link, NavLink} from "react-router-dom";

// and import all pages(components) here

function App(){

return (
<div>

     <div>
          <Link to="/">Home</Link>                              //here "Link" works like <a> tag and "to" works like href="/" attribute
          <NavLink to="/support">support</NavLink>              //here "NavLink" is same as "Link" but it adds .active class in active component so easy to identify active
     </div>

     <Routes>
        <Route path="/" element={<Home/>}></Route>
        <Route path="/support" element={<Support/>}></Route>
        <Route path="*" element={<NotFound/>}></Route>          // * means universal excluding mentioned paths
      </Routes>

</div>
)
}


```

➔ *here "/" is home and "/support" is the child of / (home) > /support --- and because of this we can do NESTED ROUTING* <br/>
<br/>
➔ */*     &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;        ---> parent  <br/>
➔ */support* &nbsp; &nbsp; &nbsp;        ---> in / there is support --- child <br/>
➔ */about* &nbsp; &nbsp; &nbsp;         ---> in / there is about --- child <br/>

```
// nested-routing

<Routes>

         <Route path="/" element={<Home/>}>
         <Route path="/support" element={<Support/>}></Route>
         <Route path="*" element={<NotFound/>}></Route>
         </Route>

</Routes>

```

➔ *but here parent element wo child route element ko render nhi hone de raha matalab sab urls par sirf homePage he open ho raha hai* <br/>
 <br/>
➖➖➖➖➖➖➖➖➖➖➖➖➖➖➖<br/>
 <br/>
➔ `<Outlet>` parent route element ke andar child route elemnt ko render karne ki permission deta hai <br/>

```
<Routes>
        <Route path="/" element={<Mainheader/>}>
           <Route index element={<Home/>}></Route>                             // index means default route
           <Route path="/support" element={<Support/>}></Route>
           <Route path="/about" element={<About/>}></Route>
           <Route path="*" element={<NotFound/>}></Route>
        </Route>
      </Routes>
```

➔ in `Mainheader` component
```
import { Outlet } from "react-router-dom" ;

function Mainheader ()
{
   return ( <Outlet></Outlet> ) 
}

```


➔ `<Route index>` matches only when the URL path exactly matches the parent route's path and is typically used for rendering default content within a section of your app.<br/>
➔ `<Route path="*">` acts as a catch-all route, rendering its component when no other route has matched the URL path. It's often used to handle undefined routes or show error pages.

 <br/>
➖➖➖➖➖➖➖➖➖➖➖➖➖➖➖<br/>
➖➖➖➖➖➖➖➖➖➖➖➖➖➖➖<br/>
 <br/>

### ✔️ useNavigate()  
➔ navigation through anywhere  <br/>
➔ here in `Labs` page component <br/>

```
import { useNavigate } from "react-router-dom" ;

const Labs =()=>{

    const navigate = useNavigate();

    function clickHandler(){
        navigate("/about");                     // here ("url") means navigate to "url"
    }

   function backHandler(){
        navigate(-1);                           // here (-1) means it navigate to the BACK (PREVIOUS) opened page
    }

    return(
        <div>
            <div>
                this is labs page
            </div>
            <button onClick={clickHandler}>move to about page</button>
            <button onClick={backHandler}>Go Back </button>
        </div>
    )

}
```
 <br/>
➖➖➖➖➖➖➖➖➖➖➖➖➖➖➖<br/>
➖➖➖➖➖➖➖➖➖➖➖➖➖➖➖<br/>
 <br/>
 
## 💙 Conditional Operators
✔️ [**REACT conditional Operators**](https://chat.openai.com/share/0421b886-f0bb-4362-a912-7f89dd22716d)

➖➖➖➖➖➖➖➖➖➖➖➖➖➖➖<br/>
➖➖➖➖➖➖➖➖➖➖➖➖➖➖➖<br/>

## 💛 api fetching axios method
➔ installing
```
npm install axios
```
➔ using
```
import axios from "axios";

async function fetchData(){

        const url = `https://api.giphy.com/v1/gifs/random?api_key=${API_KEY}`;

        const output = await axios.get(url);

        console.log(output);

    }
    
useEffect(()=>{fetchData()} , [])

```

➖➖➖➖➖➖➖➖➖➖➖➖➖➖➖<br/>
➖➖➖➖➖➖➖➖➖➖➖➖➖➖➖<br/>

## ❤️ Custom HOOK
➔ avoid code duplication <br/>
➔ [DRY coding + yt explained shortest](https://youtu.be/TM6G_23tNVw?si=euj2lzyMzflqBH0A)  <br/> 
➔ [custom hooks explained](https://chat.openai.com/share/6702aa24-ade0-4cbe-bc4d-f7c032cea12c) <br/> 
➔ [thapa technical yt](https://youtu.be/ZyNWBiay5S4?si=VZByBKJMVWqbDDiw) <br/>

➖➖➖➖➖➖➖➖➖➖➖➖➖➖➖<br/>
➖➖➖➖➖➖➖➖➖➖➖➖➖➖➖<br/>

## 💙 Context API

➔ **Prop Drilling** <br/>
➔ [what is Prop Drilling ? and disadvantages](https://chat.openai.com/share/fe576ecd-5cf9-4f8f-8976-c813f043a414) <br/>
➔ [what is Prop Drilling ?](https://chat.openai.com/share/fe576ecd-5cf9-4f8f-8976-c813f043a414) <br/>

<br/>

➔ **State Lifting UP** <br/>
➔ [what is ? - send data from child to parents using propFunction](https://chat.openai.com/share/7f01b44a-7a12-46f5-8ad0-37af826e4c90)  <br/>

<br/>

➔ we are sending props from one parent to the child1 then child2 then child3 then child4 - and here the child1, child2, child3 do not need the data but if we want to pass the data from parent to the child4 then we have to do it  <br/>
➔ it reduce redundancy and performance <br/>
➔ so the solution to send data from parent to child4 without including the child1,2,3 -- is context api

<img src="https://camo.githubusercontent.com/a7f3db9e96268a208a485a976a27aa54ea54badf8d9ba960ce50ef1bb908eb73/68747470733a2f2f6765656b6561736b626c6f67706963732e73332d61702d736f757468656173742d322e616d617a6f6e6177732e636f6d2f706f7374732f575832303139303733302d31333533353425343032782e706e67" width="600px" height="300px" />

 <br/>

➔ Rules:  <br/>
➔ createContext() = creation of context <br/>
➔ provider = context provide <br/>
➔ consume <br/>

✔️ *jis component me context provide kar rhe hai wo component and us component ke sabhi childrens uus value ko use kar sakte hai --means decenteralized value create kar rhe hai* <br/>

<img src="https://www.carlrippon.com/static/0d1f722d0fe4c2bc4c3d71595dbe67dd/ca682/prop-drilling-v-context.png" width="700px" height="400px" />

➖➖➖➖➖➖➖➖➖➖➖➖➖➖➖<br/>
➔ firstly created a folder named "context" and then created a file named "AppContext.js" in that

```
export const AppContext = createContext();

function AppContextProvider( {children} )                            //🌐 children means `<App />`
{
   const [loading,setLoading] = useState(false);
   const [page,setPage] = useState(1);

   // data filling
   if(page==1){
   setPage(page+1);
   }

   function handlePageChange(page){
        setPage(page);
    }

   const value = {           //✔️ value is Object
   loading,
   setLoading,
   page,
   setPage,
   handlePageChange
   }

   // 💯 AppContext.Provider because we have created AppContext as createContext

   return <AppContext.Provider value={value}>     //✔️ we are using above value obj
        {children}                                //🌐 children means `<App />`
    </AppContext.Provider>;

}
```

➔ we want to use AppContextProvider() on `App.js` and their children 
➔ so in `index.js` file we are doing this and here we are sending `<App/>` component as {children} in the "AppContext.js"

```
const root = ReactDOM.createRoot(document.getElementById("root"));
root.render(
  <AppContextProvider>
    <App />
  </AppContextProvider>
);
```

### ➔ useContext Hook -- consuming data 

```
import { AppContext } from "../context/AppContext";


const value = useContext(AppContext);
// or
const { loading } = useContext(AppContext);

```

➖➖➖➖➖➖➖➖➖➖➖➖➖➖➖<br/>
➖➖➖➖➖➖➖➖➖➖➖➖➖➖➖<br/>

## 🤍 useSearchParams() and useLocation() in react-route
 
➔ [useSearchParams()](https://chat.openai.com/share/fc36c106-c78f-4635-8d25-4822a01d17f5) <br/>
➔ [useLocation()](https://chat.openai.com/share/1a6c673f-89f5-45c0-adcc-0887827ab847)  <br/>
➔ [LoveBabbar-guide](https://drive.google.com/file/d/1MgZvDD_weKooCxKD-HZI88xoxnejqENH/view?usp=sharing) <br/>

➖➖➖➖➖➖➖➖➖➖➖➖➖➖➖ <br/>
➖➖➖➖➖➖➖➖➖➖➖➖➖➖➖

## 💚 Redux ToolKit

➔ what is and why ?

✔️ Installation
```
npm install @reduxjs/toolkit react-redux
```

✔️ create Slice = slices canbe single or multiples ( like SLICEs of one pizza and they create a whole pizza that is STORE )
```
//📂 src > redux folder > slices folder > CounterSlice.js

import { createSlice } from "@reduxjs/toolkit";


//🏳️‍🌈 createSlice mei 3 things ayegi 1)name 2)initialState 3)reducers means obj jis k andar sab functions honge

const initialState={
    value : 0,
}

export const CounterSlice = createSlice({
    name: 'counter',
    initialState,
    reducers : {
        increment : (state) => {
            state.value += 1;
        },

        decrement : (state) =>{
            state.value -= 1;
        }
    }
})

// 🌐 in every slice 
export const { increment, decrement } = CounterSlice.actions;   //exporting functions from actions
export default CounterSlice.reducer;                            //exporting reducer

```

✔️ create Store = store k andar sab slices ayegi ( store global state/centeralized state hogi jiske andar sab states store hogi in form of slices )

```
//📂 src > redux folder > store.js

import { configureStore } from '@reduxjs/toolkit';

import CounterSlice from './slices/CounterSlice';

const store = configureStore({

  reducer : {
        counter : CounterSlice ,                         // idhar "reducer" obj k andar sabhi slides ayegi ==> name : sliceName
    },                                                   // agar ERRORS aarhe hai like( Store does not have a valid reducer) toh `CartSlice.reducer` try kro

})

export default store;
```

✔️ Connect reduxToolkit with reactJs using `<Provider>` 

```
import { Provider } from "react-redux";
import store from "./redux/store";

const root = ReactDOM.createRoot(document.getElementById("root"));
root.render(
  <Provider store={store} >
    <App />
  </Provider>
);

// aab <App/> k andar k sare components use kar payenge redux States ko
```

➖➖➖➖➖➖➖➖➖➖➖➖➖➖➖ <br/>
### useSelector() ✔️ Access state/ value from Slice

```
import { useSelector } from "react-redux";

const value = useSelector( (state)=> state.counter.value )

//📝EXPLAINED----------------------------------------------------------------
// here useSelector( callBack function that returns the value )
// sabse pehele call store me jati hai then wo slice me jati hai

// state => { counter: {value: 0} }
// state.counter => {value: 0}
// state.counter.value => 0

// matlab "state" k andar sabhi slices hongi and us slices k andar unki value hongi
// idhar sirf ek slice hai jiska name "counter" diya tha and uski initialState(initialValue) = 0 define ki thi
```

➖➖➖➖➖➖➖➖➖➖➖➖➖➖➖ <br/>
### useDispatch() ✔️ Access functions(reducers)

```
import { useDispatch} from "react-redux";
import { decrement, increment } from "../redux/slices/CounterSlice";

function CounterComponent()
{
   const dispatch = useDispatch();

   return(
   <div>
      <button onClick = { ()=>dispatch( increment() ) } > Increment </button>
      <button onClick = { ()=>dispatch( decrement() ) } > Decrement </button>
    </div>)

}

```
➖➖➖➖➖➖➖➖➖➖➖➖➖➖➖ <br/>
✔️ Access Input parameters using "action.payload"

```
.
.
.
reducers : { 
   add : (state,action) => { ( state + action.payload ) }        //state means present value -- and -- action.payload means passed argument
}

//-------------------------------
//passed arguments from anywhere

dispatch(add(5)) ;
```

➖➖➖➖➖➖➖➖➖➖➖➖➖➖➖<br/>
➖➖➖➖➖➖➖➖➖➖➖➖➖➖➖<br/>

## ❤️ useReducer hook
➔ if you want to use multiple useState() then to avoid this you can use this <br/>
➔ [technical-thapa](https://youtu.be/VdXGIEYZuCw?si=Bg6O_vSW8OYLdUmd) <br/>
➔ [gpt](https://chat.openai.com/share/aa3c0607-c76e-42be-bd88-4602a08b785d) <br/>

🚨 Explained in amazon clone by [cleaver programmer](https://youtu.be/RDV3Z1KCBvo?si=F_9n5O1xr0th0CwG) <br/>

<br/>

<br/>



➔ with context-api
```
//📂 src > context > StateProvider.js

import React, { createContext, useContext, useReducer } from "react";

export const StateContext = createContext();

export const StateProvider = ({ reducer, initialState, children }) => (
  <StateContext.Provider value={useReducer(reducer, initialState)}>
    {children}
  </StateContext.Provider>
);

//anywhere we can use useStateValue() instead of using useContextHOOK which is useContext(StateContext)
export const useStateValue = () => useContext(StateContext);
```

➔ reducer file which have reducer initialState and reducer
```
//📂 src > context > reducer.js

export const initialState = {
  user: null,
  playlists: [],
}

const reducer = (state, action) =>
{
  console.log(action);

  switch (action.type)                  // we can also use IF-ELSEIF-ELSE here insted of switch
  {
    case "SET_USER" :
      return {
        ...state,
        user: action.user,
      };

   case "SET_PLAYLISTS" :
      return {
        ...state,
        playlists: action.playlists,
      };

   default :
      return state;

    }
}

export default reducer;
```

➔ how to joint context-api
```
// 📂 index.js

import reducer, { initialState } from "./reducer";  //📂 src > context > reducer.js

ReactDOM.render(
  <React.StrictMode>
    <StateProvider initialState={initialState} reducer={reducer}>
      <App />
    </StateProvider>
  </React.StrictMode>,
  document.getElementById("root")
);

```

➔ use useReducer() hoook
```
const [state,dispatch] = useDataLayerValue();
//or
const [state,dispatch] = useContext(stateContext);
//or
const [{user,playlists} ,dispatch] = useDataLayerValue();   //console.log(user); -- everytime updated like useState

//console.log("state ==",state); // initialValues {user: null,playlists: []} OTHERWISE latestValuesOfInitialState {user: "updatedValue",playlists: []}
//console.log("dispatch ==",dispatch); // function to set initialValues

dispatch({
  type : "SET_USER",
  user : "updatedValue",
});
```

➖➖➖➖➖➖➖➖➖➖➖➖➖➖➖<br/>
➖➖➖➖➖➖➖➖➖➖➖➖➖➖➖<br/>
➖➖➖➖➖➖➖➖➖➖➖➖➖➖➖<br/>
➖➖➖➖➖➖➖➖➖➖➖➖➖➖➖<br/>

# 🧩 CHEAT-SHEET 🎼 🎇

 🎯 [by LoveBabbar](https://drive.google.com/file/d/1gvCogzZeqEcY8UwCypfR7LOFx2soaXCx/view?usp=sharing) <br/>
 🎯 [random](https://drive.google.com/file/d/16Z7qBikLr_GTjI-xzmHyRIVtiZmZnN28/view?usp=sharing) <br/>
 🎯 [by tutorialsPoint](https://drive.google.com/file/d/1DGP7WYTMjEnxdfmpz3PSLKYMUAw4H1lT/view?usp=sharing) <br/>
 🎯 [imp topics to learn](https://drive.google.com/file/d/1EtA2awgTCVZckTAO__zHfrNL88yNlaei/view?usp=sharing) <br/>
➖➖➖➖➖➖➖➖➖➖➖➖➖➖➖<br/>
♻️ @ Created by Parth with 💚
