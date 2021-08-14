# Bind, Apply, and Call Methods in JavaScript #

Bind, Call and Apply are very important tools in functional programming of JavaScript which have a relationship with 'this' variable. Everything in Javascript is an object. A function is also an object that has all the properties of a normal object and some hidden properties such as 'Code' property and an optional name property which is anonymous in JS.

An internal property 'code' holds all the function code that we write in a function. Call, Apply, and Bind are built-in methods in all Javascript functions.

The execution context and call stack are important phases in a program result. Execution context is a wrapper around the currently executing code.  It consists a 'this' variable which refers to the current object. It contains the variable environment which is a place in memory to make variable live and relate on with each other. The outer environment of a function is 'null' at global level. 

Call, apply, and bind methods enable us to set the 'this' context and also enables to control the behavior of 'this' variable.

Example:

    '''

    function greet() {
      return 'Hello ${this.name}' }
    
    const person = {
      name : "Madhavi Latha" }
      
    greet.call (person);
    greet.apply (person);
    
    const greet2 =  greet.bind (person)
    greet2();
  
    '''
When the first argument is null or undefined,the 'this'variable points to the global object. But in the strict mode, it would be undefined.

## Functionalities of the three methods ##

The call() method invokes a function and allows to pass the arguments one by one. 

The apply() method invokes a function and allows to pass arguments as an array. 

The bind() function returns a new function allowing us to passany number of arguments in this array.


### Bind() Method ###

Bind() creates a new function when it is called and has its 'this' keyword set to the provided value.

    '''                 
    var employee = {
      firstName: "Madhavi",
      lastName:  "Latha",
      getEmployee: function() {
        var fullName = this.firstName+ ' '+ this.lastName;
        return fullName;
        }
      };
      
      var employeeName function() {
        console.log (this.employeeName () + ' is passed!';;
       }
       
      var logemployeeName = employee.bind(employee);
      logemployeeName ();

  
    '''
    
In the above example of code chunk, Javascript Engine creates a new 'studentName' instance and  bind 'student' object as its 'this' variable and copies the studentName() function. After creating a copy of the studentName function, it is able to call 'logStudent'(). although it was not existing on the student object initially. It will recognize all the properties and methods of student object automatically.

After a bind() value, we can use the function just like it was any other normal function. We can update the function to accept parameters and pass them as well. We use bind method to call a function with the 'this' value, which refers to the same object which is currently selected. It allows us to easily set which object will be found by the this keyword when a functionor method is invoked.


