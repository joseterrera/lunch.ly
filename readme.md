Type psql on terminal and create database: `CREATE DATABASE lunchly;`
Exit, and then type psql < data.sql to populate database
Run `npm install`
Run `nodemon server.js`

To fix this, you can tell nodemon what extensions to watch with the -e flag. For this assignment, it’s worth telling it to listen for changes to HTML, CSS, and Javascript, so you should start your server with the following command:

$ nodemon -e js,html,css

JavaScript Getter
In JavaScript, getter methods are used to access the properties of an object. For example,

let student = {

    // data property
    firstName: 'Monica',
    
    //accessor property(getter)
    get getName() {
        return this.firstName;
    }
};


// accessing getter methods
console.log(student.getName); // Monica


In JavaScript, setter methods are used to change the values of an object. For example,

let student = {
    firstName: 'Monica',
    
    //accessor property(setter)
    set changeName(newName) {
        this.firstName = newName;
    }
};

console.log(student.firstName); // Monica

// change(set) object property using a setter
student.changeName = 'Sarah';

console.log(student.firstName); // Sarah



getter setter:
These two keywords define accessor functions: a getter and a setter for the fullName property. When the property is accessed, the return value from the getter is used. When a value is set, the setter is called and passed the value that was set. It's up to you what you do with that value, but what is returned from the setter is the value that was passed in – so you don't need to return anything.