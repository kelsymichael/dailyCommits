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




