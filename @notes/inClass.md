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

### FLEXBOX <-- the future for layouts
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















