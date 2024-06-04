https://eloquentjavascript.net/00_intro.html
- intro to javascript, history, ecma script standards

https://eloquentjavascript.net/01_values.html
- operators, booleans, logicals

https://eloquentjavascript.net/02_program_structure.html
- for loops, if statements, variables (let, const, var)

https://eloquentjavascript.net/03_functions.html
-  functions, nested functions which leverages lexical scoping
- closure, recursion, growing functions in a mantainable way, pure functions don't have side effects and are idempotent
  
https://eloquentjavascript.net/04_data.html
- objects and methods, built in functions, spreading parameters, arrays, objects, mutability, optional property access with `?`, JSON.stringify and JSON.parse
- #todo go back to complete the last 2 exercises

https://eloquentjavascript.net/05_higher_order.html
- higher-order functions are those tht operate on other function either by taking them as arguments or returning them
- good for data processing by being able run filtering arrays, mapping functions and return an array that is same length but have each element transformed by mapping function, reduce to summarize and output condensed data
- Unicode give you 65,000 characters; UTF-16 invented to increase allocation, most chars use single 16 bit but others use 2 code units ( emojis and some Han characters)
- acc comes before curr for reduce

https://eloquentjavascript.net/06_object.html
- `this` binds to the object from where it's being called
- classes, prototypes and private functions with #, overriding methods and polymorphism
- symbols can be use to name a key the same as a reserved variable name
- iterator, inheritance
- encapulsate logic with objects and only expose an interface so you control how others interact with the object
- Different types can implement the same interface. Using an interface automatically to know how to work with many different objects that provide the interface is polymorphism
```
  Exercise 1

  class Vec {
    constructor(x, y) {
        this.x = x
        this.y = y
    }
    plus(another_vec) {
        return new Vec(this.x + another_vec.x, this.y + another_vec.y)
    }
    minus(another_vec) {
        return new Vec(this.x - another_vec.x, this.y - another_vec.y)
    }
    get length() {
        return Math.sqrt(this.x * this.x + this.y * this.y)
    }
}
console.log(new Vec(1, 2).plus(new Vec(2, 3)));
// → Vec{x: 3, y: 5}
console.log(new Vec(1, 2).minus(new Vec(2, 3)));
// → Vec{x: -1, y: -1}
console.log(new Vec(3, 4).length);
// → 5

Exercise 2

class Group {
    constructor() {
        this.members = []
    }
    static from(input) {
        const group = new Group()
        for (let i = input[0]; i <= input[1]; i++) {
            group.members.push(i)
        }
        return group
    }
    has(val) {
        let hasVal = false
        if (this.members.indexOf(val) > -1) {
            hasVal = true
        }
        return hasVal
    }
    add(val) {
        if (!this.has(val)) {
            this.members.push(val)
        }
    }
    delete(val) {
        let res;
        const idx = this.members.indexOf(val)
        if (idx > -1) {
            res = this.members.splice(idx, 1)
        }
    }
}
let group = Group.from([10, 20]);
console.log(group.has(10));
// → true
console.log(group.has(30));
// → false
group.add(10);
group.delete(10);
console.log(group.has(10));
// → false```
