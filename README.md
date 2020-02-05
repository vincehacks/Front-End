# Front-End

Created by Vince Chang </br>

Here is where I post useful information for doing Front-End Development

#### DOCUMENTATION
- [Mozilla Docs](https://developer.mozilla.org/en-US/docs/Web)
- [HTML Elements](https://developer.mozilla.org/en-US/docs/Web/HTML/Element)
- [HTML Attributes](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes)


#### HOW TO OPTIMIZE HTML
- [Compressing JPEG](https://compressjpeg.com/)
- [Website Optimization](http://www.websiteoptimization.com/)
- [Performance Rules](http://developer.yahoo.com/performance/rules.html)
- [Page Speed](https://developers.google.com/speed/pagespeed/)
- [Paint Flashing Tool](https://developer.mozilla.org/en-US/docs/Tools/Paint_Flashing_Tool)


#### CREATE REACT APP
- [Create React App Medium Article](https://medium.com/in-the-weeds/learning-react-with-create-react-app-part-1-a12e1833fdc)


#### SHORTCUT COMMANDS
Cmd + o is shortcut to open file from browser
Cmd + shift + c  / Cmd + shift + i = open inspect via Chrome
Cmd + ctrl + space = emojis

#### MISC LINKS
- [Learning Shell](explainshell.com)
- [Learning Git](ohshitgit.com)

#### HTML
- Img tags can be used both in html and css if it is in css then is just for decoration. Like the background img. If it’s actual pictures of things then use img. You can’t do alt in css only img
- Window is the global context

#### CSS
- Pseduo classes use the colon. Based on state like hover , first-child, last-child, nth-child
- Look up box-sizing border box
- ```*{box-sizing: border-box;}```


#### LEARNING FLEX BOX & CSS GRID
- [Flexbox defense](http://www.flexboxdefense.com/)
- [Flexbox froggy](https://flexboxfroggy.com/)
- [Git Repo w/ Useful Info](https://github.com/jen4web/fem-layout)
- [Flexbox Resources](https://github.com/jen4web/fem-layout/blob/master/resources/resources.txt)
- [Web Responsive Design](https://alistapart.com/article/responsive-web-design/)
- [Box Sizing Border Box](https://www.paulirish.com/2012/box-sizing-border-box-ftw/)


#### INTERVIEW QUESTIONS
- Event stop propagation js interview question
- What is your favorite css named color?

```java

/* =========================================================================
 * Function Name: map.getOrDefault(key, defaultValue)
 * Returns the value to which the specified key is mapped, or defaultValue if
 * this map contains no mapping for the key.
   ========================================================================= */
  Map<String,Integer> map = new HashMap();
  map.put("Vince",27);
  map.put("Lurks",21);
  System.out.println("Vince's age: " + map.getOrDefault("Vince",-1)); // 27
  System.out.println("Lurks's age: " + map.getOrDefault("Lurks",-1)); // 21
  System.out.println("Baloo's age: " + map.getOrDefault("Baloo",-1)); // -1


/* =========================================================================
 * Function Name: string.isEmpty()
 * Returns true if, and only if, length() is 0.
 * Use this instead of doing if(string.length() == 0)
   ========================================================================= */
  String string1 = "Vince";
  String string2 = "";
  System.out.println(string1.isEmpty()); // True  == if(string1.length() == 0)
  System.out.println(string2.isEmpty()); // False == if(string2.length() == 0)


/* =========================================================================
 * Function Name: isDigit(char ch)
 * Determines if the specified character is a digit.
 * Function Name: isLetter(char ch)
 * Determines if the specified character is a letter.
   ========================================================================= */
  char c = 'v';
  char c2 = '2';
  System.out.println(Character.isLetter(c1)); // True
  System.out.println(Character.isDigit(c2));  // True


/* =========================================================================
 * Function Name: Arrays.toString(array)
 * Converts an array to a string!
   ========================================================================= */
  String[] arr = new String[]{"Vince","Chang","is","cool"};
  System.out.println(Arrays.toString(arr)); // "Vince Chang is cool"


/* =========================================================================
 * Function Name: string.split(regex)
 * Returns a String[]
 * Splits this string around matches of the given regular expression.
   ========================================================================= */
  String s = "Vince Chang is cool";
  String[] wordArr = s.split(“ “); // ["Vince","Chang","is","cool"]


/* =========================================================================
 * HOW TO CREATE A STRING FROM A CHAR ARRAY
   ========================================================================= */
  char[] charArray = new char[]{'v','i','n','c','e'};
  String newString = new String(charArray);
  System.out.println(newString); // "vince"


/* =========================================================================
 * HOW TO TELL IF A CHARACTER IS IN A STRING
 * Function Name: string.indexOf(char c)
 * Returns the index within this string of the first occurrence of the
 * specified character, otherwise returns -1
   ========================================================================= */
  String s = "vince"
  if(s.indexOf(‘a’) > 0);
    System.out.println("true"); // Will not print here
  else
    System.out.println("false");// Will print false


/* =========================================================================
 * Enhanced For loop vs Regular For loop
 * Example will show the equivalent
   ========================================================================= */
  String string = "vince";
  for(int i = 0; i < string.length(); i++)
	  System.out.print(string.charAt(i)); //'v','i','n','c','e'

  for(char c : string.toCharArray())
	  System.out.print(c);                //'v','i','n','c','e'


/* =========================================================================
 * HOW TO PRINT CONTENTS OF A LINKED LIST
   ========================================================================= */
  LinkedList<Node> list = new LinkedList<Node>();
  for(Object o : list)
    System.out.println(o);
```

#### HACKERANK QUESTIONS
1. Which of the following data structures is suitable for modeling telephone
connections in a network? [circular linked list, m-ary trees, graphs, sets]
**Answer**: m-ary trees, answer is binary tree

2. An input restricted dequeued is a linear list in which terms may be inserted
at one end but moved from either end. Such a data structure can be operated
[neither as a queue nor a stack, as a queue but not a stack, as a stack but not
a queue, both as a queue and a stack]
**Answer**: niether as a queue nor a stack

3. In a binary tree that has K nodes having two children and L leaves:
[L = K + 1 , L = 2K + 1 , L = K -1 , No relation can be formed]
**Answer**: No relation can be formed

4. A sorting algorithm is stable if it maintains a the relative order of records
with equal keys. Which of the following is not a stable sorting algorithm?
[heap sort, bubble sort, selection sort, merge sort]
**Answer**: Stable: Bubble, Insertion, Merge, and Count sort. Unstable: Quick
and Heap Sort.