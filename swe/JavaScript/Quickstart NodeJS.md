#### Installation
- Install nodejs with `nvm`
- Create project directory
- Install dependencies with `npm i express`
- Update `package.json` with command shortcuts

```
  "scripts":{
  "start": "node index"
  "dev": "nodemon index"
  }
```

#### Creating project
- Create `index.js` and start coding

```javascript
const express = require("express")
const path = require("path")

const app = express();
const PORT = process.env.PORT || 5000 //or another port number

// send back "hello world" when you go to the "/" path
app.get("/", function(req, res){
	res.send("Hello World!");
})

app.listen(PORT, () => console.log(`Server running on port ${PORT})`);
```

#### Environment variables for NodeJS projects
Use `.env` and use with package `dotenv`
https://www.freecodecamp.org/news/heres-how-you-can-actually-use-node-environment-variables-8fdf98f53a0a/

#### Express
Express is a server-side / back-end framework that works with Node.js
Can also render views with express but usually used with a front end that renders the data that is sent over from the backend so it's dynamic

#### Create a `routes/` directory 
You can then export from the file. You have to import express and use the express router to make this work. Then import it in `index.js`

```javascript
// this is data.js
const express = require("express")
const router = express.Router();

// get all data
router.get("/", (req, res) =>{
	// this returns all the data object
	res.json(data)
})

// get a single data
router.get("/:id", (req, res) => {
	const found = data.some(data.id === parseInt(req.params.id))
	if(found){
		res.json(data.filter(d => d.id === parseInt(req.params.id)))
	}else{
		res.status(400).json({msg: `No data found with id of ${req.paramas.id}`})
	}
})

modules.exports = router;
```

```javascript
//this is index.js

//Data api routes
app.use("/api/data, require("./routes/api/data")")
```

#### Middleware

```javascript
// creates the middleware function called middleware1
const middlewareOne = (req, res, next) =>{
	console.log("Performing some task");
	next()
}

//calls and initialized that middleware function
app.use(middlewareOne)
```

You can create a middleware/ directory/folder where you store all of your middleware. 
You can then export from the file. Then import it in `index.js`

```
// this is in the middlewareOne.js within the middlware/ directory
const middlewareOne = (req, res, next) =>{
	console.log("do some work");
	next()
}

module.export.middlewareOne
```

```javascript
//this is in index.js
const middleware = require("/middleware/middlwareOne")
app.use(middlewareOne)
```

Useful express middleware
```
app.use(express.json()) //raw json
app.use(express.urlencoded({extended: false})) //handles form submissions
```

Middleware are functions that have access to the request and response and executes code that in the middle of the request response cycle.  Each middleware has to call the next middleware function to execute it. If middleware does not call the next one then the later middleware do not get executed. 


