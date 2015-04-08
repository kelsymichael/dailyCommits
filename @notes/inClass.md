# INCLASS NOTES - DevMountain 

## Git
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

	<footer></footer>		<— can be used in multiple places 

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

### inline styles  <—- don’t use it
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

# 2015-04-01 - InClass w01d03 - Wed

## inclass start of project -- going over problem 3
	
	nesting was used for the logo, (example inClass) container>header>logo

	overall it was how I did it, still should go back to finish it

## InClass Lecture

	css shorthand - 
		margin: 0, 0, 0, 0; --> margin: 10px 20px;
		margin: top, bottom;

// review of D02 assignment - png1 --> saved on CodePen

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
change things w/out commiting

Has auto-suggestion, unless it's looking for a specific number value --> 'inherit/initial/~sometimes normal

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


### positioning --> in codePen

 ! as a general rule, you DON'T want to use positioning to get it exactly where you want

	default position = static
		relative = relative to whatever it would normally go, it's relative to that
		absolute = based on the BROWSER WINDOW
			// instead of 'where would this normally go, it's looking at how is this offset from the browswer window

					relative = where it would be be
					absolute = from the browser window

HOW TO CHANGE HOW ABSOLUTE WORK
	! change it's parent to RELATIVE, this will make it ABSOLUTE from it's parent instead of browser window


### display --> codepen

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

### FLEXBOX <-- the future for layouts  // ! in codepen.io add 'display: -webkit-flex;' in addition to display: flex;
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


c flex-basis: ; <-- the natural width of the elements
c flex-grow: 1 ; <-- arbitrary number
c flex-grow: 2 ; <-- how much these items will grow in relation to each other

c flex-shrink: 1; <--arbitrary, similar to flex-grow
c flex-shrink: 2; <--shrinks twice as much as the others


####shorthand properties
c flex: growValue shrinkValue basis; <-- this 'flex:' shorthand expects 3 values
	flex: 1 1 450px;

// shorter shorthand

to get something twice as wide than something, use this shorthand:
c flex: 1;
	flex: 2; <--twice as wide as ^

####flex-direction
p flex-direction: row || column;
	flex-direction: row-reverse;
	flex-direction: column-reverse;

####using padding / margin with flexbox
just as normal, use p container

set min-width on p container to effect everything 
	setting for wrapping on the other line
	p flex-wrap: wrap; <--default is nowrap
		flex-wrap: wrap-reverse; <--the fourth item would jump to the top as it gets smaller // probably won't use it that much

####flex-flow: shorthand for flex-direction: & flex-wrap
flex-direction (horizontal or vertical) flex-wrap (wrap or wrap-reverse)
	// ^ are the flow

// ! can set flex-basis: auto;

####flex-box vendor prefixes
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

#2015-04-02 -InClass w01d04 - Thu
			
review of MDN - for reference 

###tables
 // don't use this unless you have actual tabular data // 

	<table>
		<tr>
			<td>table1</td>
			<td>cellData</td>
		</tr>
	</table>

display: inline / inline-block / or **display table**
	using display: table is fine, but don't use it html unless actually making a table

p	display: table;
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

###sudo classes
	.button:hover
	.button:active	<-- when you actually click it
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

.button:nth-child(1 <--where you want to start)
.button:nth-child(2n + 1) {
}

### media quirier && responsive design

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


###different selectors

.box.blue  ( <-- select only items with the class both .box ** .blue )

.box + .box  ( <-- will be applied to any .box that has .box PRECEDING it, so the first .box will not have the style applied to it ).

.parent > .box  ( <-- direct decendent ) 

.parent .blue  ( <-- item that is .blue which is nested in .parent )


 
### chrome dev tools
	using the inspector you can toggle :hover, :active, etc., and allows you to edit while looking at that state

# TOY PROBLEM

  css-selectors fromt : https://flukeout.github.io
	second one finished

### @Home flex tut
p display: flex;
p flex-direction: column; <--default is row
									row-reverse; <--reverses the c's
									column-reverse: <--reverse the c's

c flex: 2  <--twice as big as 2
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

!// <-- add 10px of padding on the body to show it re-size !//

media query -
	@media (max-width: 600px) {
		.item1 { order: 4; }
		.item1 { order: 1; }
		.item1 { order: 1; }
		.item1 { order: 1; }
}


###adding content:
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

p flex-wrap: nowrap; <--default 
	this defines how you want the container to react 

p flex-wrap: wrap <--this will react with the the container to make the items react

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

p align-content: flex-start; <--aligns with the 'start' && the example it would be next to the other content
	instead of evenly spacing the c's in the container, it would get rid of that space

in the example, p flex-flow: COLUMN wrap; <--

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

###justifying content
the justify content deals with the MAIN axis (versus the CROSS axis of the 

example they take off the flex property in three of the c's, but keeps it on item 4

p justify-content: center; <--this allows to adjust the other axis, i.e., rows deal with horizontal on the align-content, while justify-content deals with vertical

// justify-content along main
	align-content along cross

###align-items
allows you to align each individual flex-item to cross-axis instead of the entire row or column as a whole

a way to align items based on the height of those items (default = stretch)

p align-items: flex-start; <--this gets rid of the stretch and allows the example items to be the height of the content (and not the full height of the container

	// allows to retain their natural height instead of all of the columns/rows being the same height

	p items-align: center; <--put them in the center

	p items-align: baseline; <-- when the items have padding/margin, it changes the content, so the headers of the content are all aligned, in this example the headers
	
	property called 'align-self'

	c align-self: flex-end; <--this allowed the example to have .item1 ignore the other three .items that were aligned to the baseline

// had main .container display: flex; <-- that is a div around everything, then followed other containers



## 2015-04-03 - w01d05 start of JS - Fri

format of the classes until ~ weds, will be 2-a-days
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

# 6 April 2015 - w02d01

JS ~ objects // 

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
	
//calories --> 0,
//total carb --> 2g,
//protein --> 0
//vitaminb6 --> 100%,
//ingredients --> carbonated water, citric acid, sorbic acid
//servingsPerContainer --> 2
//servingSize --> 8.0 fl. oz
//name --> zero ultra

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

a 'for in loop' <-- loops over every key in your object

for(var key in monster) {
  console.log( key + ':' + monster[key]);
}
	
in order to you 'dot' notation. the thing to the left of the dot is an object


## 7 April 2015 - inclass w02d02

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

'this' keyword ---> object
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


###from inclass afternoon lecture w02d02
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
// e.g.,, left of  cahlan.sayName();  <---to the left is 'cahlan'


// whenever you see the 'this' keyword, look to when the function was called
// and to the left of that keyword

// maker pattern = creat an object and return that object
//constructor these things do that

//? the 'this' keyword allows your functions to be more dynamic

// protypes live on functions, every function has a prototype

/* end of inclassLecture */
---



