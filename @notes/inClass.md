# INCLASS NOTES - DevMountain

### Git
for getting onto your branch

	// git push origin <nameOfBranch>

git branch <nameOfBranchToCreate>



### html / css
html = skeleton of webapp/website
css = hair/skin visuals

every html element has default properties (e.g., margin/padding,etc.)
thing have defaults (know the defaults to use the proper tag)
	knowing the defaults == cleaner code
	
	html5 == try to make more semantic tag
	
	<footer></footer>       <— can be used in multiple places 
	
	<ol>
	  <li></li>
	    </ol>  <—— ordered list
	
	    <ul>
	      <li></li>
	        </ul>  <—— unordered list
	
	            // caniuse.com // <— to check for compatibility 

### classes and id’s
reuse class
id == don’t use id’s if you can help it

as a general rule you don’t want to throw out a style to all div’s

	for SPECIFICITY YOU DON’T WANT A HIGH NUMBER (e.g., 120+ in the specificty calculator)

### inline styles  \<—- don’t use it
  don’t do it.

	something that is even worse
	    using !important   <—- as a general rule
	            // using important to debug only
	
	                ^ the specifity and you don’t see the !important (which is infinite specific) it eliminates a specifity issue
	
	
	                !! width is specific to the container it’s in
	                    it has to be defined, e.g., you have to define the body (it’s parent) in order to make it work)
	
	                    when to use pixels > percentages would be a design that is set at a fixed amount
	                        e.g., a sidebar that’s 310px
	                                don’t want to use, case example would be using a very large hi-res screen

### background-image
	background-size: cover
	            or contain
	                    background-repeat: no-repeat;
	
	                    background: url(stuff.image) no-repeat;
	
	
	                    will be using float: left || right
	
	                    you will generally float the parent instead of using overflow: auto, etc.,

## 2015-04-01 - InClass w01d03 - Wed
---
### InClass start of project -- going over problem 3 
	nesting was used for the logo, (example inClass) container>header>logo
	
	overall it was how I did it, still should go back to finish it

### InClass Lecture

	css shorthand - 
	    margin: 0, 0, 0, 0; --> margin: 10px 20px;
	    margin: top, bottom;

// review of D02 assignment - png1 --\> saved on CodePen

### color
	hex - 
	    #000000 = black
	    #ffffff = white
	    #333333 = darkGrey
	        cons // no alpha layer
	    shorthand - if the first 3 = last three, stop @ 3
	        e.g., 000  == 000000
### floats
	do you want to float the parent?
	    yes = float
	    no = overflow auto

### dev tools - Chrome
	when looking @ a website, right-click --> 'inspect element'
Can change html on the fly, color, etc.
change things w/out committing

Has auto-suggestion, unless it's looking for a specific number value --\> 'inherit/initial/\~sometimes normal

### keep code DRY - don't repeat yourself
example of bad :
	button1 {
	    background: red;
	    color: white;
	}
	button2 {
	    background: red;
	    color: white;
	}
	button3 etc.

good example:
	.button {
	    background: red;
	    display: inline-block;
	    padding 20px;
	    }
	
	.button--call-to-action {
	    background: blue;
	}
<!-- end of example -->


### positioning --\> in codePen
 ! as a general rule, you DON'T want to use positioning to get it exactly where you want

	default position = static
	    relative = relative to whatever it would normally go, it's relative to that
	    absolute = based on the BROWSER WINDOW
	        // instead of 'where would this normally go, it's looking at how is this offset from the browswer window
	
	                relative = where it would be be
	                absolute = from the browser window

HOW TO CHANGE HOW ABSOLUTE WORK
	! change it's parent to RELATIVE, this will make it ABSOLUTE from it's parent instead of browser window


### display --\> codePen
display: block;
	-div's are naturally block
	-will take up as much width as possible

display: inline-block;
	-only take up the space that you need
	-!! it ADDS an EXTRA CHARACTER OF SPACE !!!
	    -- e.g., two blocks @ 50% in display:inline-block <-- WILL NOT FIT SIDE-BY-SIDE, b/c of the extra character
	        * using floats can make these fit *
	-it respects verticle margin
	 

display: inline
	! DOES NOT RESPECT VERTICLE MARGIN
	
	text is by default - inline 

### FLEXBOX \<-- the future for layouts  // ! in codepen.io add 'display: -webkit-flex;' in addition to display: flex;
	- put the properties on the parent
	
	parent element == display: flex;
	    e.g., 
	        .parent {
	            display: flex;
	            justify-content: flex-start;
	            height: 200px;
	        }
	
	        .box {
	            background: black;
	            height: 50px;
	            width: 50px;
	        }
<!-- end of example -->

<!-- beginning of Tut+ 'CSS: Flexbox Essentials -->
<body>
	<div class='container'>
	    <div class='item item1'>item1</div>
	    <div class='item item2'>item2</div>
	    <div class='item item3'>item3</div>
	    <div class='item item4'>item4</div>
	    <div class='item item5'>item5</div>
	</div>
</body>

<!--start of css -->
.container {
	background-color: #555;
	width: 800px;
	height: 400px;
	margin: 0 auto;
	display: flex;
}

.item {
	width: 60px;
	height: 60px;
}

// ! rest of code is in CodePen.io 'tutsPlus flexbox'
 

<!--start of notes -->
divs = naturally block elements
(p == short for parent element / c == short for child element)

