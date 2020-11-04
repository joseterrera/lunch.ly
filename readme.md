Lunch.ly Reservation System

Lunchly is an Express app that is not an API server, nor is it RESTful. Instead, it’s a server-side templated application with custom URLs.

Inside of models, we define two objects: Customers and Reservations. We use static methods.
As MDN describes it, “Static methods are called without instantiating their class and are also not callable when the class is instantiated. Static methods are often used to create utility functions for an application.” In other words, static methods have no access to data stored in specific objects.

Calling a static method or property:
```js
class ClassWithStaticMethod {

  static staticProperty = 'someValue';
  static staticMethod() {
    return 'static method has been called.';
  }

}

console.log(ClassWithStaticMethod.staticProperty);
// output: "someValue"
console.log(ClassWithStaticMethod.staticMethod());
// output: "static method has been called."
```


Static methods are most often useful for methods that do things like create a new customer, or look up a customer in a database — you’d want to call this function before we had an individual customer yet, since the job of this function is to find/create one.

While many languages call these “class methods,” in Javascript they’re often called “static methods,” so JS uses the static keyword to create these methods.

In this app, we use static methods inside the models. These methods are meant to be called on the class. They look up the corresponding customer in the database, and return a JS instance of the correct class.




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
