## Day_3: Connect FrontEnd and Backend in Javascript
There are Two ways to use Packages in javascript.
- common js
  
        const express = require('express')
- module js
  
        import express from 'express'
  if you're using module then you have to define type as module in package.json

          "type": "module"
### To create a web application using Vite, then follow these steps:

- Install Node.js: Ensure that you have Node.js installed on your system. You can download and install it from the official Node.js website: https://nodejs.org/
- Install Vite: You can install Vite globally using npm (Node Package Manager) by running the following command in your terminal or command prompt:

        npm install -g vite
- Create a new Vite project: Once Vite is installed, you can create a new project by running the following commands:

        mkdir my-vite-app
        cd my-vite-app
        vite
    This will prompt you to choose a project template. You can choose from various options like Vue, React, Preact, or Vanilla (plain JavaScript).
- Install dependencies: After choosing the template and generating the project, navigate into the project directory and install dependencies using npm or yarn:

        cd my-vite-app
        npm install
- Run the development server: Once the dependencies are installed, you can start the development server by running:

        npm run dev
  This will start the development server, and you can access your web application at http://localhost:3000 by default.
- Build your application: When you're ready to build your application for production, you can run:

        npm run build
    This will generate a production-ready build of your application in the dist directory.
- Serve the built application: You can serve the built application locally using a tool like serve. Install it globally using npm:

        npm install -g serve
  then navigate to the dist directory and run:

        serve -s
  This will serve your built application at http://localhost:5000 by default.

## CORS
  CORS stands for Cross-Origin Resource Sharing. It is a security feature implemented by web browsers to restrict web pages from making requests to a different origin (domain, protocol, or port) than the one from which the current page was served.

### Why CORS?
  CORS is essential for web security because it prevents malicious websites from accessing sensitive data or performing actions on behalf of a user without their consent. For example, if you're logged into your bank's website, you wouldn't want a malicious site you visit to be able to make requests to your bank's API and perform transactions on your behalf.

### How CORS works:
  When a web application makes a cross-origin request (a request to a different origin), the browser adds an "Origin" header to the request, indicating the origin from which the request originated.

  The server receiving the request can respond with one of the following:

- Allow the request: If the server determines that the request is allowed from the specified origin, it includes the "Access-Control-Allow-Origin" header in the response with the value of the requesting origin. This indicates to the browser that the request is allowed.
- Deny the request: If the server determines that the request is not allowed, it can respond with an error code (e.g., 403 Forbidden) and optionally include the "Access-Control-Allow-Origin" header with a value of "*" (wildcard) to indicate that no origins are allowed to access the resource.
- Preflight request: For certain types of requests (e.g., requests with custom headers or non-simple HTTP methods like PUT or DELETE), the browser sends a preflight request with the "OPTIONS" method to check if the server allows the actual request. The server responds with appropriate CORS headers to indicate whether the actual request is allowed.
- Implementing CORS in a server:
### To enable CORS on a server, the server must respond to requests with the appropriate CORS headers. These headers include:

- Access-Control-Allow-Origin: Specifies which origins are allowed to access the resource. It can be a specific origin or "*", which allows any origin.
- Access-Control-Allow-Methods: Specifies which HTTP methods are allowed when accessing the resource.
- Access-Control-Allow-Headers: Specifies which headers are allowed in the actual request.
- Access-Control-Allow-Credentials: Specifies whether credentials (e.g., cookies, HTTP authentication) are allowed in the actual request.
- Access-Control-Max-Age: Specifies how long the results of a preflight request can be cached.
### Example CORS headers:
  Here's an example of how you might implement CORS headers in an Express.js middleware:

      const express = require('express');
      const app = express();
      
      app.use((req, res, next) => {
        res.setHeader('Access-Control-Allow-Origin', '*'); // Allow requests from any origin
        res.setHeader('Access-Control-Allow-Methods', 'GET, POST, PUT, DELETE, OPTIONS'); // Allow specified methods
        res.setHeader('Access-Control-Allow-Headers', 'Content-Type, Authorization'); // Allow specified headers
        next();
      });
      
      // Your routes and other middleware...
      
      app.listen(3000, () => {
        console.log('Server is running on port 3000');
      });

## PROXY
  A proxy server acts as an intermediary between a client (such as a web browser) and other servers (such as web servers). It facilitates indirect connections between clients and servers, allowing clients to access resources from the server without directly communicating with it.

### How Proxies Work:
  When a client sends a request to access a resource (such as a web page), instead of directly contacting the server hosting that resource, the request is sent to the proxy server. The proxy server then forwards the request to the appropriate server and relays the response back to the client.

### Uses of Proxies:
- Security: Proxies can provide an additional layer of security by filtering incoming and outgoing traffic, blocking malicious content, and masking the client's IP address.
- Caching: Proxies can cache frequently accessed resources, reducing bandwidth usage and improving performance by serving cached content to clients instead of fetching it from the original server every time.
- Anonymity: Proxies can hide the client's IP address from the server, providing anonymity and privacy for users browsing the web.
- Content Filtering: Proxies can be configured to filter or block certain types of content, such as advertisements, adult content, or specific websites, for users within a network.

### Types of Proxies:
- Forward Proxy: Also known as a "gateway" or "web proxy," a forward proxy sits between clients and the internet. Clients send requests to the forward proxy, which forwards them to the internet on behalf of the clients, hiding their IP addresses.
- Reverse Proxy: A reverse proxy sits in front of one or more servers and handles requests on their behalf. It can perform tasks such as load balancing, SSL termination, caching, and request routing, improving performance and security.
- Transparent Proxy: A transparent proxy intercepts traffic without modifying it and forwards it to its destination. It does not require any configuration on the client side, making it "transparent" to the client.
- Anonymous Proxy: An anonymous proxy hides the client's IP address from the server, providing anonymity for the client. However, it does not hide the fact that a proxy is being used.
### Using Proxies in Web Development:
  In web development, proxies are often used during development to overcome CORS restrictions, access resources from different domains, or route requests to different servers. Tools like webpack-dev-server or the built-in proxy feature in create-react-app allow developers to configure a proxy server during development to proxy requests to an API server or other resources.

  Overall, proxies are versatile tools with various uses in networking, security, and web development, providing flexibility, anonymity, and performance improvements for users and developers alike.

      server:{
        proxy:{
          '/api':'http://localhost:3000'
              }
