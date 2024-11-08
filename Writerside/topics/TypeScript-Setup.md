# TypeScript Setup

First, make sure that you have Node.js installed:

```Bash
node --version
```
If you get a version number back, it means Node.js is installed, and you can proceed to the next step,
anything else means that Node.js is not installed. 
[Download and install from here](https://nodejs.org/en/download/prebuilt-installer)

Next, install typescript globally using npm

```Bash
npm install -g typescript
```

To confirm whether the installation worked, typed ```tsc``` on the terminal/command prompt window,
it should give you some sort of output but not an error.

In case there is an error, for Windows users, try to open the command prompt in administrator mode, for
Mac/Linux user, run the command above as super admin ie ```sudo npm install -g typescript```.

Next, navigate to your project folder and initialize a package.json file by running the command below:

```Bash
npm init -y
```

Now, install typescript to your project as a development dependency.

```Bash
npm install typescript --save-dev
```

Whenever working with TypeScript, we have to provide a configuration file that tells TypeScript how to behave.

To do this, run the following command:

```Bash
npx tsc --init
```

This creates a new TypeScript configuration file in the current project directory, this file has
different options that the compiler will use when compiling our TypeScript code to JavaScript code.

## Your first TypeScript code!
With the above setup complete, let's now write our first TypeScript code.

Inside your project directory, create a file ```hello.ts``` with the following code:

```Typescript
const value: number = 5;
console.log(number);
```

To execute the code above, we need to convert it to JavaScript code first and then execute the generated
JavaScript code.

To do this, navigate to where the file ```hello.ts``` lives and run the following command:

```Typescript
tsc hello.ts
```

This will generate a hello.js file with the following code:

```Javascript
var value = 5;
console.log(value);
```

We can now execute this Javascript file with node.

## Making work easier with vite

```Bash
npm init vite PROJECT_NAME -- --template vanilla-ts
```

Let's create a project called ```hello-ts```:

```Bash
npm init vite hello-ts -- --template vanilla-ts
```