p display: flex;


c flex-basis: ; \<-- the natural width of the elements
c flex-grow: 1 ; \<-- arbitrary number
c flex-grow: 2 ; \<-- how much these items will grow in relation to each other

c flex-shrink: 1; \<--arbitrary, similar to flex-grow
c flex-shrink: 2; \<--shrinks twice as much as the others


#### shorthand properties
c flex: growValue shrinkValue basis; \<-- this 'flex:' shorthand expects 3 values
	flex: 1 1 450px;

// shorter shorthand

to get something twice as wide than something, use this shorthand:
c flex: 1;
	flex: 2; <--twice as wide as ^

#### flex-direction
p flex-direction: row || column;
	flex-direction: row-reverse;
	flex-direction: column-reverse;

#### using padding / margin with flexbox
just as normal, use p container

set min-width on p container to effect everything 
	setting for wrapping on the other line
	p flex-wrap: wrap; <--default is nowrap
	    flex-wrap: wrap-reverse; <--the fourth item would jump to the top as it gets smaller // probably won't use it that much

#### flex-flow: shorthand for flex-direction: & flex-wrap
flex-direction (horizontal or vertical) flex-wrap (wrap or wrap-reverse)
	// ^ are the flow

// ! can set flex-basis: auto;

#### flex-box vendor prefixes
 // install 'autoprefixer'


// simple website layout //



--- 
### OVERFLOW
	.parent {
	    background: black;
	    stuff
	    stuff
	    overflow: scroll;
	}
	
	auto == does it need a scrollbar? adds if yes
	scroll == adds scrollbar whether needed or not

### FONT-FAMILY
	basic about serif/san-serif
	add moarrr

### Z-INDEX
	poisition absolute & relative works, static will NOT allow
	generally label it w/ 100
	
	// working on a good z-index example in codePen.io, along with positions
parent:
	flex-direction: row || columns
	flex-direction: row-reverse; column-reverse;

child:
	flex: 1;
 
### MAX/MIN width
	sometimes you'll want to put a constraint, specifically with large screens
	    e.g., someone has a 4k monitor and it looks like shit
	    !!! IF YOU WANT IT FLEXIBLE
	        width: 50%;
	        max-width: 600px;

### reset vs. normalize
	used to be a good convention to add a reset stylesheet
	    reset stylesheet resets everything
	        e.g., h1, h2, etc., are exactly the same, e.i.,
	
	*normalize* is considered a best practice
	    !! INCLUDE IN OUR PROJECTS @ THE BEGINNING of the html !!

# 2015-04-02 -InClass w01d04 - Thu
		 
review of MDN - for reference 

### tables
 // don't use this unless you have actual tabular data // 

	<table>
	    <tr>
	        <td>table1</td>
	        <td>cellData</td>
	    </tr>
	</table>

display: inline / inline-block / or **display table**
	using display: table is fine, but don't use it html unless actually making a table

p   display: table;
c display: table-cell;
c vertical-align: center;

	// think of every element as a rectangle ~ box
	    the box-model is the thing that determines the size of the element
	width:
	height:
	padding:
	border:
	    margin: <-- has nothing to do with the size of the element

#### border-box takes into account both padding and margin in calculating box-size

learn more about 'transition' and look at 'will-change' for smoother performance

### sudo classes
	.button:hover
	.button:active  <-- when you actually click it
	.button:visited <-- the visited state
	
	.input:focus <-- used for forms


.button:nth-child(even) {
	background: blue;
}

