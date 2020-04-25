# README

Created by Vince Chang </br>

Here is where I post useful information found and learned over time

#### DOCUMENTATION

- [Mozilla Docs](https://developer.mozilla.org/en-US/docs/Web)
- [HTML Elements](https://developer.mozilla.org/en-US/docs/Web/HTML/Element)
- [HTML Attributes](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes)

#### ACRONYMS

- ES5/ES6 = ECMAScript

| Acronym   | Meaning                               |
| --------- | ------------------------------------- |
| ES5/ES6   | ECMAScript                            |
| B.E.M     | Block Element Modifier                |
| S.O.L.I.D | Single Responsibility Principle       |
| TCP       | Transmission Control Protocol         |
| IP        | Internet Protocol                     |
| DNS       | Domain Name Server                    |
| HTTP      | Hyper Text Transfer Protocol          |
| HTML      | Hyper Text Markup Language            |
| SEO       | Search Engine Optimization            |
| DOM       | Document Object Model                 |
| URI       | Uniform Resource Identifier           |
| URL       | Uniform Resource Locator              |
| URN       | Uniform Resource Name                 |
| MIME      | Multipurpose Internet Mail Extensions |
| API       | Application Programming Interfaces    |
| C.R.U.D   | Create Read Write Delete              |

### PRINCIPLES

#### B.E.M

- B.E.M stands for Block Element Modifier
- Standard naming convention for CSS class names
- **Block**: The outermost parent element of the component is defined as a block
- **Element**: Inside of the component may be one or more children called
  elements
- **Modifier**: Either a block or element may have a variation signified by a
  modifier
- Ex. [block]\_\_[element]--[Modifier]

#### S.O.L.I.D PRINCIPLES OF OOP

- Acronym for 5 design principles to make software more understandable, flexible
  & maintainable

1. **Single Responsibility Principle**
   - A class should have only one single responsibility
2. **Open/Closed Principle**
   - Software Entities should be open for extension, but closed for
     modification
3. **Liskov Substitution Principle**
   - Objects in a program should be replaceable w/ instances of their subtypes
     without altering correctness of that program
4. **Interface Segregation Principle**
   - Many client specific interfaces are better than on general purpose
     interface
5. **Dependency Inversion Principle**
   - One should depend upon abstractions, not concretions

#### CLIENTS & SERVERS

The client uses the web browser to send and receive requests to the server

- **Clients**: Web users internet connected devices
- Ex. Computer is connected to WiFi or phone is connected to network
- **Servers**: Computers that store webpages, sites, apps
- When a client device wants to connect to a webpage, a copy of the webpage is
  downloaded from the server onto the client machine to be displayed in the
  user's web browser
- Ex. Nginx, Tomcat
- For handling data sent to a server use:
  - Express for Node.js
  - Django fro Python
  - Laravel for PHP
  - Ruby on Rails for Ruby

#### HOW THE INTERNET WORKS

**Internet Connection**: Send and receive data on the web
**TCP/IP**: Communication tools that define how data should travel across the
web
**DNS**: Like an address book for websites. Browsers look at DNS to find the
real address before retrieving the website. i.e (Google.com is resolved to
172.217.0.46). The browser needs to find out which server the website lives on,
so it can send HTTP messages to the right place
**HTTP**: Application protocol that defines a language for clients and servers
**URI**: A system for identifying pieces of info on the network
**Methods**: OPTIONS, GET, HEAD, POST, PUT, DELETE, TRACE, CONNECT
**Component Files**: Websites are made up of many files

- 2 Types:
- **Code Files**: HTML, CSS, JavaScript
- **Assets**: Images, Music, Video, Word Doc, PDF, etc
  **HTTP Headers**: Additional data sent to give more context about the
  transaction between the client and the server

#### WHEN YOU TYPE A WEB ADDRESS AND HIT ENTER IN THE BROWSER

1. The browser goes to the DNS sever and finds the real address of the server
   that the website lives on
2. The browser sends an HTTP request message to the server, asking it to send a
   copy of the website to the client. This message and all other data sent
   between the client and the server is sent across your internet connection using
   TCP/IP connection.
3. If the server responds (approves) the client's request, the server sends the
   client a **"200 Response"** and starts sending the website files to the browser
   in small chunks called packets
4. The browser assembles the packets into a complete website and displays it

- **Packets**:
  - Data sent as thousand of small chunks so that many different website users
    can download the same website at the same time
  - If it were just one big packet, it would only allow ONE person to download
    at a time

#### SEARCH ENGINE OPTIMIZATION (SEO)

- Process of making a website more visible in search results, also improving
  search ranking
- Search Engines crawl the web and index content found
- SEO methods in 3 broad classes:
  1. **Technical**:
     - Tag the content using semantic HTML
     - Crawlers find the content you want to be indexed
  2. **Copy Writing**:
     - Write content using visitor's vocab
  3. **Popularity**:
     - You get the most traffic when other established sites link to your site

#### EXTRA

- If a path has spaces in it, use quotes to wrap each path:
  `mv “/Users/vincechang/Desktop/REST-API” /Users/vincechang/Documents`

#### MISC LINKS

- [Learning Shell](explainshell.com)

#### INTERVIEW QUESTIONS

- Event stop propagation js interview question
- What is your favorite css named color?
