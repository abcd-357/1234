1.simple
```
<!DOCTYPE html>
<html>
<head>
<title>Combined Program</title>
<style>
body {
  background: lightblue;
  text-align: center;
  font-family: Arial;
}
input, button {
  margin: 5px;
  padding: 8px;
}
</style>
</head>
<body>

<h1>Welcome to My Website</h1>
<p>This is my webpage.</p>
<a href="https://google.com">Visit Google</a>
<hr>

<p id="msg">Click the button</p>
<button onclick="document.getElementById('msg').innerHTML='Hello User!'">
Click Me
</button>
<hr>

<h2>Registration Form</h2>
<form onsubmit="check(); return false;">
<input type="text" id="name" placeholder="Name" required><br>
<input type="email" id="email" placeholder="Email" required><br>
<input type="password" id="password" placeholder="Password" minlength="6" required><br>
<button type="submit">Register</button>
</form>

<script>
function check() {
  alert("Registration Successful!");
}
</script>

</body>
</html>
```
4.chatbot
```
<html>
<head>
<title>Simple Chatbot</title>
<style>
body {
  background: lightblue;
  text-align: center;
  font-family: Arial;
}
#chat {
  background: white;
  width: 300px;
  height: 200px;
  margin: auto;
  overflow: auto;
}
input, button {
  padding: 8px;
  margin: 5px;
}
</style>
</head>
<body>

<h2>Simple Chatbot</h2>

<div id="chat">Bot: Hello! Welcome!</div><br>

<input id="msg" placeholder="Enter message">
<button onclick="send()">Send</button>

<script>
function send() {
  let msg = document.getElementById("msg").value;
  let reply = "I don't understand";

  if (msg == "hi")
    reply = "Hello!";
  else if (msg == "how are you")
    reply = "I am fine!";
  else if (msg == "name")
    reply = "I am Chatbot!";
  else if (msg == "bye")
    reply = "Goodbye!";

  document.getElementById("chat").innerHTML +=
    "<p>You: " + msg + "<br>Bot: " + reply + "</p>";

  document.getElementById("msg").value = "";
}
</script>

</body>
</html>
```



5.Desktop Application Using Node.js and Electron

### 1. index.html

```

<!DOCTYPE html>
<html>
<head>
<title>Desktop App</title>
<style>
body {
    background: lightblue;
    text-align: center;
    font-family: Arial;
}
</style>
</head>
<body>
<h1>Welcome to My Desktop App</h1>
<p>Created using Node.js and Electron</p>
<button onclick="alert('Hello User!')">
Click Me
</button>
</body>
</html>

```

### 2. main.js

```

const { app, BrowserWindow } = require('electron');

app.whenReady().then(() => {
    const win = new BrowserWindow({
        width: 600,
        height: 400
    });

    win.loadFile('index.html');
});

```

### 3. package.json

```

{
  "name": "desktop-app",
  "version": "1.0.0",
  "main": "main.js",
  "scripts": {
    "start": "electron ."
  }
}

```

## How to Run

Step 1: Create a folder named `desktop-app`.

Step 2: Save all three files inside it:

desktop-app

&#x20;index.html

&#x20;main.js

&#x20;package.json

Step 3: Open CMD in that folder and install Electron:

```
npm install electron --save-dev
```

Step 4: Run the application:

```
npm start
```



6.Calculator
```
<html>
<head>
<title>React Calculator</title>
<script src="https://unpkg.com/react@18/umd/react.development.js"></script>
<script src="https://unpkg.com/react-dom@18/umd/react-dom.development.js"></script>
<script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>
</head>
<body style="text-align:center;background:lightblue">

<div id="root"></div>

<script type="text/babel">
function Calculator() {
  const [a,setA] = React.useState("");
  const [b,setB] = React.useState("");
  const [result,setResult] = React.useState("");

  return (
    <div>
      <h2>Simple Calculator</h2>
      <input type="number" placeholder="First Number"
        onChange={e=>setA(e.target.value)}/><br/><br/>
      <input type="number" placeholder="Second Number"
        onChange={e=>setB(e.target.value)}/><br/><br/>

      <button onClick={()=>setResult(+a + +b)}>+</button>
      <button onClick={()=>setResult(a-b)}>-</button>
      <button onClick={()=>setResult(a*b)}>*</button>
      <button onClick={()=>setResult(b==0?"Cannot divide by zero":a/b)}>/</button>

      <h3>Result: {result}</h3>
    </div>
  );
}

ReactDOM.createRoot(document.getElementById("root"))
.render(<Calculator/>);
</script>
</body>
</html>
```

