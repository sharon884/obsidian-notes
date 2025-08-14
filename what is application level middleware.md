
### **Key Points**

- Application-level middleware is **global to the app** unless you specify a path.
    
- It can **modify request/response**, perform **logging, authentication, validation**, etc.
    
- Always call `next()` unless you end the response (e.g., `res.send()`).
  
  
  
  

const express = require("express");

const app = express();

const PORT = 3001;

app.use((req, res, next ) => {

    console.log("thi is an example for the application level middleware!");

    next();

});
app.get("/", ( req, res ) => {

    res.send("hai this your express server with applicaton level middleware ");

});

app.listen(PORT, () => {

    console.log(`server is listening on PORT : http://localhost:${PORT}`);

});