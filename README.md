## Desktop Application Using Node.js and Electron

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


Click Me

