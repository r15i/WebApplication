 Css or Cascading style Sheets(css)
 is the the standard for defining the presentation of documents written in HTML 

[[HTML5]] $\rightarrow$ structure
[[CSS3]] $\rightarrow$ presentation 
[[JavaScript]] $\rightarrow$ behaviour

**Benefits**:
- precise type and layout controls 
- less work 
- reliable browser support 

## Css theory 

- exist an invisible box around every HTML element 
- CSS allow you to create rules that control the way that each individual box(and the content of the box ) is presented  
![[Pasted image 20240603143703.png]]
###### Types of telements 
- **inline** elements(the red boxes): elements flow with the text and do not start on a new line
``` Html  
<b>, <i>, <span>, <img>
``` 
- **block** elements(the green boxes): look like they start a new line

#### Apply styles to the document 
- External style sheets (as a separated file )(usually the best choice):
``` HTML 
<!--self closing tag -->
<link href="css/styles.css" type=“text/css" rel="stylesheet" />
``` 
- Embedded style sheets (as a tag in HTML)(bad )
- Inline (as an attribute )(bad)

##### Modular approach (multiple style sheets)
To build an organized structure of styles usually we have a modular approach 
in 2 ways:
- using the `<link>` tag 
- using : `@import url("typography.css")` **directly in css**


# Stylesheets instructions 
A stylesheet is made of more style instructions called rules 
each with :
- A **selector**: The elements interested by the rule (in Red)
- A **declaration**: The effective style (in Green ) 
![[Pasted image 20240603145957.png]]

#### Selector
Various types of selector
![[Pasted image 20240603150139.png]]
![[Pasted image 20240603150212.png]]
![[Pasted image 20240603150337.png]]
##### Identifier of pseudo-classes 
Pseudo-class selectors are used to apply styles to elements in certain states like :
```CSS 
/*first element of a list */
li:first-child{
}
/*color of the string of a link */
a:link {
color: maroon; }
/*color on visited link */
a:visited {
color: gray; }

/*change based on User input events */
/*on user focus*/
input:focus {
background-color: yellow;}
/*on mouse over */
a:hover {
color: maroon;
background-color: #ffd9d9;}
/*on user use of the element */
a:active {
color: red;
background-color: #ffd9d9; }
```
###### Group Selector 
to apply with multiple rules
`h1, h2, p, em, img { border: 1px solid blue; }`
#### Declaration  
The  declaration  is made of a **property:value** pair 
``` CSS 
{
font-size: small;
font-family: sans-serif;
}
```
### CSS rules of inheritance 
if there are two or more rules that apply to the same element it will be applyed the declaration based on: 
- **Specificity**: if a selector is mode **specific** than the other it will take over 
- **Last rule**: if the two are identical, the latter of will take precedence 
- 
to raise the importance of a property we can use the **keyword** `!important`
##### Rule of thumb for inheritance 
- In general,properties related to the styling of text (font size, color, style) are passed down.  Borders, margins, backgrounds, padding and so on are **not** inherited  
- we can force a lot of propreties to inherit by using `inherit` keyword for the value of property to make it inherit the value from the parent
##### hierarchy of styles 
the browser select the style to apply in this order:
- Browser defaults 
- User Style Settings 
- linked External 
- Imported 
- Embedded 
- Inline style specification 
- any `!important` by the author 
- any `!important` by the user
# Color 
There 4 ways to specify the color in css :
```CSS 
/* rgb value */
p {

 /*hsl(hue,saturation,lightness) and rgb */
 color:hsl(0,0%,78%); 
 color: rgb(100,100,90);} 
 /*hsla(hue,saturation,lightness,opacity) and rgba*/
 color:hsla(0,0%,78%,0.5); 
 color: rgba(100,100,90,0.5);}
/* hex code */
 color: #ee3e80;
/* color name */
 color: DarkCyan;
/*level of opacity */
 opacity : 0.5;
} 
```
# Text 
**Serif** $\rightarrow$  add extra details on the end of the main strokes of the letters 
**Sans-Serif** $\rightarrow$ Serif with straight ends to letters and with a cleaner design 
**Monospace** $\rightarrow$ every letter have the same width
**Cursive / Fantasy** $\rightarrow$ simulate cursive and used for headlines 

**To nothe that a tyeface need to be installed on the pc so usually sites rely on the dafault fonts given by the browser to avoid have problems**
Is much more common to specify the font family to allow a better portability 
```CSS 
body {
font-family: Georgia, Times, serif;}
h1, h2 {
font-family: Arial, Verdana, sans-serif;}
.credits {
font-family: "Courier New", Courier, monospace;
}
```
we can both use the **percentages** or **pixels** as unit of the size of the text 

# The box Model 
Every element in a document generalises a box to wich different propreties can be applied:
- control the dimension 
- create rounded borders 
- set margins 
- show and hide boxes
![[Pasted image 20240603161038.png]]
```css 
/* sizing the box*/
p{
width: 500px;
height: 150px;
padding: 20px;
border: 2px solid gray;
margin: 20px;
} 
```
##### Units of measure of the box 
- **Pixels**: they allow designers to accurately control the box size.
- **Percentages**: the size of the box is relative to the size of the browser window or, if the box is encased within another box, it is a percentage of the size of the containing box.
- **Em**: the size of the box is based on the size of text within it

##### Overflow property 
Set how the text react when it overflow from the parent element in wich it is 
- visible: default value (it goes over the marigin)
- hidden: the content that does not fit does not appear beyond the edges of the element’s content area.
- scroll: when scroll is specified, scrollbars are added to the element box 
- auto: allow the browser to decide how to handle overflow  
### Padding 
parameters for padding  dimension (can be still percet or pixel ) 
``` css 
/*all in one settings*/
padding: 10px 5px 3px 1px;
/*padding settings*/
padding-top:10px;
padding-right:5px;
padding-bottom:3px;
padding-left:1px;
```
### Borders 
parameters of border:

##### Width 
```CSS 
border-width:thin;
border-width:medium;
border-width:thick,

border-width: 2px 1px 1px 2px;
/*OR*/
border-top-width 10px;
border-right-width 10px;
border-bottom-width 10px;
border-left-width 10px;
```
#### border-style
Border style property values :  
solid: a single solid line
dotted: a series of square dots
dashed: a series of short lines
double: two solid lines
groove: appears to be carved into the page
ridge: appears to stick out from the page
inset: appears embedded into the page
outset: looks like it is coming out of the screen
hidden / none: no border is shown 

and still use all `border-topstyle, border-left-style, border-right-style, border-bottomstyle`

```css 
/* on the four borders */
bordercolor: darkcyan deeppink darkcyan deeppink;
h1 { border-left: red .5em solid; }
h2 { border-bottom: 1px solid; }
p.example { border: 2px dotted #663; }
```
#### Margin 
for the marigin applies the same rules than for the border and padding 
```css 
p { margin: 20px;}
p#B {
margin-top: 2em;
margin-right: 250px;
margin-bottom: 1em;
margin-left: 4em;}
```
### Interesting tags 
![[Pasted image 20240603164750.png]]

# Display roles 
Display roles defines the type of element box an element generates in the layout, it is a very important css properties for controlling the layout.
essentially set **how** and if it **gets** displayed 

- `display:none` remove the object (without leaving the blank space `visibility:hidden`)
- `display:inline` set he display of the elements as horizontal (useful for menus)

# Floating and Positioning 

