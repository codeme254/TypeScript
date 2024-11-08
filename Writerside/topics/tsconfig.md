# tsconfig

The tsconfig file specifies options for the compiler and some project settings that are important as we
write TypeScript code.

Some notable options are:

**target**: the target option specifies the version of JavaScript that the TypeScript code should compile down to. 
For example, setting target: "ES6" will generate JavaScript code compatible with ES6 standards, while target: 
"ES5" will output ES5-compatible code.

**module**: the module option in TypeScript defines the module system for the compiled output. For example, setting 
module: "CommonJS" outputs code that uses CommonJS modules (typically used in Node.js), while module: "ESNext" or 
module: "ES6" uses ECMAScript module syntax (ESM) for browser or modern environments.

**rootDir**: The rootDir option in TypeScript specifies the root folder containing the source files. TypeScript will 
look for files to compile starting from this directory. For instance, if you set rootDir: "./src", TypeScript will 
consider src as the main folder for input files, helping to organize the source structure and keep the output organized 
according to this directory layout.