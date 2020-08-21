# Drum-Kit---A-Drum-Player

It is a really cool project where the user has the whole Drum kit on their keyboard! The users can play different Drum Sounds and experiment with their own melodies!

NOTES:
JAVASCRIPT:
PLEASE REFER LINE 223 FOR NOTES SPECIFIC TO DRUM-KIT PROJECT.

alert("message") - for displaying an alert window.
prompt("message: ") - to take input from user by giving a particular message

var name="Rohan"; - var to declare a variable

typeof(name); - to get the type of a variable

console.log(name) - to get the output in console of the browser

function newFunc(bottle){
    //use function to declare a new function
}

var a = 1;
var b = "1";

if (a === b){
    // === checks whether a == b and whether a and b are of same data type or not. Data types should also match.
}

if (a == b){
    // == checks whether a == b and ignoring the data types.
    }

===
!==
<
>
<=
>=

//&& || ! - same as C++


var arr = [1, 2, 3]; - to declare an array.

arr.includes(2) - includes function will tell whether an element exists in the array or not. Returns a Boolean. i.e True or False.

arr.push(4); - push() an element at the end of the array.
arr.pop(4); - pop() deletes an element from the end of the array.

------------------------------------------------------

website part:

Just like CSS, js can be implemented into a website in 3 ways:
1. Inline js  :-  
    <body onload="alert('Hello');"> 
        Hello 
    <body>

2. Internal js :-
    <script type="text/javascript">
        alert("hello");
    </script>

3. External js :-
    <script src="index.js" charset="utf-8"> </script>


--------------------------------------------------------
javascript DOM :

document;

        #document (i.e whole document TREE)
            |
           html
        ---------
        |        |
       head     body
        |        |
       title     H1

document.firstElementChild;
since firstElement is html so it will return the whole html TREE.


document.firstElementChild.firstElementChild;
since firstElement is html, and it's firstElementChild is head so it will return the whole head element TREE.


document.firstElementChild.lastElementChild;
since firstElement is html, and it's lastElementChild is body so it will return the whole body element TREE.


document.firstElementChild.lastElementChild.firstElementChild;
since firstElement is html, and it's lastElementChild is body, and body's firstElementChild is the H1 element so it will return the whole body element. By this way we can target a specific element in the html using Javascript DOM. In the next example we'll see how to manipulate this selected element.

var heading = document.firstElementChild.lastElementChild.firstElementChild;
heading.innerHTML = "Good Bye";  
//innerHTML is used to manipulate the inner html of the target/selected element.

heading.style.color = "red";
//.style.color will change the color of the target/selected element.

document.querySelector("input").click();
//looks into the entire document for an object that has a selector of type Input, and click() simulated a mouse click on that element.

There are 2 characteristics associated with an element/object:
1. Property
2. Methods

Property of an element/object is like it's color, 
i. we can get property:
    eg: car.color;

ii. we can set property:
    eg: car.color = "red";

Methods are always applied on an object.
    eg: car.drive();
    //method call on object car. drive() method is associated with car object.


PROPERTIES EG:
- innerHTML
- style
- firstChild

METHODS EG:
- click()
- appendChild()
- setAttribute()


document.getElementsByTagName("li");
//here getElementsByTagName("li") will return all the li elements from the selected tree.

Please note that, as the name suggests getElements... it will return all the elements found. So, it will return in an array form.
So, in order set a property we have to select a particular array element which we want to manipulate. i.e:

document.getElementsByTagName("li")[3].style.color = "purple";

document.getElementsByTagName("li").length will get the length of the array thus telling us how many li elements exists in the document.

document.getElementsByClassName("btn");
//here getElementsByTagName("btn") will return all the elements with class="btn" from the selected tree.
//it will also return in the form of array(since name: getElements....)

document.getElementsByID("title");
//here getElementsByID("title") will return the element from the document with ID="TITLE".
//Please not since all the id's in an html doc. should be unique, so it will not return array in this case. (thus the name getElement....)