7.## Visitor Counter Using Session in Node.js

Aim: To implement a web application that counts website visits using sessions.

### 1. app.js

```

const express = require('express');
const session = require('express-session');

const app = express();

app.use(session({
    secret: 'mysecret',
    resave: false,
    saveUninitialized: true
}));

app.get('/', (req, res) => {
    req.session.count = (req.session.count || 0) + 1;

    res.send(`
        <h1>Visitor Counter</h1>
        <h2>You visited this page ${req.session.count} times</h2>
    `);
});

app.listen(3000, () => {
    console.log('Server running on http://localhost:3000');
});

```

## How to Run

Step 1: Create a folder named `visitor-counter`.

Step 2: Save the code as `app.js`.

Step 3: Open CMD inside that folder and type:

```
npm init -y
npm install express express-session
```

Step 4: Run the application:

```
node app.js
```

Step 5: Open Chrome and enter:

`http://localhost:3000`



8.Voting

```
<!DOCTYPE html>
<html>
<head>
<title>Voting App</title>
<script src="https://unpkg.com/react@18/umd/react.development.js"></script>
<script src="https://unpkg.com/react-dom@18/umd/react-dom.development.js"></script>
<script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>
<style>
body {
    text-align: center;
    background: lightblue;
    font-family: Arial;
}
button {
    padding: 10px;
    margin: 10px;
}
</style>
</head>
<body>

<div id="root"></div>

<script type="text/babel">
function App() {
    const [a, setA] = React.useState(0);
    const [b, setB] = React.useState(0);

    return (
        <div>
            <h2>Voting Application</h2>

            <h3>Candidate A: {a} Votes</h3>
            <button onClick={() => setA(a + 1)}>
                Vote A
            </button>

            <h3>Candidate B: {b} Votes</h3>
            <button onClick={() => setB(b + 1)}>
                Vote B
            </button>

            <h3>Total Votes: {a + b}</h3>
        </div>
    );
}

ReactDOM.createRoot(document.getElementById("root")).render(<App />);
</script>

</body>
</html>
```



9.password strength

```
<!DOCTYPE html>
<html>
<head>
<title>Password Strength</title>
<script src="https://code.jquery.com/jquery-3.7.1.min.js"></script>
<style>
body {
    text-align: center;
    background: lightblue;
    font-family: Arial;
}
input {
    padding: 10px;
}
</style>
</head>
<body>

<h2>Password Strength Checker</h2>

<input type="password" id="pass" placeholder="Enter Password">
<h3 id="result"></h3>

<script>
$(document).ready(function() {
    $("#pass").on("input", function() {
        let p = $(this).val();

        if (p.length == 0)
            $("#result").text("");
        else if (p.length < 6)
            $("#result").text("Weak").css("color", "red");
        else if (p.length < 10)
            $("#result").text("Medium").css("color", "orange");
        else
            $("#result").text("Strong").css("color", "green");
    });
});
</script>

</body>
</html>
```


10. star rating
```

<!DOCTYPE html>
<html>
<head>
<title>Star Rating</title>
<script src="https://code.jquery.com/jquery-3.7.1.min.js"></script>
<style>
body {
    text-align: center;
    background: lightblue;
    font-family: Arial;
}
.star {
    font-size: 40px;
    color: gray;
    cursor: pointer;
}
</style>
</head>
<body>

<h2>Star Rating Using jQuery</h2>

<div>
    <span class="star">★</span>
    <span class="star">★</span>
    <span class="star">★</span>
    <span class="star">★</span>
    <span class="star">★</span>
</div>

<h3 id="result"></h3>

<script>
$(document).ready(function() {
    $(".star").click(function() {
        let n = $(this).index() + 1;

        $(".star").css("color", "gray");
        $(".star").slice(0, n).css("color", "gold");

        $("#result").text("You rated " + n + " stars");
    });
});
</script>

</body>
</html>

```