what .button:after {
	content: '';  <----used for icons primarily / or triangles for tooltips, will use :before && :after

.button:after {
	clear:both; <--clear fixes
}

.button:nth-child(1 \<--where you want to start)
.button:nth-child(2n + 1) {
}

### media query && responsive design
	design mobile first <-- 
	    think about content in a strategic way to present well on
	        -mobile
	        -&& computer
	
	poor web design would be university websites

@media {

}

larger projects put media query AFTER THE THING YOU WANT CHANGED



mobile first will use min-width generally, not max width

 // put media queries when the design starts to breakdown

 4 media query break-points should be good

 depending on the size of he site, you'll want to place the media-query right after the thing you want to change
!!  media queries at the top do not have any specificity && won't be applied

things to know
	when working on a web app, the designer says i need this to be a fixed width e.g., sidebar to be 300px, but the rest of the site to be a %
	
	!* on 'width' property
	    width: calc(100% - 300px);  
	
	    browser read from RIGHT to LEFT for selectors
	    looks for the body first 


### different selectors
.box.blue  ( \<-- select only items with the class both .box \*\* .blue )

.box + .box  ( \<-- will be applied to any .box that has .box PRECEDING it, so the first .box will not have the style applied to it ).

.parent \> .box  ( \<-- direct descendent ) 

.parent .blue  ( \<-- item that is .blue which is nested in .parent )


 
### chrome dev tools
	using the inspector you can toggle :hover, :active, etc., and allows you to edit while looking at that state

### TOY PROBLEM
  css-selectors fromt : https://flukeout.github.io
	second one finished

### @Home flex tut
p display: flex;
p flex-direction: column; \<--default is row
	                                row-reverse; <--reverses the c's
	                                column-reverse: <--reverse the c's

c flex: 2  \<--twice as big as 2
c flex: 1
c flex: 2
c flex: 1

	// specifying the order
c flex:1;
	order:2;
 
c flex:1;
	order:1;

c flex:1;
	order:4;

c flex:1;
	order:3;

!// \<-- add 10px of padding on the body to show it re-size !//

media query -
	@media (max-width: 600px) {
	    .item1 { order: 4; }
	    .item1 { order: 1; }
	    .item1 { order: 1; }
	    .item1 { order: 1; }
}


### adding content:
normally takes up the flex box
// using padding & margin is very much the same as in everyday use //   

you could hard-code the height, but you don't know how much content will be in there. no matter how much you put in there they will be the same height

content-spacing:

.item {
	padding: 10px; <--still need padding so the text doesn't run right next to the edge
	margin: 10px;
}

can set min-width, so that the columns will sop resizing, but the CONTAINING element will continue to collapse

### wrapping content
p flex-wrap: nowrap; \<--default 
	this defines how you want the container to react 

p flex-wrap: wrap \<--this will react with the the container to make the items react

 // if the minimum widths of your flex-items exceeds the width of the CONTAINER, you're able to define how those items behave

### flex-flow shorthand
	it combines flex-direction && flex-wrap

p flex-flow: row wrap; (first = direction second = wrap)

!# when the content over-flows the container , e.g., you have a lot of <p> and it goes over

	to fix, set the flex-basis
	
	c flex: 1 0 auto; <-- the flex-basis: auto; is what helps
	
	c width: 200px;
	c max-height: 250px; <--issue in the tutsplus example

### cross-axis alignment
when your content wraps to the next row or column, depending on how your layout is set up, there may be unwanted space along the cross-axis, this discusses how to align-content to adjust spacing

p align-content: flex-start; \<--aligns with the 'start' && the example it would be next to the other content
	instead of evenly spacing the c's in the container, it would get rid of that space

in the example, p flex-flow: COLUMN wrap; \<--

p display: flex;
	flex-flow: column wrap;
	align-content: flex-start; <--default is 'stretch
	
	
	when it's columns - the cross axis is horizontal
	when it's row - the cross axis is vertical
	
	// when p flex-flow: row wrap;
	p align-content: flex-start;
	                        flex-end; <--align to bottom
	                        flex-between; <--ADJUST SPACE BETWEEN 
!!! the flex-between will allow the items to be on opposite ends

### justifying content
the justify content deals with the MAIN axis (versus the CROSS axis of the 

example they take off the flex property in three of the c's, but keeps it on item 4

p justify-content: center; \<--this allows to adjust the other axis, i.e., rows deal with horizontal on the align-content, while justify-content deals with vertical

// justify-content along main
	align-content along cross

### align-items
allows you to align each individual flex-item to cross-axis instead of the entire row or column as a whole

a way to align items based on the height of those items (default = stretch)

p align-items: flex-start; \<--this gets rid of the stretch and allows the example items to be the height of the content (and not the full height of the container

	// allows to retain their natural height instead of all of the columns/rows being the same height
	
	p items-align: center; <--put them in the center
	
	p items-align: baseline; <-- when the items have padding/margin, it changes the content, so the headers of the content are all aligned, in this example the headers
	
	property called 'align-self'
	
	c align-self: flex-end; <--this allowed the example to have .item1 ignore the other three .items that were aligned to the baseline

// had main .container display: flex; \<-- that is a div around everything, then followed other containers



## 2015-04-03 - w01d05 start of JS - Fri
format of the classes until \~ weds, will be 2-a-days
	lecture in morning
	lecture in the afternoon

inventing this language
	user input (database - real time data)
	animations
	calculations
	ability to modify html/css
	user interactions
	asynchronous <-- allows for e.g., a tweet would be able to post && communicate from frontend to backend w/out the browser freezing
	
	frontend = html/css/js
	    jQuery <-- exists for manipulating the DOM much easier, e.g.,
	        because you know jQuery does NOT mean you know javascript

starting in-class project 

## 6 April 2015 - w02d01

JS \~ objects // 

example of a credit card, has the following properties
	number, exp date, name, type of card, etc.
	array[] wouldn't be helpful

objects are key-value, e.g.,
	var card = {
	    number: 234234,
	    expDate: '4/17',
	    name: 'kelsy g'
	};
	
	    biggeset difference between arr and obj, arr have specific order

for creating objects
	    var object = {}; 
	
	    var object = {
	        name: value
	    };

example:
//tyler's car wash
//moneyMade
//totalWashes
//open
//red, blue, green (occupied: true/false, status: 'working'/'broken')


var tylersCarWash = {
  moneyMade: 325345,
	totalWashes: 324,
	open: true,
	slots: {
	    red: {occupied: true, status: 'working'},
	    blue: {occupied: false, status: 'working'},
	    green: {occupied: false, status: 'broken'},
	}
};
 
//calories --\> 0,
//total carb --\> 2g,
//protein --\> 0
//vitaminb6 --\> 100%,
//ingredients --\> carbonated water, citric acid, sorbic acid
//servingsPerContainer --\> 2
//servingSize --\> 8.0 fl. oz
//name --\> zero ultra

var monsterDrink = {
  calories: 0,
	totalCarb: '2g',
	protein: 0,
	vitaminb6: '100%',
	ingredients: {
	
	    },
	servingsPerContainer: 2,
	servingSize: '8.0 fl. oz',
	name: 'zero ultra'
};

### to delete
	delete monster.calories
 
// can't delete a value without deleting it's key

to access values inside an object
	dot notation =  monster.protein
	bracket notation = monster['protein'];  <--- get the value or key of protein

a 'for in loop' \<-- loops over every key in your object

for(var key in monster) {
  console.log( key + ':' + monster[key]);
}
 
in order to you 'dot' notation. the thing to the left of the dot is an object


## 7 April 2015 - inClass w02d02

inClass - toyProblem: var combinator = function(firstName, lastName) {
	// combines them and returns them to a new array;

put 2 ways of doing the toy problem, followed by a recursion way in toyProblem w02d02

starting // WAR problem

// synchronous 
 
	var dan = function(x) {
	    x =  x + 3;
	    x = x * 5;
	    return x;
  }
 
example of twitter 
	// a callback, would be when twitter needs a way to show the new tweets
	        // the callback puts the tweeets back on the page

// if you're getting data from the server it doesn't freeze everything

### After-lunch lecture - prototypes

instead of having the sayHello fn for every new user, it's possible to create one instance in memory that the other reference it.

var CreateUser = function(email, pw, username) {
	this.email = email;
	this.pw = pw;
	this.username = username;
	};

'this' keyword ---\> object
  // you don't need to define the object (e.g., var obj = {};)

	this.
	  1. an object is created for us, called --> this
	    2. fn automatically returns 'this'
	    3. && and return for us.
!! whenever you invoke a function with the 'new' keyword, it automatically creates

// job interview, when creating with the 'new' keyword it:
	1. creates an object
	2. returns that object

// instead of JS creating a plain object with the 'this' & 'new'


### from inClass afternoon lecture w02d02
---
// pattern below is the maker pattern, function that creates an object
var createUser = function(em, pw, uname){
	    return {
	                email: em,
	                        password: pw,
	                                userName: uname,
	                                        sayHello: function(){
	                                                alert('Hello');
	                                                    }
	                                                     };
};

// you can create multiple users with the same createUser

var newUser = createUser('asdfasdf@gmail', 'testPW', 'ttesUser');
var newUser2 = createUser('testc@gmail', 'user1password', 'ttesUser1');

var sayHello = function(){
	    alert('Hello');
};

createUser.sayHello();

///

CreateUser.prototype.sayHello = function() {
	    alert('Hello');
};

// create a 'Person' constructor which takes in a 'name' and 'age' 
// and returns an object with both of those properties/value

var Person = function(name, age) {
	    this.name = name;
	        this.age = age;
};

// above is the CONSTRUCTOR

var me = new Person('tyler', 24);
var cahlan = new Person('cahlan', 30);

// can do me.name, and cahlan.name

Person.prototype.sayHellow = function() {
	    alert('Hello');
};


// to invoke with 'me', put == me.sayHello();
// cahlan ==== cahlan.sayHello();

Person.prototype.sayName = function() {
	    alert('My name is ' + this.name);
};

// when sayName is invoked, it says 'who invoked me'
//! to figure it out, left to the dot'.' and call-time
// e.g.,, left of  cahlan.sayName();  \<---to the left is 'cahlan'


// whenever you see the 'this' keyword, look to when the function was called
// and to the left of that keyword

// maker pattern = creat an object and return that object
//constructor these things do that

//? the 'this' keyword allows your functions to be more dynamic

// protypes live on functions, every function has a prototype

/\* end of inclassLecture \*/
---

## 8 April w02d03 - inClass morning
toy problem: 
// write a function here...

//...to make the below function invocation work

sum([1,4,2,5,2,8], function(total){
	return 'The total sum of the array is ' + total;
	{);

---
answer :
var sum = function(arr, cb){
	    var total = 0;
	        for(var i in arr) {
	                    total += arr[i];
	                        }
	                            return cb(total);
};

var arr1 = [1,4,3,5,2,8];

sum(arr1, function(total){
	    return 'the total sum of the array is ' + total;
});
---


// when splicing in an array, everything shifts, making it need a 'i--' to ensure everything is covered

### Closures
var cExample = function() {
	var cTest = 'Closed';
	};
	
	console.log(cTest);
	
	// end <-- above example will give an error because of scope
---
// browser uses the 'Window' object as global scope

var cTest2 = 'Open';

car cExample = function(){
	var cTest = 'Closed';
	console.log(cTest2);
	var dan = function(){
	    var cTest3;
	    };
};

*don't shadow variables*

### polluting the global scope
// by not declaring with var, you are putting functions on the global scope

! 'for' and 'if' expressions *DO NOT* create scopes

## 9 April 2015 - inClass lecture
	// tought by dave smith

why does JQuery exist?
	browser vendors had a hard time agreeing on certain features and document name
	
	started out as having a DOM (document object model). We should use css style - selectors to manipulate the dom

jQuery provides a nice abstraction

walk through the DOM \~

// where to put a <script></script>
JS/html/css parse from top to bottom
cdn (content delivery network)

through the DOM -
	by definition, html is just a giant string
	browser is a giant string parser
	the representation of the html/css in memory

first jQuery function to know:
	'ready' the dollar-sign $ <-- one of the few things js treats just as a variable, $ is just like letter a,b,c
	
	all jquery things today will be $
	the document object - has a lot of options to be able to manipulate the dom
	
	$(document).ready(function() {
	    console.log('the document is ready now');
	});
	
	generally put all of your code inside a document.ready

### how to select elements on page w/jQuery
  var element = $('#username');

	jquery returns a jquery object
	jquery can match multiple items
	
	$(document).ready(function(){
	    var element = $('.welcome');

### actual structure changes
$('#container').prepend('<h3>this is an h3 warning </h3>');

// removing more items then intended is easy to do in jQuery

### click events
$(document).ready(function() {
	$(#submit

});


### event delegation & 'bubbling'

	// can do sudo states, e.g., if($('h1').is(':visible'))

### for interacting with the user
$('body').on('click', 'button', function(event) {
	console.log('the users password in', $('#password


## \*    ajax = how you send http requests to the server \*

when pulling out a .val(); \<-- it will get the first one in the DOM

the val() can you in a lot of circumstances

xss attack == cross-type browser attack

$('body').on('click', 'button', function(even){
$('#container').find('div').remove();
});
 
 
//body

// all jQuery is, is a bunch of jQuery functions, that work on jQuery objects

jQuery UI \<-- for visual things

### chaining
## comparing to Angular
	abstraction (in software), take something complicated and put a level of abstraction to be able to manage complicated problems
	
	
	bldg a web app
	    lowest most complicated 
	
	                        Angular1
	                        jQuery
	                        DOM


two separate concerns
	1. html
	2. js/logic
						 


*one of the biggest challenges* creating the correct abstractions for your applications

// for smaller projects google
	what you need and 'google cdn'



application programmers interface (api)
 those publicly available functions that you interact with

focus refers to the element that the user is clicked on

## start of mini-project
// go back and check css

## 10 April 2015 - w02d05

// begin $.ajax jQuery 

POST - GET -

sample code from app.js in twitter-clone: 
$(document).ready(function(){

	    $('#tweet-controls').hide();
	
	        $('.tweet-compose').on('click', function(){
	                    $(this).animate({height: '5em'});
	                            $('#tweet-controls').show();
	                                });
	
	            $('.tweet-compose').on('keyup', function(){
	                        var text = $('.tweet-compose').val();
	                                var charCount = 140 - text.length;
	                                        $('#char-count').html(charCount);
	
	
	                                                                    if((charCount <= 10) && (charCount >= 0)) {
	                                                                                    $('#char-count').css('color', '#C20016'); }
	                                                                                            else {
	                                                                                                            $('#char-count').css('color', '#999');
	                                                                                                                    }
	
	                                                                                                                            if(charCount < 0) {
	                                                                                                                                            $('#tweet-submit').prop({disabled: true});} 
	                                                                                                                                                    else {
	                                                                                                                                                                    $('#tweet-submit').prop({disabled: false});
	                                                                                                                                                                            }
	
	                                                                                                                                                                                    });
	
	                        // } else if (charCount === 0) {
	                                        //  $('#char-count').css('color', '#999');
	                                                    //  $('#tweet-submit').prop({disabled: true}); 
	                                                                // } else if (charCount >= 0) {
	                                                                                //  $('#tweet-submit').prop({disabled: false});
	                                                                                            // }
	
	
	
	
	
	
	                                                                                                    // if(charCount === 0) {
	                                                                                                                //  $('#tweet-submit').prop({
	                                                                                                                            //      disabled: true,
	
	                                                                                                                                                //      });
	                                                                                                                    //  }
	
	                                                                                                                        // });
	
	
	
	
	
	
	});

<!----end ----->


## 12 April 2015 - sun
	made minor edits for w03d01 mini-project
	    'step 1'. parenths close, ..'html', skeleton, application.

angular apps - 
	start codeschool
	+- finished pre-reading
	 - look @ tutsPlus, finish project


## 13 April 2015 - mon - w03d01
toy problem: write a function called Reverse that takes in a string and reverses that string without using .reverse on the Arrays prototype

var reverse = function(str){
	    var stringReverse = '';
	        for(var i = str.length; i > 0; i--){
	                    stringReverse += str.slice(i - 1, i);
	                        }
	                            return stringReverse;
};


// mine
var Reverse = function(str){
	    var newString = [];
	        for(var i = 0; i < str.length; i++){
	                        newString.unshift(str.charAt(i));
	                            }
	                                return newString.join('');
};

// start of angular

## why do we have Angular -
	1. separate logic
	2. templating (e.g., dashboard-view, and then swap out users
	
	// example of a template
	
	e.g.,
	<!---setting--->
<div>
    <span> username: {{user.name}} </span>
    <span> email: {{user.email}} </span>
</div>

(5 parts to angular)

AngularJS Fundamental in 60-ish minutes (video);

// inClass from video
	directive - extends HTML (teaches HTML new Tricks)
	filter - filter data
	view - HTML Document / Template
	controller - logic layer (controls the view)
	$scope - Object


whenever you create a new controller, you get a $scope object

var app = aangular.module('nameOfModule', []);

app.js

### start of mini project - babies first angular
## start of project - angular-friends - w03d01
// need to figure out steps 5/6 of project
## 14 april 2015 - w03d02
toy problem: write a function that returns the factorial of a number // the number 5 will return 5*4*3*2*1 ===\> 120

var numberChange = function(number){
	    var thing = 1;
	        for(var i = number; i > 0; i--){
	                    thing = thing*i;
	                        }
	                            return thing;
};

## start of yesterday's review of project;
// building a large project with loads of controllers, would be messy

// the controller --\> controls the view
// doing things with the server requests = service

deals with view = controller || server request = service

this controller uses only these services
// you don't want to load all the services in all of the controllers

anything you want to inject you insert as a parameter
a service won't re-run the code once it is made
	// a service is created once, used many times

design pattern:
	//(state = state of being, e.g., you're logged in, that's a state)
	
	data should be in services (states);

want to put logic in something. (method = function lives in an object)

if you're in the view, the only thing you can point to is the $scope


## variables in the .service
a maker function would be the way that 

## start of w03d02 mini-project
## 15 april 2015 - w03d03
toy problem: write a function called simpleSymbols that takes in a string parameter and determines if it is an acceptable sequence by either returning the string true of false. the str param will be composed of a + and = symbols with several letters between them (ie ++d+===+c++==a) and for the string to be true each letter must be surround by a + symbols. so the string to the left would be false, the string will not be empty and will have at least one letter

// a true statement would be +d+===++a++=+b+=

// one answer not using regex
var simpleSymbols = function(str){
	    for(var i = 0; i < string.length; i++){
	                if(string.charAt(i) !== "=" && string.charAt(i) !== '+'){
	                        return str.charAt(i-1) === '+' && str.charAt(i+1) === '+';
	                                }
	                                    }
};


// start of a review
\~ use var if you want it to be private, helps prevent pollution

## start of w03d03
HTTP / JSON / PROMISES

### starting off with http
	--> datacenter delivering content to your computer

example of callback

function getPuppy(cb){
	//remember, this is an async function
}

getPuppy(function(puppy){
	render(puppy)   
})


// promise version
function getPuppy(){
  // build and return a promise object
}

var puppyPromise = getPuppy()

puppyPromise.then(//what to do if work, //what do if didn't work)
puppyPromise.then(function(puppy){
	render(puppy)
}, function(err){
	console.log('ohnothisisbad');
})



{
	then: function(){...}
	catch: function(){...}
}


 --\> standardization ( js A+ promises spec )

### promises can be chained, instead of a nested crazy callback


# 16 april 2015 -- w03d04

toy problem / given an arbitrary input string, return the first non-repeated character in the string. the example: firstNonRepeatedCharacter('ABA'); // =\> 'B';
firstNonRepeatedCharacter('AABCABD'); // =\> 'C'


// dylan's answer
var nonRepeater = function(str){
	    var index=[];
	        var count;
	            str.split('').forEach(function(letter, i) {
	                        count=0;
	                                str.split('').forEach(function(latter){
	                                                if(leter === latter) {
	                                                                    count += 1;
	                                                                                }
	                                                                                        });
	                                        index.push(count);
	                                            });
	                return str[index.indexOf(1)];
};



// \<-- get other solutions for G+ --\>


## 17 april 2015 w03d05
review of w03d04 iTunes api project

$q creates deferred, deferred generates your promises

// everything that has been registered with the .then, will fire after
// the promise is RESOLVED

// some inClass code
\<!DOCTYPE html\>
<html lang="en">
<head>
	<meta charset="UTF-8">
	    <title>$q demo</title>
	    </head>
	    <body ng-app='qDemo'>
	        <div ng-controller='qDemoCtrl'>
	                <input type="number" ng-model='testNumber'>
	                        <button ng-click='asyncAction(testNumber)'>Async</button>
	                                <h1>{{ newNumber }}</h1>
	                                    </div>
	
	                                            <script src='https://cdnjs.cloudflare.com/ajax/libs/angular.js/1.3.15/angular.js'></script>
	                                                <script type="text/javascript">
	                                                    var app = angular.module('qDemo', []);
	
	                                                        app.controller('qDemoCtrl', function($scope, $q, $timeout){
	                                                                    var asyncAction = function(number) {
	                                                                                    var deferred = $q.defer();
	                                                                                                $timeout(function() {
	                                                                                                                    deferred.resolve(number);
	                                                                                                                                });
	                                                                                                         return deferred.promise;
	                                                                                                            })
	
	                                                            $scope.fireAsync = function(number){
	                                                                        var promise = asyncAction(number);
	                                                                            });
	
	
	
	
	
	    </script>
	
	    </body>
	    </html>
### end of inClass

## 18 April 2015 - sat
todo: 
 - review angular w03
 - wireframe logYourlog

## 19 April 2015 - sun
 - update the angular shared module on Github
	 - make PSD and Sketch files for templates

## 20 April 2015 - mon - w04d01
- angular js routes

toy problem w04d01 - 
  write a function called ABCheck that takes a string parameter and returns the string  true if the characters a and b are separated by exactly 3 places anywhere in the string at least once (e.g., 'lane borrowed' would result in true because there is exactly three character between a and b), otherwise return false.
toy prob answer:
 
	var ABCheck = function(str){
	    var arr = str.split('');
	    for(var i = 0; i < arr.length; arr++){
	        if(arr[i] === 'a'){
	            if(arr[i-4] === 'b' || arr[i+4] === 'b'){
	                return true;
	                }
	        }
	    }
	    return false;
	}

// end ---\> of first example

// second example:
  var ABCheck = function(str){
	    var newStr = str.toLowerCase();
	    var arr = str.split('');
	    for (var i = 0; i < arr.length; i++){
	        if (arr[i] === 'a' || arr[i] === 'A' && arr[i+4] === 'b'){
	            return true;
	        }
	    }
	return false;
}

// benefit of the array vs. string, generally if you want to alter the string, you want to split() it and put it into an array

// beginning of routing lecture
- begin review of angular (from w03)
angular === a framework
	a framework === a skeleton you build your app around, and it also abstracts
	angular takes care of a lot of things, including data binding, $http, etc.
	ANGULAR:
	    controller - the glue between the service and the view
	        - $scope - anything you want in the view, you need in the $scope
	    service - where data is getting manipulated and stored, anything that doesn't deal directly with the view (e.g., ajax requests, other data, etc.)
	        promise - it uses a callback functions. promises solves the problem that lets asynchronous programming happen.
	            promise is just an object
	            handles async programming

# routing
	routing - ~handling the path, and providing the user with the proper html template and information
	    specific to angular
	        - angular has it's own routing service

TODO:
	-watch routing tuts ~

# 21 April 2015 - w04d02
toy problem:
	write a func() that generates an arr of integers of the Fibonacci sequence up to i = 100. Fib seq defined by Fn = Fn-1 + Fn-2
	then write a func() to check if given num is in the Fib seq, return 'yes' or 'no'

// answer 1:
  var fibCheck = function(fn1, fn2){
	    var sequence = [fn1, fn2];
	    for(var i =1; i < 100; i++){
	        var newNum = sequence[i] + sequence[i-1];
	        sequence.push(newNum);
	    }
	    if(sequence.indexOf(num) !== -1){
	        return 'yes'
	    } else {
	        return 'no'
	    }
	
	    console.log(sequence);
	}

\<---end of answer one ---\>
### review w04d01 - nbaRoutes
 step 2: going into teamService.js
 
	var app = angular.module('nbaRoutes');
	
	app.service('teamService', function($http, $q){
	    this.addNewGame = function(gameObj){
	        var url = 'https://api.parse.com/1/classes/' + gameObj.homeTeam;
	    if(parseInt(gameObj.homeTeamScore) > parseInt(gameObj.oppentScore)){
	        gameObj.won = true;
	    } else {
	        gameObj.won = false;
	    }
	    return $http({
	        method: 'POST',
	        url: url,
	        data: gameObj
	    });
	    };
	    //will get team data
	    this.getTeamData = function(team) {
	        var dfd = $q.defer();
	        var url = 'https://api.parse/1/classes/' + team;
	        $http({
	            method: 'GET',
	            url: url
	        }).then(function(data){
	            console.log(data);
	            var results = data.data.results;
	            var wins = 0;
	            var losses = 0;
	            for(var i = 0; i < results.length; i++){
	                if(results[i].won){
	                    wins++;
	                }else if (!results[i].won){
	                    losses++;
	                }
	            }
	            results.wins = wins;
	            results.losses = losses;
	        })
	          return dfd.promise
});

### step 3: in
app.js

app.config(function($routeProvider, $httpProvider){
	$httpProvider.interceptor.push('httpRequestInterceptor');
	
	$routeProvider
	.when('/', {
	    templateUrl: 'js/home/homeTmpl.html',
	    controller: 'homeCtrl'
})
	.when('/teams/:team', {
	    templateUrl: 'js/teams/teamTmpl.html',
	    controller: 'teamCtrl'
	    resolve: {
	        teamData: function(teamService) {
	            return teamService.getTeamData();
	    }
	})
	<!---rest is in subl file --->

## start of directives lecture - w04d02
 

## 22 april 2015 - w04d03

toy problem:
	find the only item that occurs an even number of times in an array. if there is more than one item that occurs an even number of times, just return one of them.
	    // e.g., var onlyEven = evenOccurence([1,6,2,4,4,5,6,8,9,6]);
	                console.log(onlyEven); // 4

<!-- start of first answer -->
var evenOccurence = function(arr){
	var times = {};
	var x = 0;
	while( x < arr.length) {
	    if(!times[arr[x]]){
	        times[arr[x]] = 1;
	    } else {
	        times[arr[x]]++
	    } x++
	} for(var i in times) {
	    if (times[i]%2 ===  0) {
	        return i;
	    }
	}
}
<!---end of first solution -->

## start of Dave Smith Lecture
	--> notes in rhodia

### start of review w04d02 - in subl
## 23 April 2015 - w04d04
toy problem:
  write a function that accepts a number, n, and returns the nth Fibonacci number. use a recursive solution to this problem; if you finish with time left over, implement an iterative solution.

	// below example is if it starts @ 1;
	*nthFibonacci(2); // => 2
	*nthFibonacci(3); // => 3
	*nthFibonacci(4); // => 5
0,1,1,2,3,5,8,13,21,34...


// recursive function is a function to call itself, but you have to have it tell itself, up to a point (or it will run forever);

a good use case, would be using a nested loops?

<!--start of answer one -->
  var findFib = function(n){
	    if(n === 0 || n ===1){
	        return 1;
	    } else {
	     return findFib(n-1) + findFib(n-1);
	    }
	};

<!--end of answer one -->


### start of lecture w/Chris for fireBase
// people have been moving away from relation databases because of scaling issues (tons of data, having to join together, taking a bunch of nodes, which is being pulled from each table)
	e.g., facebook is going to want some data in relation database, but other things in noSQL solutions. 
	    you do lose some analyzing, because you have to loop through all of the objects

	 
## 24 april 2015 - w04d05
// start of lecture by @chrisesplin, chris@quiver.is

## 28 April 2015 - w05d02
Giphy Project toDo - api interactions
	        - get giph from user input
	        - display giph
	        - ability to save giph
	            -saved giphs will only display still image
	        - show giphy links underneath image to embed easily


## 30 april 2015 w05d04
// start of node topic //

## 1 may 2015
in-class notes

//
var http = require('http');
var server;

server = http.createServer();

//routing
server.on('request', function(req, res) {
	if('GET' === req.method){
	    res.end('You got me!');
	    return;
	
	}
	if (
	res.end();
});

server.on('listening', function(){
	console.log('ready to accept requests');
});
server.listen();

## 2 may 2015
	-go over express()
	-start wireframes
 
# 4 may 2015 -- w06d01
	toy problem w06d01 - http://jsfiddle.net/cahlan/jfba13a6/

answer jsfiddle.net/cahlan/2ub9u8fj

## 5 may 2015 -- w06d02
// toy problem w06d02 -- write a function that can only be invoked once //

//--example one--// -- not correct

var timesInvoked = 0;

var oneTime = function(){
	if(timesInvoke > 0){
	    return 'cannot be invoked more than once'
	}
	else {
	    timesInvoked++;
	    return ' here is my function doing stuff';
	}
}

//--example two--//

var singleton = (function(){
	function createdFunction(){
	    var myFunction = function(){
	        console.log('created only once')
	    }
	return createdFunction;
	}
	return {getFunction:function(){ 
	    if (createFunction)};
})

## 6 may 2015 
	toy problem w06d03
	make the following code work:
	var counter = getCounter();
	counter(); //2
	counter(); //4
	counter(); //6

var getCounter = function() {
	var num =0;
	return function(){
	    num += 2;

## 7 may 2015
	toy prob: w06d04 - 
	recreate the Array prototype push method. if you get done, also do pop. hint: use the *this* keyword

answer/
	Array.prototype.push = function(item){
	    this[this.length] = item;
	    this.length++;
	    return this.length;
	};
	
	nameOfArray.push('item')

## 8 may 2015
	todo:
	    -review mongodb && mongoose
---

## 9 may 2015
	saturday
	    -wireframe
	    -setup environment variables
	    -google oauth2
	        -doublecheck fitbi

## 10 may 2015
	-went over pluralsight - mean stack
	-wireframe everyones' apps
	-pair program

## 11 may 2015
	---
	too sick to go in, suspect flue from part-timer
	---

## 13 may 2015
 ---
 still sick, day has been blur of day/nyquil
 ---

## 14 may 2015
	---
	double-check apis on mashape - 
	    refactore giphygift
	---

 
asdfasdf
:“


## 15 may 2015 -- inpoint
## 18 may 2015 --
	-utemp expansion / exposition

## 21 May 2015 - w08d04
	-refactor code - 

## Sass & Compass Notes - (https://www.youtube.com/channel/UCPgvHY8Q2ZaYxYCeJvYd45w) \<-- youtube playlist
// use .scss, not .sass

### Variables -
	$main_color: #023e54;
	.nabar {
	    background: $main_color;
	}

### Nesting - group rules that are related to each other (similar to @media queries)
	e.g.,
	.pixgrid {
	    ul {
	        margin: 0;
	        etc:
	        li {
	            float: left;
	            etc:
	        }
	        img {
	            max-width: 96px;
	            cursor: pointer;
	        }
	    }
	}

### Operators
	$border_thickness : 1px;
	$thicker : $border_thickness*5;
	
	.sidebar {
	    @if ($border_thickness<=1) {
	        background-color: red;
	    } @else {
	        background-color: yellow;
	    }
	}
	
	.sidebar {
	    background-color: red;
	}

### Mixins (aka: functions)
	@mixin rounded( $radius: 10px) {
	    -webkit-border-radius: $radius;
	    border-radius: $radius;
	    background-clip: padding-box;
	}
	
	ul {
	    padding: 0;
	    margin: 0;
	    list-style: none;
	
	        li img {
	      display: block;
	        @include rounded(20px);
	        }
	}

### compass = a framework with pre-built mixins / solve common problems
// 6 june 2015
	-get UI for tree finished by COB monday
	-re-work skeletong css && animate.css

---\> process notes / separate into categories / make angular sortable app

## notes for group project
Features
	-make folder public
	    -subscribe/follow to folder
	            -save to your bookmarks
	                -public / private(following) folders
	
	                // chrome bookmarks --> save to your site
	                    -doesn’t effect
	
	                    -admin (person who created bookmark)
	
	                    sharing:
	                        userID
	                                -publicID
	                                        is admin?
	                                                    yes==edit
	                                                                no==error
	
	                                                                // Would you like to make edits/changes?
	                                                                        -->copy to your bookmarks
	                                                                                —> know that it 
	
	                                                                                make folder public --> changes ‘status’ on folder
	                                                                                    --loops through anything ‘public status’ - puts in feed
	                                                                                            --follows == adds username to folder in mongo



### notes about uiTreeExample
in basic-example.html
	add input ng-model='searchText' line 77
	add filter:searchText - line 87
 *basic search working*

!! note to self - the colors generated in sketch versus the color picker within sublime are *NOT* the same. hex from Sketch looked nicer (slightly flatter)

	in angular - commenting out after {{somethingInBraces}} won't effect it, need to delete/remove the code

!! note to self 
	- adding a background-image: url(/folder/etc/img.png) <-- add the root '/'
//\\
followup with employer listing, forward to krissy