------

document.querySelector(" element-tag/ class / id ");
//just like in external css, a query selector could be an element tag, or a class or an id, and just like we use them in css by combining we can also implement that here..

eg. document.querySelector("h1");       // selected the h1 tag
eg. document.querySelector("#title");   // selected the #title id, #is used for id's
eg. document.querySelector(".btn");     // selected the .btn class, .is used for classes.

eg. document.querySelector("li a");    // selected the anchor tag under the li

eg. document.querySelector("li.item");

eg. document.querySelector("#list a);

///// querySelector(); always returns a single element, i.e. the first ever occurance which is found. In order to get all the occurance, we have to use:

// querySelectorAll("#list .item");

document.querySelectorAll("#list .item")[2].style.color = 
"blue";

// used index to manipulate the property since an array is returned by querySelectorAll.


-------------------------------------------------------
change CSS using javascript:

-in css properties are seperated by hyphen(-), eg: font-size
but since javascript follows camel case the properties also follow camelCase in javascript, so: fontSize.

-We have to use property-value as a string in javascript, eg:
CSS: font-size: 10px;
javascript:
<eg. obj>.fontSize = "10px";


-----------------------------------------------------------------
document.querySelector("button").classList;
//classList returns the list of all classed applied to the element "button"

document.querySelector("button").classList.add("invisible");
//classList.add("") adds/applies an existing defined class in css to the 
desired element i.e. button here. the invisible class is defined in css and it is applied to the button tag when javascript will execute.


document.querySelector("button").classList.remove("invisible");
//classList.remove("") removes an existing applied class from the element when javascript is executed.


document.querySelector("button").classList.toggle("invisible");
//classList.toggle("") toggles an existing applied class from the element when javascript is executed. i.e if the class already is applied it removed it. and if it's not applied then it adds/applies it to the element. Thus the name toggle.

 document.querySelector("h1").textContent;
 //.textContent will return only the text content where as innerHTML will return the full html inside the given element tag (if exists)

 using innerHTML we can also change the inner html using javascript.

 document.querySelector("a").attributes;
//.attributes will return a list of all the attributes associated with the element tag.

 document.querySelector("a").getAttribute("href");
 //.getAttribute("") returns the value of a particular attribute associated with a specific tag. i.e value of href with 'a' tag is www.google.com

 document.querySelector("a").setAttribute("href", "www.bing.com");
 //.setAttribute("attr", "value") sets the value of a particular attribute associated with a specific tag. i.e value of href with 'a' tag was www.google.com  but now changed to "www.bing.com"

 
-------------------------------------------------------------------------

Advanced javascript & DOM Manipulation [Drumkit Project]:

document.querySelector("button").addEventListener("click", handleClick);
//<target>.addEventListener("<Event_Type, usually in lowercase>", <Listener, Zusually a js-function[without parenthesis] called when the specified event gets detected>);
// if we use parenthesis with the function call in case of Listener, then the function is immediately called, as the pointer reaches that statement. But we want the function to be called when the event is happening so the name of the function is passed without parenthesis.
// An anonymous function is a function without a name:
function () {
    <statements>;
}
//We can use anonymous function in the place of Listener in the above example.


function sum(num1, num2)
{
    return num1+num2;
}

function calculator(num1, num2, operator)   //higher order function are functions that can 
{                                           //take other functions as inputs.
    return operator(num1, num2);
}


#objects in javascript:

var student = {
    name = "Rohan",
    age = 20,
    weight = 70
}

//constructor function: A constructor function in javascript is always started with a capital first letter exception to the camel case.

function Student(name, age, weight)
{
    this.name = name;
    this.age = age;
    this.weight = weight;
    this.admission = function(){            //function within an object.
        alert("Admission Successful!")
    }
}

var stud = new Student("Mehra", 12, 50); 
//A constructor function in javascript is always called with 'new' keyword.

stud.admission();
