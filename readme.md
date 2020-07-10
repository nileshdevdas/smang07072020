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




Demo Card Layout 
<div class="container-fluid">
  <div class="row">
    <div class="col-sm-4">
      <div class="card">
        <div class="card-header bg-dark text-white">Component</div>
        <div class="card-body">xxxx</div>
      </div>
    </div>
    <div class="col-sm-4">
      <div class="card">
        <div class="card-header">xxxx</div>
        <div class="card-body">xxxx</div>
        <div class="card-footer">Copyrith Vinsys</div>
      </div>
    </div>
    <div class="col-sm-4">
      <div class="card">
        <div class="card-header">xxxx</div>
        <div class="card-body">xxxx</div>
      </div>
    </div>
  </div>
</div>

-------------------------------------------------------------------------------------------------
Complete angular/cli 
Complete angular Strcuture 
Complete angular file system 
ng serve 
ng build 
ng new 
ng g c (generate component)
{{}} --> The expression 
State in the component 
Module -> A module is like a package 
angular.json (How it works)
node_modules 
npm
ts Typescript 

Component : ts + css + html 
select tag 
Environtment Setup / Project Setup / Components 
General MVC / Using Npm and Other things ng 
how to add boostrap or any other dependant libraries to our applcation 
------------------------------------------------------------------------------------------------
1. Data Binding 
    a) oneway   ====> from html to Component ts 
                ----> from ts to html 
    b) twoway   from both the sides when ever it changes either side it impacts both 

2. Event Binding (clicks , events )

3. Directives 

4. Pipes 


add a new component 
ng g c <componentname> ==>  Component gets added 

find the location where you wish add the component add the selector tag in the 
html of the parent component 
ng serve and check if the parent and child are being rendered 

Add a Movies state to you movies list 
movies = ['','','','','']


We are working with a single page application 
1. The Page is your framework or your application 
2. thes session is your environment in which application

Is HelloComponent / Appcomponent the Roor
The page Root Layout is The AppComponent 
         Route -> Home --> Href ==> HomeComponent
                  About-US ->Href --> AboutUsComponent                   

index.html
    <app-root></app-root>=====> component who has  selector called app-root
                                        AppComponent:
                                            app.component.html  // view  template
                                            app.component.ts // state & behaviour
                                            app.component.css  // l&f
                                            

app.component.html 
    <app-navbar></app-navbar> ========> component 
                                        NavbarComponent
                                            navbar.component.html  / view
                                            navbar.component.ts  / state & behaviour
                                            navbar.component.css  / L&F


    <app-footer></app-footer>




index.html -> root-component-> Renders and rendes html --> It finds furtther component =--> 
it renders those in those component if i have component ---> 

app.module.ts (Repository (All all component in the module))
index.html(app-root)
|
|-------Root (app-layout)
          |-------Layout (app-header/app-grid/app-footer)
                     |-------Header (content)
                     |-------Grid (app-comp1, app-comp2)
                               |---------Comp1 (app-movielist)
                                            |-----MovieList 
                               |---------Comp2 (content)
                     |-------Footer (content)
==============================
1. ng g c navbar
2. ng g c footer 
3. ng g c layout 
4. ng g c movieslist 
5. ng g c moviesdetails
6. ng g c movieratings 
======================================
AppComponent 
    |-------navbar
            layout
                |----- movieslist
                |------moviesdetails 
                |------moviesratings 
            footer 

ng new <>
cd yourproject 
npm i bootstrap 
----------------------------------------------------------------------------------------------------

Data Binding :- from component to page (state) {{}}
                from page to component  (Forms)  

{{}}

Event Binding 
()
movielist == component
ngFor == Directive 
()  == event binding 
{{}} == data binding 
|  === pipe 

Component 
Pipe




-------------------------------------------------------------------------------------------------
How to build to component 
How to make use of the pipes  | date , curreny , uppercase . ... 
How to make use of the components in the page 
How to make the components display content and Create Child Components 
How to make state binding {{}}
How to make State iteration *ngFor 
How to make use of the Action Event binding ()
How to make use of style sheets bootstrap  in our code 
How to make ng build and deploy it on external server 
How to make use of the ng serve to run you applicatiokn 
Role of the angular.json 
Role of the Typescript 
Role of ts files and the html css that make component 
What angular cli ng build , ng serve ng g c 
What is the use of npm install where -g is global and without -g is local 
    for project dependencies we should not use -g 
    for tool and global dependency we should use -g (IF you are installing cli -g is required)
    but if you are install a project library bootstrap you dont need -g 
We have seen how augury pluging works debug of state + component hierachy 
We have also seen we can type script debug if --prod is not enabled and allow map files 
We have how to make use css and use of the component css and we have not create component roles 
    navigator / footer / layout / movieslist / moviesdetails .... (Component model) 
We also seen what is module  
        Collection the components, the import of moudles 
        |---- Modules 
                a) Declares components 
                    pipes, directives, components, guards 
                b) Provides Services 
                    non ui components 
                c) Imports Other Modules
                    i depend on external module unless i import i cannot use it  
                d) Boostraps its own start up Classes 
                e) exports 
                        if you wish to create a component and let other modules 
                        use you component then you must export to let the 
                        other modules import and use the component 
                
