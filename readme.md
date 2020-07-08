1. What is Client Side MVC 
2. Browser is server ?  
    Write code and control the interaction i the browser 

What is that i needd from the server ? 
React 
Angular 
ViewJs 
Backbone



#nuget 
#maven
#pip 
#npm 

node: (yes u use node in javacript for locally testing the applications ) // ng serve 
npm:  (add the modules to the the angular --> Dependencies )


npm install typescript (local install --> own environment)
# typescript compile and should be installed globally 

All the tools you will install as a global install 
npm install -g typescript (on the global location )

# npm install -g  typescript
# tsc -version

THe TSC Version will tell you the required :- version of you typescript compiler installed : 

create a new file  example1.ts 
# contents 
console.log("Hello World" )

# how to compile 
tsc  <urfilename>

#  should generate the .js 


1. You did not 
npm install -g typescript 

2.  old prompt 
    close the old prompt 

https://github.com/nileshdevdas/smang07072020.git



Data types at typescript 
/// typescript has data types 
var a: number = 1
var username: string = 'xxx'
var password: string = 'xxxx'
var x : any = 0
var z : boolean = true;

#############################################

import { Department } from "./example2";

class Employee {
    // constructor only called when object is created 
    constructor(public a: string) {
        console.log("Employee constructor")
    }
    /// a method that returns anytype as i did not define one
    // now defined a return type for the function 
    getMeMoney(): number {
        console.log("in Employee..")
        return 100;
    }

}

class Manager extends Employee {
    constructor(public nameofemp) {
        super(nameofemp); // need te super class constructor to work 
        console.log("Manaager Constructor")
    }

    getMeMoney(): number {
        console.log("in Manager")
        return super.getMeMoney()+ 0;
    }
}
var empinst = new Manager("username");
console.log(empinst.getMeMoney());
console.log(empinst.a)
console.log(empinst);




Example of inherintecen and supper 
// the import 
import { Department } from "./example2";

/// base class ++ export  
export class Employee {
    constructor(public a: string) {
        console.log("Employee constructor")
    }
    getMeMoney(): number {
        console.log("in Employee..")
        return 100;
    }
}
/// class with extenstion (inheritence) 
class Manager extends Employee {
    constructor(public nameofemp) {
        super(nameofemp); // need te super class constructor to work 
        console.log("Manaager Constructor")
    }

    // overriden function
    getMeMoney(): number {
        
        console.log("in Manager")
        // call parent function
        return super.getMeMoney() + 10293;
    }
}
var empinst = new Manager("username");
console.log(empinst.getMeMoney());
console.log(empinst.a)
console.log(empinst);
------------------------------------------------------------------------------------------------------------Day 2 : 
1. understand what is angular cli
2. install a angular cli 
3. create a new project using the angular cli 
4. Understand the project scaffolding 
5. Understand the structure of files and thier contents 
6. Run the sample application 
7. Start Angular basics understanding on what is a angular component , angular modules , angular directives, angular pipes services guards intercepts 
8. new new ng serve , ng build ng generate and related things 

What is angular CLI : 
Command Line Interface :- 
Using the CLI you can create a project template in angular 

# i am trying to install a specific version of the cli 
npm i -g  @angular/cli@7.3.10




















