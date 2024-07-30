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
- Examples of bundlers, webpack, babbel, parcel. All bundlers are about the same and its a matter of choice.
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