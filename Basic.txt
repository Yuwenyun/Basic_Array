//create object with new
var person = new Object();
person.name = "Owen";
person.age = 23;
//create object with json
var person =
{
    name:"Owen",
    age:23
};

//access property of object
alert(person.name);
//access property in indexer way
alert(person["age"]);


//create Array object
var array = null;
array = new Array();
array = new Array(20); //specify the length
array = new Array("red", "blue");
array = Array("red"); //omit new
array = ["rad"];
//use length property to add/remove elements of array
array = [1, 2, 3];
array.length = 2;
alert(array[2]); //undefined, element 3 deleted

//check if an object is Array
if(array instanceof Array)
    alert(true);
if(Array.isArray(array)) //better
    alert(true);

//normal methods of Array
var array = [3, 2, 7, -5];
alert(array.join("#")); //create string with # as delimeter
//use array as stack
array.push("owen");
alert(array); //3, 2, 7, -5, owen
array.pop();
alert(array); //3, 2, 7, -5
//use array as queue
array.push(true);
array.shift();
alert(array); //2, 7, -5, true

array.reverse();
alert(array); //true, -5, 7, 2
array.sort();
alert(array); //-5, 2, 7, true
array.sort(function(a, b)
{
   if(a > b)
       return -1;
   else if(a < b)
       return 1;
   else
       return 0;
});
alert(array); //7, 2, true, -5
alert(array.indexOf(true));

/*
 *iterator related methods
 */
//every() accepts function with 3 args in
//arguments array, when every item in the func 
//returns true, every() returns true
alert(array.every(function()
{
   //arguments[0]: current item
   //arguments[1]: index of current item
   //arguments[2]: array
   alert(arguments[0] + ", " + arguments[1] + ", " + arguments[2] + ", " + arguments[3]);
   return true;
}));
//some() is the same as every(), only return true when
//at least one item in func returns true
alert(array.some(function()
{
   //arguments[0]: current item
   //arguments[1]: index of current item
   //arguments[2]: array
   alert(arguments[0] + ", " + arguments[1] + ", " + arguments[2]);
   return false;
}));
//get those items satisfy the condition
alert(array.filter(function()
{
    if(arguments[0] > 0)
        return arguments[0];
}));
//return no value
alert(array.forEach(function()
{
    alert(arguments[1]);
}));
//return result of each item in func 
alert(array.map(function()
{
    return arguments[0] * 2;
}))