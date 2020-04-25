# CSS (CASCADING STYLE SHEETS)

Created by Vince Chang </br>

Here is where I post useful information on CSS. Stylesheet language used to
describe the presentation of a document written in HTML or XML

#### LEARNING FLEX BOX & CSS GRID

- [Flex box defense](http://www.flexboxdefense.com/)
- [Flex box froggy](https://flexboxfroggy.com/)
- [Git Repo w/ Useful Info](https://github.com/jen4web/fem-layout)
- [Flex box Resources](https://github.com/jen4web/fem-layout/blob/master/resources/resources.txt)
- [Web Responsive Design](https://alistapart.com/article/responsive-web-design/)
- [Box Sizing Border Box](https://www.paulirish.com/2012/box-sizing-border-box-ftw/)

#### THE RUNDOWN

- **Document**: Usually a text file structured using a markup language (HTML) or
  XML/SVG
- **CSS Properties**:
  - Values set to update how HTML is displayed
- **CSS Selector**:
  - Select which elements to apply property values to

#### HOW DOES CSS WORK

The browser converts HTML and CSS into the DOM, then browser displays DOM

1. Load HTML
2. Parse HTML
   2a. Loads CSS - Parse CSS, then goes to 2b
   2b. Creates DOM tree - Display

#### ABOUT THE DOM (DOCUMENT OBJECT MODEL)

- Tree Structure
- Each element, attribute, and piece of text becomes a DOM node
- Some elements are parents of child nodes and child nodes have siblings

#### CSS SELECTORS

1. **Simple Selector**:
   - Match one or more elements based on element type, class or id
2. **Attribute Selector**:
   - Match one or more elements based on their attribute values
3. **Pseudo Classes**:
   - Match one or more elements that exist in a certain state such as an
     element that's being hovered over
4. **Pseudo Elements**:
   - Match one or more parts of content that are in a certain position in
     relation to the element
5. **Combinators**:
   - Ways of combining 2 or more electors in useful ways for specific
     selections
6. **Multiple Selectors**:
   - Idea is that you can put multiple selectors on the same css rule separated
     by commas

```css
.class #id * universal selector that applies to all elements;

[attr] = select all elements with the attr
[attr=val] = select all elements with the attr, but only if the value is val
[attr~=val] = select all elements with the attr, but only if val is one of a
space separated list of words contained in attr's value
[attr^=val] = select all elements with attr for which the value STARTS with
val
[attr$=val] = select all elements with attr for which the value ENDS with val
[attr*=val] = select all elements with attr for which the value contains the
SUBSTRING val
```

#### PSEUDO CLASSES

- Keyword added to the end of a selector preceded by a colon
- Specify add style to a selected element, but only when it's in a certain state
- Ex. When hovering over an element

| PSEUDO CLASS        |
| ------------------- |
| :active             |
| :checked            |
| :default            |
| :dir()              |
| :disabled           |
| :empty              |
| :enabled            |
| :first              |
| :first-child        |
| :first-of-type      |
| :fullscreen         |
| :focus              |
| :focus-within       |
| :hover              |
| :intermediate       |
| :in-range           |
| :invalid            |
| :lang()             |
| :last-child         |
| :last-of            |
| :left               |
| :link               |
| :matches()          |
| :not()              |
| :nth-child()        |
| :nth-last-child()   |
| :nth-last-of-type() |
| :nth-of-type()      |
| :only-child         |
| :only-of-type       |
| :optional           |
| :out-of-range       |
| :read-only          |
| :read-write         |
| :required           |
| :right              |
| :root               |
| :scope              |
| :target             |
| :valid              |
| :visited            |

#### PSEUDO ELEMENTS

- Keywords preceded by two colons
- Added to end of selectors to select a certain part of an element

  | PSEUDO Elements |
  | --------------- |
  | ::after         |
  | ::before        |
  | ::first-line    |
  | ::first-letter  |
  | ::selection     |
  | ::backdrop      |

#### COMBINATORS & SELECTOR LISTS

1. **Selector List** AB
   - Any element matching A and/or B
2. **Child Combinator** A > B
   - Any element matching B that is a **direct child** of A
3. **Adjacent Sibling Combinator** A + B
   - Any element matching B that is the next sibling of element matching A
4. **General Sibling Combinator** A ~ B
   - Any element matching B that is one of the next siblings of an element
     matching A

#### CSS VALUES & UNITS

1. **Numeric Values**
   - Length values for specifying element width, border thickness, or font size
2. **Percentages**
   - Also be used to specify size or length
   - Good for **responsive** design
   - Shifts as the browser's viewpoint changes

`em` is the same as the font-size of the current element
`em` are the most common relative unit you'll use in web development
Measures the length of an "m"
`rem` works like `em`, except it will always be equal to the size of the default
base font-size, this does not inherit font sizes, but `em` does

#### THE CASCADE

Indicates that the order of the CSS rules matter, but there is more

What selectors win in the cascade depends on 3 factors

1. Importance (`!important`)
2. Specificity
3. Source Order

IDs and class selectors have higher specificity than element selectors
Best time to use is when you're working on a content management system (CMS) and
can't edit core CSS modules

**Specificity**

- Measure of how specific a selector is (how many elements it could match)
- **Precedence**: `!important`, `#`, `.class`, `element`
- The amount of specificity a select has is measured with 4 units

1.  **Thousands**
    - Score one in this column if the declaration inside a style attribute (in
      line styles) there are no selectors so specificity is always 100
2.  **Tens**
    - Score one in this column for each class selector, attribute selector, or
      : -> pseudo-class contained in the overall selector
3.  **Ones**
    - Score on in this column for each element selector or pseudo element (::)
      contained in overall selector

**Source Order**

- If multiple competing selectors have the same importance and specificity, 3rd
  factor to break the tie is **source order**
- **Later rules win over later ones!**

#### INHERITANCE

Some property values applied to an element will be inherited by the element's
children and some won't

**4 Universal Property Values for Specifying Inheritance**

1. **Inherit**:
   - Sets the property value applied to a selected element to be the same as
     the parent element
2. **Initial**:
   - Sets the property value applied to a selected element to be the same as
     the value for that element in the browser's default style sheet
3. **Unset**:
   - Resets property to its natural value
4. **Revert**:
   - Reverts the prop value if the current origin had not applied any styles to
     it

#### THE BOX MODEL

The CSS Box Model is the foundation of layout on the web. Each element is
represented as a rectangular box with the box's content, padding, border, margin
built around each other

**Width & Height**

- Set the width and height of the **content box**, this content includes both
  text content set inside the box and other boxes representing nested child
  elements

**Padding**

- Refers to the inner margin of a CSS box (between the outer edge of content box
  and inner edge of the border)

**Border**

- By default border has a size of 0

**Margin**

- Pushes up against other CSS boxes in the layout, behaves like padding

#### ADVANCED BOX MANIPULATION

**Overflow**: Content that doesn't fit inside box size

1. **Auto**
   - If too much content, the overflow content is hidden and scroll bars
2. **Hidden**
   - If too much content, overflow is hidden
3. **Visible**
   - Content will be show outside of the box

#### TYPES OF CSS BOXES

The type of box applied to an element is specified by the **display** property

```css
display:block
display: inline
display: inline-block
```

**block**

- "Keep together as a block"
- A block box is a box that's stacked upon other boxes and can have width and
  height set on it

**inline**

- "Will line break"
- An inline box is the opposite of block box, it flows with the document's text
- Width and height have no effect
- Padding, margin, and border will update position of surrounding text, but not
  affect the position of other block boxes

**inline-block**

- "Won't line break"
- In between block and inline, it flows with surrounding text and other inline
  elements without creating line breaks before and after

#### CSS LAYOUT

Methods that can change how elements are laid out

1. Display Property
   - Flex Box: 1D layout either in **row** or **column**
   - `display:flex`
   - Apply this property to the parent element, so all elements will become
     children
   - Grid Layout: 2D layout **row** and **column** same time
   - `display:grid`
   - A grid layout will have rows and columns and the gaps between then are
     called **gutters**
2. Floats
   - Floating an element changes the behavior of that element and the block
     level elements that are follow it in normal flow and the surrounding content
     floats around the floated item
   - **4 Possible Values**:
   ```css
   float:left
   float:right
   float:none
   float:inherit
   ```
3. Position Property
   - Not used to create layouts but, to fine tune position of items on a page
4. Table Layout (Don't use this)
5. Multi-Column Layout

#### POSITIONING TECHNIQUES

5 Position Types:

1. **Static** (Default: Normal Position)
   - Default every element gets
   - Put element in normal place of document
2. **Relative** (Thinks about others)
   - Modify position on the page, moving it relative to its position in normal
     flow
   - Uses `top, bottom, left, right`
3. **Absolute** (Doesn't care)
   - Move an element completely outside of the page's normal layout flow
   - Ex. Popup boxes, Control menus
4. **Fixed** (Even if you scroll, you'll still see it stay in same position)
   - Similar to absolute, except fixes element relative to browser's view port
   - Ex. Navigation var
5. **Sticky** (Until you hit it, then you'll always see it)
   - Makes an element act like `position:static` until it hits a defined offset
     from the viewport at which point acts like `position:fixed`
6. **Z-index**
   - When elements start to overlap, this can determine the element that goes on
     top or bottom
   - Values:
   - `+` move elements higher up (or in front of other elements)
   - `-` move elements lower down (or in back of other elements)
