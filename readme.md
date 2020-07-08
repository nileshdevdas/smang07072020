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


ng = > aNGular
1. ng new   ---> Allows you to create a new project   

What has ng new done 
    a) it has created a project folder imdbapp 
    b) inside the folder it has genertated some files and folder 
        node_modules # all the dependencies required are installed in the node module
            this is how javascript node works :- node_modules 

    ng version outside a angular project is different --> only gives you the version of the cli 
    ng version inside a angular project is different --> both the cli version as well as the version of the 
                                                         angular components framework installed 

    07/08/2020  10:24 AM    <DIR>          .
07/08/2020  10:24 AM    <DIR>          ..
07/08/2020  09:55 AM               246 .editorconfig (This is for vscode )
07/08/2020  09:55 AM               629 .gitignore    (This if for git not for angular)
07/08/2020  09:55 AM             3,816 angular.json  (Yes the main angular boostrap file )
07/08/2020  09:55 AM    <DIR>          e2e           (Selenium + Jasmin+ Karma + testing)
07/08/2020  09:56 AM    <DIR>          node_modules  (Dependencies)
07/08/2020  09:55 AM             1,307 package.json  (What are my dependencies this not angular npm                                                  dependencies file)
07/08/2020  09:55 AM             1,025 README.md     Not angular but sample project description
07/08/2020  09:55 AM    <DIR>          src          (The main folder this has everything .... )
07/08/2020  09:55 AM               435 tsconfig.json (Configuration about the typescript)
07/08/2020  09:55 AM             1,621 tslint.json   (Configuration about typescript linting)

what is in my angular.json :- 

ng new ## creates a new angular app 
ng serve ## starts a local development webserver and launches the angular application s
ng build ## creates a code for deployment to the production generallly  --prod with not generate the 
            .map (Debug files)
ng test  ## runs testing  for unit testing 


# ng new if was use to create a new app 
# ng serve will be used to run the app in development mode 
# ng build will generate output files for production deployment 
# ng build has 2 variants --prod  and without --prod  the --prod disables the debug mode 

ng generate 
What is in my source folder 
Every angular angular aplication has modules 
rootModules
    /

A Moduuel : 

The root module is app.module.ts 

A modules is collection of all  the components of that module 
a modules is nothing but a namespace :- 
The module is going act a shell for the following 
    a) Component 
    b) Route 
    c) Directive 
    d) Pipes
    e) Services 
    f) the files surrounding 




A modules can have other modules inside it 
    A module can have 
    components :- Angular Compoents 
    own services 
    own pipes and directive 
    own routes 
    own guards 
    own configuration 

How to create a component 
ng g c <youcomponnet> will create a component
How to add the component to a page 
a component can be added to any component page so if you want a component to appear inside 
as speific page you will need to add the component-selector tag in the parent components 
html file 
Here in our case we dont have any other component than the root componenet hence we will 
definitely add the component tthe root compoinent html app.component.html 
<app-hello></app-hello>
How to understand the component files 
   a component is made of majorly 3 things 
   a) the ts file of the component (Controller file)
   b) The View (Css and Html )
   c)  The model is missing ? Controller --> State is alos model state 
How to use state of the component on the page
Declara a variable in the component and once you have the varibale 
Variable can be used directly in the  view 
{{varible}} ->expression 

|--- angular/cli  we installed the angular 

how to create a new angular project :- 
ng new <projectname>

What gets created 
node_modules (dependencies )//npm i when done it will pick all the module package json 
package.json --> has the details of dependencies 
angular.json  => instructions for ng serve ng build ng test ng e2e --> its configuration 
app folder ---> this is your application folder : 
    root module 
        app.module.ts 
            |--- app.component.ts <app-root><app-root>
                 app.component.html 
                 app.component.css 
Each Module is supposed to be registered in the app.module.ts
index.html ==-> app-root     

# the next things we are look at the module file 
Components need to be registered in the module.ts
Pipe/Directive/Component/Gaurds

Services : Needs to be provided 

PollyFills : Angular to support old browser like Internet explorer or old browsers 


Lets add some bootstrap to my page 
#### how to add bootstrap to you angular 

Step 1 : first download the bootstrap to node_modules 
in you project folder -> 
npm i  bootstrap

Step 2 :  you will need to add this entry in the angular.json 
           "styles": [
              "src/styles.css",
              "node_modules/bootstrap/dist/css/bootstrap.min.css" // add the requried css
            ],

Step 3 :  restart you angular ng serve any changes to the angular.json only impact after 
            relaunching the ng serve 

step 4 :   Now test you page adding a boostrap class 
                <button class="btn btn-success">Clickme </button>



























































































