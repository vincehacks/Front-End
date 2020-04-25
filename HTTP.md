# HTTP (HYPER TEXT TRANSFER PROTOCOL)

Created by Vince Chang </br>

Here is where I post useful information on the flow from client to server

#### HTTP

Protocol that allows fetching of resources, such as HTML documents. Foundation
of any data exchange on the web and a client protocol (request from browser)

- Human readable
- Extensible - new features
- Stateless: No link between 2 request being carried out on the same connection
- Sessions: Possible with HTTP cookies

#### HTTP CAN CONTROL

1. **Cache**
   - How docs can be cached
   - Instruct proxies and clients what to cache and for how long
2. **Relaxing the Origin Constraint**
   - To prevent snooping and privacy invasions
   - Only pages from the same origin can access all the info of a webpage
3. **Authentication**
   - Use headers
   - Or by using HTTP Cookies
4. **Proxy & Tunneling**
   - Hide IP Addresses
5. **Sessions**
   - HTTP Cookies allow you to link requests with the state of the server

#### PROXIES

Happens at application layer and can do:

1. **Caching**: The cache can be public or private
2. **Filtering**: Anti-virus scan, parental controls
3. **Load Balancing**: Allow multiple servers to server different requests
4. **Authentication**: To control access to different resources
5. **Logging**: Allowing the storage of historical info

#### HTTP FLOW

When the client wants to communicate with a server, either the final server or a
proxy, it performs the following:

1. **Open a TCP Connection**
   - Used to send a request to receive and answer
2. **Send a HTTP Message**
   - GET/HTTP/1.1.
   - Host: developer.Mozilla.org
3. **Read a Response Sent by Server**
   - HTTP/1.1/200 ok
   - date
4. **Close or Reuse the Connection for Further Requests**
   - Once the pipeline is activated: Several requests can be sent without
     waiting for the first response to be fully received

#### HTTP MESSAGES

1. HTTP/1.1 & Earlier
   - Human readable
2. HTTP/2
   - Binary Structure (Frame)
   - Allowing optimizations like compression of headers & multiplexing

**2 Types of HTTP Messages**

1. **Requests**
   Consists of:

   - **HTTP Method**s: verbs (GET, PUT, POST, DELETE), nouns (OPTIONS, HEAD)
   - **Path**: Path of resource to fetch, domain or TCP port
   - **The version of HTTP protocol**
   - **Headers**: Additional info about servers
   - **Body**: For posts (contains the resource that is sent)

2. **Responses**
   Consists of:

   - **Version of HTTP Protocol**
   - **Status Code**: 200 ok, 400 not found
   - **Status Message**: a short description of status code
   - **HTTP Headers**
   - **Body**: containing the fetched resource

   #### HTTP SESSION

   HTTP sessions have 3 phases:

   1. The client establishes a TCP connection (or appropriate connection if the
      transport layer is not TCP)
   2. The client sends its request and waits for the answer
   3. The server processes the request, sending back its answer, providing a
      status code and data

   **Establishing a Connection**

- Client establishes the connection
- Opening a connection is TCP
- TCP default port `80, 8000, 8080`
- The Server can't sent a client data without an explicit request for it
- Before connections are closed after 1 request, 1 response, they stay open

**Short Lived Connections**

- Each HTTP request is completed on its own connection
- TCP Handshake happens before each HTTP request
- **cons**: Time consuming

**Persistent Connections** "keep-alive"

- Each connection **stays open for a period of time** and can be **reused**
  for several requests
- Less TCP Handshakes
- **cons**: When idling, consuming resources and under heavy load, DOS attacks
  can be conducted

#### HTTP PIPELINING

- Requests are issued **sequentially**
- Next request is only issued once the response to current request has been
  received (default
- **Now it does not wait for a answer!**

#### HTTP SECURITY

1. **Content Security Policy** (CSP)

   - Security layer helps detect and mitigate certain types of attacks
   - Types of Attacks:

   1. Cross Site Scripting (XSS)
   2. Data Injection

   - Enable: configure web server to return
   - Only executes scripts loaded in source files

2. **HTTP Public Key Pinning**
   - Tells a web client to associate a specific public key with a certain web
     server to decrease attacks
   - Key is wrapped in a certificate signed by a certificate of authority (CA)
   - enable: public-key-pins
3. **HTTP STRICT-TRANSPORT-SECURITY** (HSTS)
   - Let's a website tell browsers that is should only be accessed using HTTPS
4. **HTTP Cookie**
   - It is a small piece of data that a server sends to the user's web browser
   - Browser can save it and send it back with next request to the same server
   - Remembers **stateful** information for stateless HTTP
   - Cookies have 3 purposes:
     - **Session Management**
       - Logins, shopping carts, game scores
     - **Personalization**
       - User preferences, themes
     - **Tracking**
       - Recoding and analyzing user behavior
   - Enable: HTTP Response header uses set-cookie
   - Session Cookies: Length of the session
   - Permanent Cookies: Expire on specific date

#### HTTP ACCESS CONTROL (CORS)

- Mechanism that uses additional HTTP headers to tell a browser to let a web app
  running at one origin (domain) have permission to access selected resources
  from a server at a different origin

#### HTTP CACHING

- Technique that stores a **copy** of a given resource and server it back when
  requested
- When a web cache has a requested resource in its store, it intercepts the
  request and returns a copy instead of re-downloading from server!
- **pros**: eases the load improving performance and reducing latency
- 2 Types of Caches:

1. **Shared Cache**
   - Stores responses for reuse by more than one user
2. **Private Cache**
   - Dedicated to a single user
3. **Private Browser Cache**
   - Dedicated to a single user
   - Holds all docs downloaded via HTTP by the user
   - Used for: back/forward navigation, saving, viewing as a source
4. **Shared Proxy Cache**
   - More than one user
   - Ex. ISP (internet service provider) might have set up a web proxy as part
     of its local network infrastructure to serve many users so popular resources
     are reused, reducing network traffic

- Caches have **finite** space
- Resources should have **expiration**
- If not expired = Fresh
- If expired = Stale
- Kick out resource from cache = cache eviction

#### RE-DIRECTIONS IN HTTP

- URL forwarding, more than on URL address
- Triggered by the sever with status codes of 3xx
- Can also do via:

1. **HTML Re-directions**
   - http-equiv
2. **JavaScript Re-directions**

Use Cases:

1. **Domain Aliasing**
   - Use a shorter URL to redirect you to the true URL
2. **Keeping Links Alive**
   - When restructuring websites, URLS tend to change
   - Can be configured in Apache, Nginx
