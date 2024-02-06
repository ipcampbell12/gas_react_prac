1) Start node project:  
```
npm init -y
```
2) Install clasp (make sure you have -D for devDevependcy)

```
npm install -D @google/clasp
```

3) Go to this URL to enable the google apps script API: 

[Google Apps Script API](https://script.google.com/home/usersettings)

4) Set up clasp commands
```
    "glogin": "clasp login",
    "glogout": "clasp logout",
    "gcreate": "clasp create --title ''React Test Project --rootDir ./apps-script",
    "gpush": "clasp push",
    "gpull": "clasp pull",
    "gclone": "clasp clone <id> --rootDir ./apps-script",
    "gwatch": "clasp push --watch"

```

5) use npm run for clasp commands (make sure you do npm run glogin at some point)
6) Run npm run gcreate to create new project 
7) Select project type (i.e. scripts, docs, webapp, standlone); it's fine to just choose standalone.
8) Install auto complete for script functions (Make sure you have it set to devDependency)

```
npm i -D @types/google-apps-script
```

9) File structure so far: 

![alt text](/screenshots/image-1.png)

10) Add a main.js file to the apps-script directory, and add a doGet function

```
function doGet() {
    return HtmlService
        .createTemplateFromFile("index")
        .evaluate()
        .addMetaTag("viewport", "width=device-width,initial-scale=1.0")
}
```

11) Add an index.html file to apps-script directory
12) Add meta tags to doGet function in main.js
13) File structure should look like this (You will need to move clasp.json file to the root directory): 

![alt text](/screenshots/image-2.png)

14) Deploy as web app and do gpull to update appscript.json on local side
15) Install parcel package

```
npm install --save-dev parcel
```

16) Add src file at root level of project and add an index.html file with a div with id of "app"
17) In the src folder, add an index.js file with following code from parcel: 

```
import { createRoot } from "react-dom/client";
import { App } from "./App";

const container = document.getElementById("app");
const root = createRoot(container)
root.render(<App />);
```
18) In the src file, add an App.js file with following code: 

```
export function App() {
     return <h1>Hello world!</h1>;
 }

 export default App;
```

19) Add a .gitignore file with node_modules added, then initialize a git repository
20) Your file/folder structure should look like this: 

![alt text](/screenshots/image.png)
