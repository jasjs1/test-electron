# test-electron

Learn how to use Electron for Multiplatform Desktop Applications.

## Installation
 
To install Electron, we'll be using npm.

Vital steps:

1. Make sure you are in the correct folder directory in the terminal.

   ```bash
   npm init -y
This will create a basic package.json file in the current folder directory.

2. 
``` 
npm i -D electron
```
This will install Electron.

Now you have everything you need to get Electron installed on your local machine.

## Getting Everything Working

1. Open your package.json file and modify this line:
```
"test": "echo \"Error: no test specified\" && exit 1"
```
to
```
"start": "electron ."
```

2. Create a 'main.js' file and copy this code:
```
const { app, BrowserWindow } = require('electron');

function createWindow() {
  const win = new BrowserWindow({
    width: 1200, // You can modify this
    height: 1200, // You can modify this
  });

  win.loadFile('src/index.html'); // Modify this as needed, to match up with your folder path
}

app.whenReady().then(createWindow);

app.on('window-all-closed', () => {
  if (process.platform !== 'darwin') {
    app.quit();
  }
});
```

Make sure everything matches the code provided. Otherwise, Electron may not work as expected.

3. Create a 'index.html' file
```
// If you need to change the file path go ahead and do that.

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="main.css">
    <title>Test Electron App</title>
</head>
<body>

    <h2 id="hello-msg">Hello World!</h2>
  
    <script src="script.js"></script>
</body>
</html>
```