---------------------------------------------------------------------------------------------------
Pattern : Singleton : ? 
A service is a non ui component 
A service is injectible component 
A serviec is singleton (Single Instance )instantiated only once in framework 
A service is shareble 
A service is something which would carry statless reusable business logic or 
    immutable state for the ui 
A service can bind two components 
A service is reusable peice of code 
                            Component 1                 Component2
                                 |                          |
                                 ----------------------------
                                                |
                                            Service 1 (Single instance )
This the most important part of the configuraotin wher the weaving of the angular componenetn 
when there is no service Service :- 

Single Ton ( Single instance ) Lazy and Eager :- whoever calls first that time the instance gets created but next time any one calls the same instance is always returen 
Eager : as soon as the frameword the page is up the instance is created and every time any one calls 
the simple activity is to return the instance 
What goes in my instances (Shareable business logic  )
Shareable immutable data Genrally if you dont want the data to be changed by any one 
or any static / globals any such things are implemented here 

<button (click)="fetchData()">
Your Html -->(click) 
    Component (function)  fetchData()
         ----> Service ---->    fetchInfo()
                    Http API ---->  http.get('url')
                            ---->Rest API 
                                    -----> Json 
                    HttpResp<------
            <------
    <--------
{{}}
Async in java script things are async calls Promise : is the most
-----> Request to the Caller and i dont wait 
    --> Register a call back saying tha hey i have called you please promise when you are done 
        you will call my call back 
Hey Nilesh give me data ---> I am busy 
    okay no issue when you done give me call back 
         ? Register a function as call back function -> 
         This allows me to do things in promisory way 
From your traditional Call as Call - Invoke --- Wait Return 
                             Call Invoke Return 
                                            Reverse Invoke 
On A click of a button -> Call something i may take time and then it may call back my response 

Work on the sync version 
Move to aysnc version 
move to the implementation of end to end services: 

What is a service : 
service is a singleton 
How can i create a service 
ng g s  (Creates service)

How can i use the service : 
you can use the service by dependency injection :- 
    dont call me i will call you 
    you will not instantiate or find the service just inject it 
    in you components constructor jjust inject type and the angular will find 
    the object type and give us the reference 

What should i write in my service 
    any business logic 
    any compute logic 
    any logic to fetch data from server 
    any sharing logic 
    any logic that is common goes here 

Where i am going to create small a service --> 
What make a component a component 
@Component makes this as a component 
What makes a service a service 
@Injectible makes this as a service 

Thats what it means :- for the framework 






How to create a service : 
ng g  s  ---> creates a service 
how is a service service 
@Injectible 
How to use the service 
A service is injectible in your Component 
how 
You Can directlye 
constructor(yourvar:ServiceClasss) // How does this work 
Angular Internally check that oh i have a constructor of type x variable 
It goes in the service registery an fetches the service type and injects it : 
Hence its known as dependency injection :- 
We would be put the responsibility of finding the service and getting the detail injected to angular
and not us : dont call me i will call you is what angular say : inject service just refere me 





1. Create a service ng g s <yourservice name>
2. now moveyou movies into the service while maitaining the movies data binder varibale intact 
    in your component however you can use different name inthe service or same 
3.  like you service make variable private 
    export Class FetchMovieService {
        private movies = ['','' ,''] // ideally these values would come from the webservice /api

        getMovies(){
            return this.movies; 
        }
    }

4. how to use service 
     in any component where you wish to use the service :- 
     in the constructor of that componenent you need to inject the service 
     a)  var: ServiceType  if you declare 
            public var :  ServiceType then it also exposes a local variable 
            public fms : FetchMovieService 
            automatically exposes fms variable as a part of the object 

            any where in the code you can this.fms.xxxx where xxx is varibale(public) and methods 
        you local data binded variable ==> is getting changed by a call to the service ... 
        this.movies = this.fms.getMovies()


I want first time to introduce a module ussage 
HttpClient --> is  service which available in the HttpClientModule 
and i will need to import the HttpClientModule in my modules first if i wish to use 
HttpClient 


Your service now wishes to talk to http : - 
1. HttpClient is service that is what you will do tofetch 
    get/post/put/delete/options/head 

2. The HttpClient cannot be used unless and untile the module exports it is imported in your 
    module you module need to depnd on the http module 
    import : [ 
        BrowserModule, 
        HttpClientModule
    ]
3.  Remember HttpClient is service so it need to be injected : 
    Ohh byu i am already a service can inject a service inside a service yes (Composite)
    a service can be export to be injected in  component or other service singletons 
    in your service in your constructor of the service 
    constructor(httpClient: HttpClient) // this will fail if you dont have the Imported module 
        HttpClientModule

4. now your component will be getting promise when service function called for this 
getMovies(): Observable<any> {
    /// the movies_url is a constant centralized in one file
    return this.httpClient.get(MOVIES_URL);
  }

  5.  Your component now should be subscribing it 
         this.fms.getMovies().subscribe((data) => {
      this.movies = data;
    });
    obs = this.fms.getMovies(); 
    obs.subscribe((data)=>{
        this.movies = data;
    });

    // (data)=>{}



                                            












5. Services 

6. Routes 

7. Guards 

8. Forms 

9. Security 

10. Angular as Mobile aps 

11.  Testing 















































































