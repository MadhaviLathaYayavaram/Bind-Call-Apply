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

The three  methods are function.prototype properties, developed by ECMAScript 5 version of javascript development. 


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

The bind method create a  new function where 'this' refers to the parameter in the parenthesis. This way the bind method enables calling a function with a specified 'this' value. We can specify calling parameters and connect with the bind method according to requirement. 


### Call() Method ###

Call method calls a function with a given 'this' value and arguments can be supplied individually. Just like a 'bind'  method, we can call any function and explicitly specify what 'this' should reference within the calling function. 

The call method accepts additional parameters. It executes the function it was called upon right away. It does not make a copy of the function it is being called upon. Call can be used to invoke a method within an owner object as an  argument/parameter. An object can use a method belonging to another object using call method. 

    '''
    var studentName =  function (subject, marker) {
        console.log (this.getStudentName() + ' Passed '+ subject + ' With ' + marks);
            }
            ...
     studentName.call(student, 'Science', 98);
     '''
     
  
  ### Apply() Method ###
  
Apply method serves the same purpose as 'call'. The difference is that Apply expects all the parameters in the form of an array. Call executes faster than 'Apply' because the input parameters are already formatted as per the need for the internal methods. 
  
 Call and apply are used when we want to pass a different 'this' value to the function. This means that we want to execute a function as if it were a method of a particular object. 


    '''
    var car = {
        registrationNumber: "GA12378",
        brand : "Toyota"
        displayDetails : function (ownerName) {
         console.log (ownerName+ , this is your car - "+ this.registrationNumber + " "+ this.brand); }
         }
     displaDetails.apply (car, ['Madhavi'];
     displayDetails.call (car,'Radhika'];
     
     '''
     
 Call, apply, bind enable us to set the 'this' context and enables to controlthe behavior of 'this' variable. If first argument is null or undefined, the 'this' variable points to the global object, but in case of 'strict' mode, it would be 'undefined'. It is specified in the example code below. 
 
     '''
     function greet() {
       return 'Hello ${this.name} }
       
     const person = {   name: 'Madhavi Latha' };
     
     greet.call (person);
     greet.apply (person);
     
     const greet2 = greet.bind(person);
     greet2();
     
     '''
     
      
