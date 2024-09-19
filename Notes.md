# Episode 2 -> Ignite App
    - What is NPM(Package Manager)? - Standard Repo for all Packages that you would need to include in your project
    - NPM helps ignite your package or project

# Packege.json
- What is Package.Json file? It's a configuration for NPM in your project
- NPM uses package.json to  essentially configure and manage dependencies

- Package.json file is a configuration for NPM. Whatever packages our project needs, we install those packages using
  npm install <packageName>.

- Once package installation is complete, their versions and configuration related information is stored as dependencies
  inside package.json file.

- Question: What is difference between package.json and package.lock.json?
       Answer=>  In package. json we have information about generic version
        of installed packages whereas in package.lock.json we have
        information about the specific or exact version of
        installed packages.
        
# Bundler 
- Most important package in any project!!
- What is a bundler? Bundler is a package that helps you compress, package your app so it can be shipped to production.
- Examples of bundlers include, webpack, parcel, rolup, browserify. All bundlers are about the same and its a matter of choice.
- Bundlers essetnially give super powers to your application. We get bundlers as NPM packages.

- Types of dependencies
    - Dev Dependence(Used in Development phase)
    - Normal Dependence


Examples of Bundlers:
- Use ^(carrot) vs ~(tilder)
    - ^ is recommended because its for minor version increments vs ~ which gets major updates to a package

# NPX 
    - npx is used to  execute a package for exampe 'npx parcel index.html'
    - npx means ‘execute using npm’
    - index.html is the entry point
    - so essentially running 'npx parcel index.html' parcel creates a server for us and hosts the local build for us...

* node_modules:
Which gets installed is like a database for the npm.
Every dependency in node_module will have its package.json.
Node modules are very heavy so we should always put this in
git ignore.

# To ignite our app:
    - npx parcel index.html
    - npx means ‘execute using npm’
    - index.html is the entry point

# Hot Module Replacement (HMR):
It means that parcel will keep a track of all the files which
you are updating.
There is File Watcher Algorithm (written in C++). It keeps
track of all the files which are changing realtime and it
tells the server to reload.
These are all done by PARCEL

# parcel-cache:
Parcel caches code all the time.
When we run the application, a build is created which takes
some time in ms.
If we make any code changes and save the application, another
build will be triggered which might take even less time than
the previous build.
This reduction of time is due to parcel cache.
Parcel immediately loads the code from the cache every time
there is a subsequent build.
On the very first build parcel creates a folder .parcelcache where it stores the caches in binary codeformat.
Parcel gives faster build, faster developer experience
because of caching

* dist:
It keeps the files minified for us.
When bundler builds the app, the build goes into a folder
called dist.
The `/dist` folder contains the minimized and optimised
version the source code.
Along with the minified code, the /dist folder also comprises
of all the compiled modules that may or may not be used with
other systems.

# When we run command:
    'npx parcel index.html'
This will create a faster development version of our project
and serves it on the server.

# When I tell parcel to make a production build:
    'npx parcel build index.html'
    - It creates a lot of things, minify your file.
    - And the parcel will build all the production files to
the dist folder.   

* Parcel features at a glance:
- Hot Module Replacement (HMR)
- File Watcher Algorithm - C++
- Bundling
- Minify Code
- Cleaning our code
- Dev and production build
- Super fast build algorithm
- Image Optimization
- Caching while development
- Compression
- Compatible with older browser versions
- Https on dev
- Image Optimization
- Port No
- Consistency Hashing Algorithm
- Zero Config
- Tree Shaking

* Transitive Dependencies :
We have our package manager which takes care of our
transitive dependencies of our code.
If we’ve to build a production ready app which uses all
optimisations (like minify, bundling, compression, etc), we
need to do all these.
But we can’t do this alone, we need some dependencies on it.
Those dependencies are also dependent on other dependencies

* Browserslist:
Browserslist is a tool that specifies which browsers should
be supported/compatible in your frontend app.
It makes our code compatible for a lot of browsers.

* Tree Shaking:
Tree shaking is a process of removing the unwanted code that
we do not use while developing the application.
In computing, tree shaking is a dead code elimination
technique that is applied when optimizing code.

# Episode 3 
- create a script to automate certain commands

- React.Element => creates an object behind the scenes => HTMLElement(render). 
- 

# Q ) What is another way of starting the build of the project?
        - We will be creating scripts instead of using “npx parcel index.html”. We can create different scripts for starting our
            project in Development and Production. 
        - In package.json , in the script section write the following command.
        <!--
        "scripts": {
                    "start": "parcel index.html",
                    "build": "parcel build index.html",
                    "test": "jest"
                },
        -->
        
        To run these scripts, enter the following commands in the terminal,
        To start: npm run start or npm start
        For Production Build: npm run build

#  Introducing JSX
    JSX makes developer life easy as we no longer have to write our code using React.createElement()

    Note: We write code for both Machines and Humans but first for Human understanding as it is read by a lot of developers

# Q ) What is JSX? 
    - JSX is HTML-like or XML-like syntax. JSX stands for JavaScript XML. It's a syntax extension for JavaScript.
    - It is not a part of React. React apps can be built even without JSX but the code will become very hard to read.
    - It is not HTML inside JavaScript.
    - JavaScript engine cannot understand JSX as it only understands ECMAScript

# Introducing Babel

