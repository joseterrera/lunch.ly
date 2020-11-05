Lunch.ly Reservation System

Lunchly is an Express app that is not an API server, nor is it [RESTful](https://medium.com/@atingenkay/restful-routes-what-are-they-8fe221521bb). Instead, it’s a server-side templated application with custom URLs.



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
### Static Methods

Static methods are most often useful for methods that do things like create a new customer, or look up a customer in a database — you’d want to call this function before we had an individual customer yet, since the job of this function is to find/create one.

While many languages call these “class methods,” in Javascript they’re often called “static methods,” so JS uses the static keyword to create these methods.

In this app, we use static methods inside the models. These methods are meant to be called on the class. They look up the corresponding customer in the database, and return a JS instance of the correct class.

### Getter / Setter

In JavaScript, accessor properties are methods that get or set the value of an object. For that, we use these two keywords: get and set.


#### Get

Getter methods are used to access the properties of an object. For example,
```js
let student = {

    // data property
    firstName: 'Monica',
    
    //accessor property(getter) to access property of an object
    get getName() {
        return this.firstName;
    }
};

// accessing data property
console.log(student.firstName); // Monica

// accessing getter methods
console.log(student.getName); // Monica

//trying to access as a method
console.log(student.getName()); // error
```

#### Set

In JavaScript, setter methods are used to change the values of an object. For example,

```js
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
```


### Setting up the app


1. Type psql on terminal and create database: `CREATE DATABASE lunchly;`
2. Exit, and then type psql < data.sql to populate database
3. Run `npm install`
4. Run `nodemon server.js`, or if you need to watch other parts of the app, we add the -e flag. So, when starting the server, we run instead: `nodemon -e js,html,css`




