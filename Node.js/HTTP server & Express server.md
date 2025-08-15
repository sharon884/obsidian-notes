

## **HTTP Server (built-in Node.js module)**

- Node.js has a built-in module called `http`.
    
- It lets you create a **basic web server**.
    
- You handle **everything manually**: parsing URLs, handling routes, sending responses, etc.
    
- Minimal, low-level, but flexible.



const http = require("http");

const server = http.createServer(( req, res ) => {

    if ( req.url === "/") {

        res.end("hellow this is your http server!");

    } else if ( req.url === "/hai") {

        res.end("hai this is your http server")

    }

});

server.listen(3000, () => {

    console.log("server running at : http://localhost:3000")

});



## **Express Server (built on top of HTTP)**

- **Express** is a framework built **on top of Node’s HTTP module**.
    
- It provides lots of **shortcuts and utilities** so you don’t have to write boilerplate code.
    
- Handles routing, middleware, JSON parsing, error handling, etc.
    
- Cleaner, faster to build real apps.
- 
  
  const express = require("express");

const app = express();
const PORT = 3000 ;

app.use(express.json());

app.get("/", (req, res) => {

    res.send("hellow this is your express server");

});

app.get("/hai", ( req, res ) => {

    res.send("hai this is your express server");

})

app.listen(PORT, () => {

    console.log(`server is running on http://localhost:${PORT}`);
});