11.login

```
<!DOCTYPE html>
<html>
<head>
<title>React Login</title>
<script src="https://unpkg.com/react@18/umd/react.development.js"></script>
<script src="https://unpkg.com/react-dom@18/umd/react-dom.development.js"></script>
<script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>
<style>
body {
    text-align: center;
    background: lightblue;
    font-family: Arial;
}
input, button {
    padding: 10px;
    margin: 5px;
}
</style>
</head>
<body>

<div id="root"></div>

<script type="text/babel">
function App() {
    const [user, setUser] = React.useState("");
    const [pass, setPass] = React.useState("");
    const [msg, setMsg] = React.useState("");

    function login() {
        if (user === "admin" && pass === "1234")
            setMsg("Login Successful!");
        else
            setMsg("Invalid Username or Password");
    }

    return (
        <div>
            <h2>Login Form</h2>
            <input placeholder="Username"
                onChange={e => setUser(e.target.value)} />
            <br/>
            <input type="password" placeholder="Password"
                onChange={e => setPass(e.target.value)} />
            <br/>
            <button onClick={login}>Login</button>
            <h3>{msg}</h3>
        </div>
    );
}

ReactDOM.createRoot(document.getElementById("root")).render(<App />);
</script>

</body>
</html>
```

13.ecoomerce

```
<!DOCTYPE html>
<html>
<head>
<title>Used Furniture Store</title>
<style>
body {
    font-family: Arial;
    text-align: center;
    background: lightblue;
}
header {
    background: brown;
    color: white;
    padding: 15px;
}
.product {
    display: inline-block;
    background: white;
    padding: 15px;
    margin: 10px;
    border-radius: 10px;
}
button {
    background: green;
    color: white;
    padding: 10px;
    border: none;
    cursor: pointer;
}
</style>
</head>
<body>

<header>
<h1>Used Furniture Store</h1>
<p>Buy Refurbished Furniture at Best Prices</p>
</header>

<h2>Available Furniture</h2>

<div class="product">
<h2>Wooden Chair</h2>
<p>Price: Rs. 1500</p>
<button onclick="buy('Wooden Chair')">Buy Now</button>
</div>

<div class="product">
<h2>Sofa</h2>
<p>Price: Rs. 5000</p>
<button onclick="buy('Sofa')">Buy Now</button>
</div>

<div class="product">
<h2>Study Table</h2>
<p>Price: Rs. 2500</p>
<button onclick="buy('Study Table')">Buy Now</button>
</div>

<script>
function buy(item) {
    alert("You selected " + item);
}
</script>

</body>
</html>
```


12.validation  


```

<!DOCTYPE html>
<html>
<head>
<title>Registration Form</title>
<style>
body {
    text-align: center;
    background: lightblue;
    font-family: Arial;
}
input, button {
    padding: 10px;
    margin: 5px;
}
</style>
</head>
<body>

<h2>Registration Form</h2>

<form onsubmit="return validate()">
<input id="name" placeholder="Enter Name"><br>
<input id="mobile" placeholder="Mobile Number"><br>
<input id="email" placeholder="Email"><br>
<button>Register</button>
</form>

<script>
function validate() {
    let name = document.getElementById("name").value;
    let mobile = document.getElementById("mobile").value;
    let email = document.getElementById("email").value;

    if (!/^[A-Za-z][A-Za-z0-9]{5,}$/.test(name)) {
        alert("Invalid Name");
        return false;
    }

    if (!/^[0-9]{10}$/.test(mobile)) {
        alert("Invalid Mobile Number");
        return false;
    }

    if (!/^[^\s@]+@[^\s@]+\.[A-Za-z]{2,}$/.test(email)) {
        alert("Invalid Email");
        return false;
    }

    alert("Registration Successful!");
    return false;
}
</script>

</body>
</html>

```