# Q ) Is JSX a valid JavaScript?
    The answer is yes and no.
        JSX is not a valid Javascript syntax as it’s not pure HTML or
        pure JavaScript for a browser to understand. JS does not have
        built-in JSX. The JS engine does not understand JSX because
        the JS engine understands ECMAScript or ES6+ code

# Q ) If the browser can’t understand JSX how is it still working?
    This is because of Parcel because “Parcel is a Beast”.

    Before the code gets to JS Engine it is sent to Parcel and
    Transpiled there. Then after transpilation, the browser gets the
    code that it can understand.

    Transpilation ⇒ Converting the code in such a format that the
    browsers can understand. 

    Parcel is like a manager who gives the responsibility of transpilation to a package called Babel.

    Babel is a package that is a compiler/transpiler of JavaScript
    that is already present inside ‘node-modules’. It takes JSX and
    converts it into the code that browsers understand, as soon as
    we write it and save the file. It is not created by Facebook.
    Learn more about Babel on babeljs.io 

    JSX (transpiled by Babel) ⇒ React.createElement ⇒ ReactElement ⇒ JS Object ⇒ HTML Element(render)

# Q ) What is the difference between HTML and JSX?
    - JSX is not HTML. It’s HTML-like syntax.

    - HTML uses ‘class’ property whereas JSX uses ‘className’ property
    - HTML can use hypens in property names whereas JSX uses camelCase syntax. 

# Single Line and Multi Line JSX Code
    - Single line code:
        const jsxHeading = <h1>Namaste React</h1>

    - Multi-line code:
        If writing JSX in multiple lines then using ‘()’ parenthesis is
        mandatory. To tell Babel from where JSX is starting and ending.

        const jsxHeading = (
            <div>
            <h1>Namaste React</h1>
            </div>
        )

        NOTE:
            1) Use “Prettier - Code Formatter” VS Code Extension to
            make your code look beautiful with proper formatting
            2) Use “ES lint” VS Code Extension for linting
            3) Use “Better Comments” VS Code Extension to beautify
            your comments

        
# Introducing React Components
- Everything inside React is a component.

# Q ) What are Components?
    There are 2 types of components:

    1.Class-based Components - Old way of writing code, used rarely in industry

    2.Functional Components - New way of writing code, most commonly used

# Q ) What is a React Functional Components?
- It is just a JavaScript Function that returns some JSX or a react element.
- Always name React Functional Component with Capital Letters otherwise you will confuse it with normal function

- // All are the same for single-line code
    const HeadingComponent1 = () => (
    <h1>Namaste</h1>
    )

    const HeadingComponent2 = () => {
    return <h1>Namaste</h1>
    }
    const HeadingComponent3 = () => <h1>Namaste</h1>

- To render a functional component we call them ‘<Heading1 />’.
    This is the syntax that Babel understands.
    You can also call them using these ways, ‘<Title></Title>’ or ‘{Title()}’

# Components Composition
- A component inside a component.
- Calling a component inside another component is Component Composition.
    const Title = () => <h1>Namaste React</h1>

    const HeadingComponent = () => (
    <div id="container">
    <Title />
    </div>
    )

- Code inside the ‘Title’ component will be used inside the ‘HeadingComponent’ component as the ‘Title’ component is called
inside it. 
- It will become something like this, Laying the Foundation! (Namaste-React) 10

    const HeadingComponent = () => (
    <div id="container">
    <h1>Namaste React</h1>
    </div>
    )

# Q ) How to use JavaScript code inside JSX?
- Inside a React Component when ‘{}’ parenthesis is present we can write any JavaScript expression inside it.
    const number = 10000;

    const HeadingComponent = () => (
    <div id="containter">
    {number}
    <h1>Namaste React</h1>
    </div>
    )

# Q ) How to call React Element in JSX?
- We can use ‘{}’ parenthesis.

    const elem = <span> React Element </span>

    const HeadingComponent = () => (
        <div id="containter">
            {elem}
            <h1>This is Namaste React</h1>
        </div>
    )

# Q ) What will happen if we call 2 elements inside each other?
- If we put 2 components inside each other, then it will go into an infinite loop and the stack will overflow. It will freeze
    your browser, so it’s not recommended to do so.

# Advantages of using JSX.

1) Sanitizes the data
    - If someone gets access to your JS code and sends some malicious data which will then get displayed on the screen, that attack is called cross-site scripting.
    - It can read cookies, local storage, session storage, get cookies, get info about your device, and read data. JSx takes care of your data.
    - If some API passes some malicious data JSX will escape it. It prevents cross-site scripting and sanitizes the data before rendering

2) Makes code readable JSX makes it easier to write code as we are no longer creating elements using React.createElement()
3) Makes code simple and elegant
4) Show more useful errors and warnings
5) JSX prevents code injections (attacks)

# Episode # 4

# Planning for the UI

1) Before we start coding, plan things out. Planning will make things easier to understand. We should know exactly what to build:
    # Name the App
    # UI Structure 
        * Header
            - Logo
            - Nav Items
        * Body 
            - Search 
            - Restaurant Container
                - Restaurant Card
                - Dish Name
                - Image 
                - Resturant Name
                - Rating 
                - Cuisines
                - Time to Deliver
        * Footer
            - Copyright
            - Links
            - Address
            - Contact 
    



