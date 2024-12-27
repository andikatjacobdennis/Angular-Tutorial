# Introduction
**Node.js and NPM Commands**

- `node -v`: Check Node.js version
- `npm -v`: Check npm version
- `npm uninstall -g @angular/cli`: Uninstall existing Angular CLI
- `npm install -g @angular/cli@10.0.6`: Install Angular CLI version 10.0.6
- `npm start`: Runs the development server using ng serve.
- `npm test`: Executes unit tests using tools like Karma and Jasmine.
- `npm run build`: Creates an optimized production build of the app.
- `npm install <package-name>`: Installs a new dependency.
- `npm install <package-name> --save-dev`: Installs a new dev dependency.
- `npm install -g <package-name>`: Installs a package globally on your system.

**Angular CLI Commands**

- `ng version`: Check Angular CLI version
- `ng new my-angular-app`: Create a new Angular application
- `cd my-angular-app`: Navigate to the project folder
- `ng serve`: Start the development server
- `ng generate component my-component`: Generate a new component
- `ng lint`: Checks for coding standard violations.
- `ng e2e`: Runs end-to-end tests.

# Angular Project Structure
**Main Files and Folders**

- index.html: The main entry point of the application
- app/: The main application folder
  - app.component.ts: The main application component
  - app.component.html: The HTML template for the main component
  - app.component.css: The CSS styles for the main component
  - app.routes.ts: The routing configuration for the application
- assets/: Folder for static assets (images, fonts, etc.)
- environments/: Folder for environment-specific configurations
# Interpolation and Style Binding
**Component (app.component.ts)**

```typescript

import { Component } from '@angular/core';

@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.css']
})
export class AppComponent {
  title = 'my-angular-app';
  currentDate: Date = new Date();
  techData = {
    frontend: 'Angular',
    backend: 'Node.js',
    programmingLanguage: 'TypeScript',
    database: 'MongoDB'
  };
  fontSize: string = '20px';
  isHighlighted: boolean = true;

  getGreeting(): string {
    return 'Hello from a method!';
  }
}

```

**Template (app.component.html)**

```html

<h1>{{ title }}</h1>

<p>Today's date is: {{ currentDate | date }}</p>

<p>{{ getGreeting() }}</p>

<p [style.fontSize]="fontSize">This text has dynamic font size.</p>

<p [style.color]="isHighlighted ? 'red' : 'black'">

`  `This text color changes based on a condition.

</p>

<h2>Technology Stack</h2>

<ul>

`  `<li><strong>Frontend:</strong> {{ techData.frontend }}</li>

`  `<li><strong>Backend:</strong> {{ techData.backend }}</li>

`  `<li><strong>Programming Language:</strong> {{ techData.programmingLanguage }}</li>

`  `<li><strong>Database:</strong> {{ techData.database }}</li>

</ul>

**Styles (app.component.css)**

h1 {

`  `text-align: center;

`  `color: darkblue;

}

p {

`  `margin: 10px;

`  `font-family: Arial, sans-serif;

}

ul {

`  `list-style-type: none;

`  `padding-left: 0;

}

li {

`  `margin: 10px;

`  `font-size: 18px;

}

strong {

`  `color: darkgreen;

}
```

# Event Handling in Angular
**Basic Syntax**

<button (event)="method()"></button>

**Event Binding with Parameters**

<button (click)="displayMessage('Hello from Angular!')">Show Message</button>

**Two-Way Data Binding with ngModel**

<input type="text" [(ngModel)]="name" />

**Enabling ngModel in Angular**

1. Import FormsModule in app.module.ts:

import { FormsModule } from '@angular/forms';

@NgModule({

...

`  `imports: [

...

`    `FormsModule

`  `],

...

})

export class AppModule { }

**Event Handling Methods**

logClick(event: MouseEvent): void {

`  `console.log(`Mouse clicked at X: ${event.clientX}, Y: ${event.clientY}`);

}

displayMessage(message: string): void {

`  `alert(message);

}
**


**Component Properties**

name: string = '';

title: string = 'my-angular-app';

currentDate: Date = new Date();

techData = {

`  `frontend: 'Angular',

`  `backend: 'Node.js',

`  `programmingLanguage: 'TypeScript',

`  `database: 'MongoDB'

};
# For Loops and If Statements in Angular
**For Loops (\*ngFor)**

<div \*ngFor="let item of items; let i = index">

`  `<!-- Content to display -->

</div>

**If Statements (\*ngIf)**

<div \*ngIf="condition">

`  `<!-- Content to display if condition is true -->

</div>

**Combining For Loops and If Statements**

<ul>

`  `<li \*ngFor="let item of items">

`    `<span \*ngIf="item.inStock">{{ item.name }} is in stock</span>

`    `<span \*ngIf="!item.inStock">{{ item.name }} is out of stock</span>

`  `</li>

</ul>
**


**Component-Side For Loops and If Statements**

**For Loop**

for (let num of this.numbers) {

`  `// Process data

}

**If Statement**

TypeScript

if (num % 2 === 0) {

`  `// Process data

}

**Example Use Cases**

**Displaying a List of Items**

TypeScript

export class AppComponent {

`  `items = ['Item 1', 'Item 2', 'Item 3'];

}

HTML

<ul>

`  `<li \*ngFor="let item of items">{{ item }}</li>

</ul>

**Conditionally Displaying Content**

TypeScript

export class AppComponent {

`  `isLoggedIn = true;

}

HTML

<div \*ngIf="isLoggedIn; else notLoggedIn">

`  `Welcome back, user!

</div>

<ng-template #notLoggedIn>

`  `Please log in to continue.

</ng-template>


# Directives
**Types of Directives**

1. **Component Directives**: Custom components with a template.
1. **Structural Directives**: Alter the DOM structure (e.g., \*ngIf, \*ngFor, \*ngSwitch).
1. **Attribute Directives**: Modify element behavior or appearance (e.g., ngClass, ngStyle).

**Structural Directives**

**\*ngIf: Conditionally includes an element.**

<div \*ngIf="condition">Content to display</div>

**\*ngFor: Iterates over a collection.**

<ul>

`  `<li \*ngFor="let item of items">{{ item }}</li>

</ul>

**\*ngSwitch: Switch-case directive.**

<div [ngSwitch]="color">

`  `<p \*ngSwitchCase="'red'">You chose red.</p>

`  `<p \*ngSwitchCase="'blue'">You chose blue.</p>

`  `<p \*ngSwitchDefault>Choose a color.</p>

</div>

**Attribute Directives**

**ngClass: Adds or removes CSS classes.**

<div [ngClass]="{'active': isActive, 'inactive': !isActive}">Toggle me!</div>

**ngStyle: Applies inline styles.**

<div [ngStyle]="{'color': textColor, 'font-size': fontSize + 'px'}">Styled Text</div>
**


**Creating Custom Directives**

**1. Create an Attribute Directive**

1. Generate a directive: ng generate directive directives/highlight
1. Implement logic in the directive:

TypeScript

@Directive({

`  `selector: '[appHighlight]',

})

export class HighlightDirective {

`  `@Input() appHighlight = '';

`  `constructor(private el: ElementRef) {}

`  `@HostListener('mouseenter') onMouseEnter() {

`    `this.highlight(this.appHighlight || 'yellow');

`  `}

`  `@HostListener('mouseleave') onMouseLeave() {

`    `this.highlight('');

`  `}

`  `private highlight(color: string) {

`    `this.el.nativeElement.style.backgroundColor = color;

`  `}

}

1. Use the directive in a template:

<p appHighlight="lightblue">Hover over me to see the highlight!</p>
**


**Directive Lifecycle Hooks**

1. **ngOnInit**: Called once the directive is initialized.
1. **ngOnChanges**: Called when input properties change.
1. **ngOnDestroy**: Called before the directive is destroyed.

Example:

TypeScript

@Directive({

`  `selector: '[appLogLifecycle]',

})

export class LogLifecycleDirective implements OnInit, OnDestroy {

`  `ngOnInit() {

`    `console.log('Directive initialized');

`  `}

`  `ngOnDestroy() {

`    `console.log('Directive destroyed');

`  `}

}


# Built-in Pipes

|**Pipe**|**Purpose**|**Example Usage**|
| :- | :- | :- |
|date|Formats dates.|`{{ today|
|uppercase|Converts text to uppercase.|`{{ 'hello'|
|lowercase|Converts text to lowercase.|`{{ 'HELLO'|
|currency|Formats a number as currency.|`{{ 1234.5|
|percent|Formats a number as a percentage.|`{{ 0.25|
|json|Converts an object to a JSON string.|`{{ myObject|
|slice|Extracts a portion of a string or array.|`{{ array|
|async|Unwraps Promises or Observables automatically.|`{{ asyncData|

**Custom Pipe Example**

TypeScript

import { Pipe, PipeTransform } from '@angular/core';

@Pipe({

`  `name: 'reverse'

})

export class ReversePipe implements PipeTransform {

`  `transform(value: string): string {

`    `if (!value) return '';

`    `return value.split('').reverse().join('');

`  `}

}
**


**Using Pipes in Templates**

<p>Today's Date: {{ today | date:'fullDate' }}</p>

<p>Uppercased Name: {{ name | uppercase }}</p>

<p>Price: {{ price | currency:'USD' }}</p>

**Chaining Pipes**

\-------------------

<p>{{ name | uppercase | slice:0:4 }}</p>


# Routing
**Basic Routing Configuration**

TypeScript

import { NgModule } from '@angular/core';

import { RouterModule, Routes } from '@angular/router';

import { HomeComponent } from './home/home.component';

import { AboutComponent } from './about/about.component';

const routes: Routes = [

`  `{ path: 'home', component: HomeComponent },

`  `{ path: 'about', component: AboutComponent },

`  `{ path: '', redirectTo: 'home', pathMatch: 'full' },

`  `{ path: '\*\*', redirectTo: 'home' }

];

@NgModule({

`  `imports: [RouterModule.forRoot(routes)],

`  `exports: [RouterModule]

})

export class AppRoutingModule { }
**


**Route Parameters**

TypeScript

const routes: Routes = [

`  `{ path: 'product/:id', component: ProductDetailComponent }

];

TypeScript

import { Component, OnInit } from '@angular/core';

import { ActivatedRoute } from '@angular/router';

@Component({

`  `selector: 'app-product-detail',

`  `template: `

`    `<h2>Product Details</h2>

`    `<p>Product ID: {{ productId }}</p>

`  ``,

})

export class ProductDetailComponent implements OnInit {

`  `productId: string | null = null;

`  `constructor(private route: ActivatedRoute) { }

`  `ngOnInit(): void {

`    `this.productId = this.route.snapshot.paramMap.get('id');

`  `}

}

**Lazy Loading Routes**

TypeScript

const routes: Routes = [

`  `{

`    `path: 'products',

`    `loadChildren: () => import('./features/products/products.module').then(m => m.ProductsModule)

`  `}

];
**


**Route Guards**

TypeScript

import { Injectable } from '@angular/core';

import { CanActivate, Router } from '@angular/router';

@Injectable({

`  `providedIn: 'root'

})

export class AuthGuard implements CanActivate {

`  `constructor(private router: Router) { }

`  `canActivate(): boolean {

`    `const isAuthenticated = /\* logic to check if user is authenticated \*/;

`    `if (!isAuthenticated) {

`      `this.router.navigate(['/login']);

`      `return false;

`    `}

`    `return true;

`  `}

}

TypeScript

const routes: Routes = [

`  `{ path: 'profile', component: ProfileComponent, canActivate: [AuthGuard] }

];


# Forms
**Importing FormsModule**

TypeScript

import { NgModule } from '@angular/core';

import { BrowserModule } from '@angular/platform-browser';

import { FormsModule } from '@angular/forms'; // Import FormsModule

import { AppComponent } from './app.component';

@NgModule({

`  `declarations: [AppComponent],

`  `imports: [

`    `BrowserModule,

`    `FormsModule // Add FormsModule

`  `],

`  `providers: [],

`  `bootstrap: [AppComponent]

})

export class AppModule { }

**Creating a Form**

<form #registrationForm="ngForm" (ngSubmit)="onSubmit(registrationForm)">

`  `<!-- Form fields here -->

</form>

**Form Fields with Validation**

HTML

<!-- First Name -->

<div class="mb-3">

`  `<label for="firstName" class="form-label">First Name</label>

`  `<input type="text" id="firstName" class="form-control" name="firstName" [(ngModel)]="formData.firstName" required minlength="3" />

`  `<div \*ngIf="registrationForm.controls.firstName?.invalid && registrationForm.controls.firstName?.touched" class="text-danger">

`    `First name is required and must be at least 3 characters long.

`  `</div>

</div>
**


**Handling Form Submission**

TypeScript

onSubmit(form: any): void {

`  `if (form.valid) {

`    `console.log('Form Submitted:', this.formData);

`  `} else {

`    `console.error('Form is invalid!');

`  `}

}

**Key Validation Rules**

1. **Required**: required
1. **Minimum Length**: minlength="3"
1. **Maximum Length**: maxlength="10"
1. **Email**: email
1. **Pattern**: pattern="^[0-9]{10}$"


# Reactive Forms
**Importing ReactiveFormsModule**

TypeScript

import { NgModule } from '@angular/core';

import { BrowserModule } from '@angular/platform-browser';

import { ReactiveFormsModule } from '@angular/forms';

@NgModule({

`  `declarations: [

`    `// Your Components

`  `],

`  `imports: [

`    `BrowserModule,

`    `ReactiveFormsModule,

`  `],

`  `providers: [],

`  `bootstrap: [/\* Your App Component \*/]

})

export class AppModule { }

**Creating a Basic Form**

TypeScript

import { Component } from '@angular/core';

import { FormGroup, FormControl, Validators } from '@angular/forms';

@Component({

`  `selector: 'app-reactive-form',

`  `templateUrl: './reactive-form.component.html',

`  `styleUrls: ['./reactive-form.component.css']

})

export class ReactiveFormComponent {

`  `registrationForm = new FormGroup({

`    `username: new FormControl('', [Validators.required, Validators.minLength(3)]),

`    `email: new FormControl('', [Validators.required, Validators.email]),

`    `password: new FormControl('', [Validators.required, Validators.minLength(6)])

`  `});

`  `onSubmit() {

`    `console.log(this.registrationForm.value);

`  `}

}**

**Using FormBuilder**

TypeScript

import { Component } from '@angular/core';

import { FormBuilder, Validators } from '@angular/forms';

@Component({

`  `selector: 'app-dynamic-form',

`  `templateUrl: './dynamic-form.component.html',

`  `styleUrls: ['./dynamic-form.component.css']

})

export class DynamicFormComponent {

`  `constructor(private fb: FormBuilder) {}

`  `profileForm = this.fb.group({

`    `firstName: ['', Validators.required],

`    `lastName: [''],

`    `address: this.fb.group({

`      `street: [''],

`      `city: [''],

`      `postalCode: ['']

`    `})

`  `});

`  `onSubmit() {

`    `console.log(this.profileForm.value);

`  `}

}
**


**Adding Dynamic Controls**

TypeScript

import { Component } from '@angular/core';

import { FormArray, FormBuilder, Validators } from '@angular/forms';

@Component({

`  `selector: 'app-dynamic-controls',

`  `templateUrl: './dynamic-controls.component.html',

`  `styleUrls: ['./dynamic-controls.component.css']

})

export class DynamicControlsComponent {

`  `constructor(private fb: FormBuilder) {}

`  `skillsForm = this.fb.group({

`    `name: ['', Validators.required],

`    `skills: this.fb.array([

`      `this.fb.control('') // Initial skill

`    `])

`  `});

`  `get skills() {

`    `return this.skillsForm.get('skills') as FormArray;

`  `}

`  `addSkill() {

`    `this.skills.push(this.fb.control(''));

`  `}

`  `removeSkill(index: number) {

`    `this.skills.removeAt(index);

`  `}

`  `onSubmit() {

`    `console.log(this.skillsForm.value);

`  `}

}


# Reactive Dynamic Forms
**Importing ReactiveFormsModule**

TypeScript

import { NgModule } from '@angular/core';

import { BrowserModule } from '@angular/platform-browser';

import { ReactiveFormsModule } from '@angular/forms';

@NgModule({

`  `declarations: [

`    `// Your Components

`  `],

`  `imports: [

`    `BrowserModule,

`    `ReactiveFormsModule,

`  `],

`  `providers: [],

`  `bootstrap: [/\* Your App Component \*/]

})

export class AppModule {}
**


**Creating a Dynamic Form**

\-------------------------------

TypeScript

import { Component } from '@angular/core';

import { FormArray, FormBuilder, FormGroup, Validators } from '@angular/forms';

@Component({

`  `selector: 'app-dynamic-form',

`  `templateUrl: './dynamic-form.component.html',

`  `styleUrls: ['./dynamic-form.component.css']

})

export class DynamicFormComponent {

`  `dynamicForm: FormGroup;

`  `constructor(private fb: FormBuilder) {

`    `this.dynamicForm = this.fb.group({

`      `name: ['', Validators.required],

`      `items: this.fb.array([]) // Start with an empty array

`    `});

`  `}

`  `get items() {

`    `return this.dynamicForm.get('items') as FormArray;

`  `}

`  `addItem() {

`    `this.items.push(this.fb.control('', Validators.required));

`  `}

`  `removeItem(index: number) {

`    `this.items.removeAt(index);

`  `}

`  `onSubmit() {

`    `console.log(this.dynamicForm.value);

`  `}

}
**


**Dynamic Form Template**

\---------------------------

HTML

<form [formGroup]="dynamicForm" (ngSubmit)="onSubmit()">

`  `<div>

`    `<label for="name">Name</label>

`    `<input id="name" formControlName="name" />

`    `<div \*ngIf="dynamicForm.get('name')?.invalid && dynamicForm.get('name')?.touched">

`      `Name is required.

`    `</div>

`  `</div>

`  `<div formArrayName="items">

`    `<div \*ngFor="let item of items.controls; let i = index">

`      `<label for="item-{{ i }}">Item {{ i + 1 }}</label>

`      `<input [formControlName]="i" id="item-{{ i }}" />

`      `<button type="button" (click)="removeItem(i)">Remove</button>

`      `<div \*ngIf="item.invalid && item.touched">Item is required.</div>

`    `</div>

`  `</div>

`  `<button type="button" (click)="addItem()">Add Item</button>

`  `<button type="submit" [disabled]="dynamicForm.invalid">Submit</button>

</form>
**


**Dynamic Groups**

\------------------

TypeScript

addItemGroup() {

`  `const itemGroup = this.fb.group({

`    `name: ['', Validators.required],

`    `quantity: [1, [Validators.required, Validators.min(1)]],

`  `});

`  `this.items.push(itemGroup);

}

HTML

<div formArrayName="items">

`  `<div \*ngFor="let group of items.controls; let i = index" [formGroupName]="i">

`    `<label for="item-name-{{ i }}">Item Name</label>

`    `<input id="item-name-{{ i }}" formControlName="name" />

`    `<label for="item-quantity-{{ i }}">Quantity</label>

`    `<input id="item-quantity-{{ i }}" type="number" formControlName="quantity" />

`    `<button type="button" (click)="removeItem(i)">Remove</button>

`    `<div \*ngIf="group.invalid && group.touched">

`      `Name and Quantity are required.

`    `</div>

`  `</div>

</div>


# Services
**Creating a Service**

TypeScript

// data.service.ts

import { Injectable } from '@angular/core';

@Injectable({

`  `providedIn: 'root',

})

export class DataService {

`  `constructor() {}

`  `getData() {

`    `return ['Angular', 'React', 'Vue'];  // Example data

`  `}

}

**Injecting a Service into a Component**

TypeScript

// app.component.ts

import { Component, OnInit } from '@angular/core';

import { DataService } from './data.service';

@Component({

`  `selector: 'app-root',

`  `templateUrl: './app.component.html',

`  `styleUrls: ['./app.component.css']

})

export class AppComponent implements OnInit {

`  `public frameworks: string[] = [];

`  `constructor(private dataService: DataService) {}

`  `ngOnInit() {

`    `this.frameworks = this.dataService.getData();

`  `}

}
**


**Using HttpClient in a Service**

TypeScript

// data.service.ts

import { Injectable } from '@angular/core';

import { HttpClient } from '@angular/common/http';

import { Observable } from 'rxjs';

@Injectable({

`  `providedIn: 'root',

})

export class DataService {

`  `private apiUrl = 'https://jsonplaceholder.typicode.com/posts';

`  `constructor(private http: HttpClient) {}

`  `getPosts(): Observable<any[]> {

`    `return this.http.get<any[]>(this.apiUrl);

`  `}

}

**

**Component Using the Service with HttpClient**

TypeScript

// app.component.ts

import { Component, OnInit } from '@angular/core';

import { DataService } from './data.service';

@Component({

`  `selector: 'app-root',

`  `templateUrl: './app.component.html',

`  `styleUrls: ['./app.component.css']

})

export class AppComponent implements OnInit {

`  `posts: any[] = [];

`  `constructor(private dataService: DataService) {}

`  `ngOnInit() {

`    `this.dataService.getPosts().subscribe((data) => {

`      `this.posts = data;

`    `});

`  `}

}


# API Calling
**Setting up the HttpClientModule**

TypeScript

// app.module.ts

import { NgModule } from '@angular/core';

import { BrowserModule } from '@angular/platform-browser';

import { HttpClientModule } from '@angular/common/http';

@NgModule({

`  `imports: [BrowserModule, HttpClientModule],

})

export class AppModule {}

**Creating a Service for API Interaction**

TypeScript

// api.service.ts

import { Injectable } from '@angular/core';

import { HttpClient } from '@angular/common/http';

import { Observable } from 'rxjs';

@Injectable({

`  `providedIn: 'root'

})

export class ApiService {

`  `private apiUrl = 'https://jsonplaceholder.typicode.com/posts';

`  `constructor(private http: HttpClient) {}

`  `getPosts(): Observable<any[]> {

`    `return this.http.get<any[]>(this.apiUrl);

`  `}

`  `createPost(data: any): Observable<any> {

`    `return this.http.post<any>(this.apiUrl, data);

`  `}

`  `updatePost(id: number, data: any): Observable<any> {

`    `return this.http.put<any>(`${this.apiUrl}/${id}`, data);

`  `}

`  `deletePost(id: number): Observable<any> {

`    `return this.http.delete<any>(`${this.apiUrl}/${id}`);

`  `}

}

**Using the Service in a Component**

TypeScript

// app.component.ts

import { Component, OnInit } from '@angular/core';

import { ApiService } from './api.service';

@Component({

`  `selector: 'app-root',

`  `template: `

`    `<div>

`      `<h1>Posts</h1>

`      `<ul>

`        `<li \*ngFor="let post of posts">

`          `{{ post.title }}

`        `</li>

`      `</ul>

`    `</div>

`  ``,

})

export class AppComponent implements OnInit {

`  `posts: any[] = [];

`  `constructor(private apiService: ApiService) {}

`  `ngOnInit(): void {

`    `this.apiService.getPosts().subscribe(

`      `(data) => {

`        `this.posts = data;

`      `},

`      `(error) => {

`        `console.error('Error fetching posts:', error);

`      `}

`    `);

`  `}

}


# Common Components
**Creating a Common Component**

Bash

ng generate component button

**Component Structure**

TypeScript

// button.component.ts

import { Component, Input } from '@angular/core';

@Component({

`  `selector: 'app-button',

`  `templateUrl: './button.component.html',

`  `styleUrls: ['./button.component.css']

})

export class ButtonComponent {

`  `@Input() label: string = 'Click Me';

`  `@Input() color: string = 'primary';

}

**Using Inputs for Customization**

TypeScript

// button.component.ts

import { Component, Input } from '@angular/core';

@Component({

`  `selector: 'app-button',

`  `templateUrl: './button.component.html',

`  `styleUrls: ['./button.component.css']

})

export class ButtonComponent {

`  `@Input() label: string = 'Click Me';

`  `@Input() color: string = 'primary';

}

**Using ngContent for Content Projection**

HTML

<!-- button.component.html -->

<button [ngClass]="color" class="btn">

`  `<ng-content></ng-content>

</button>
**


**Using Output() to Emit Events**

TypeScript

// button.component.ts

import { Component, Output, EventEmitter } from '@angular/core';

@Component({

`  `selector: 'app-button',

`  `templateUrl: './button.component.html',

`  `styleUrls: ['./button.component.css']

})

export class ButtonComponent {

`  `@Input() label: string = 'Click Me';

`  `@Input() color: string = 'primary';

`  `@Output() clicked = new EventEmitter<void>();

`  `onClick() {

`    `this.clicked.emit();

`  `}

}


# Feature Flags
**Creating a Feature Flag Service**

TypeScript

// feature-flag.service.ts

import { Injectable } from '@angular/core';

@Injectable({

`  `providedIn: 'root',

})

export class FeatureFlagService {

`  `private flags: { [key: string]: boolean } = {};

`  `loadFlags(flags: { [key: string]: boolean }): void {

`    `this.flags = flags;

`  `}

`  `isFeatureEnabled(feature: string): boolean {

`    `return !!this.flags[feature];

`  `}

}

**Creating a Mock Feature Flag Configuration**

TypeScript

// feature-flags.ts

export const FEATURE\_FLAGS = {

`  `newFeature: true,

`  `experimentalFeature: false,

};
**


**Loading Feature Flags into the Service**

TypeScript

// app.module.ts

import { NgModule, APP\_INITIALIZER } from '@angular/core';

import { FeatureFlagService } from './services/feature-flag.service';

import { FEATURE\_FLAGS } from './feature-flags';

function initializeFeatureFlags(featureFlagService: FeatureFlagService): () => void {

`  `return () => featureFlagService.loadFlags(FEATURE\_FLAGS);

}

@NgModule({

`  `providers: [

`    `{

`      `provide: APP\_INITIALIZER,

`      `useFactory: initializeFeatureFlags,

`      `deps: [FeatureFlagService],

`      `multi: true,

`    `},

`  `],

})

export class AppModule {}

**Using Feature Flags in Components**

TypeScript

// app.component.ts

import { Component } from '@angular/core';

import { FeatureFlagService } from './services/feature-flag.service';

@Component({

`  `selector: 'app-root',

`  `template: `

`    `<div \*ngIf="isNewFeatureEnabled">New Feature is enabled!</div>

`    `<div \*ngIf="!isNewFeatureEnabled">New Feature is disabled.</div>

`  ``,

})

export class AppComponent {

`  `isNewFeatureEnabled: boolean;

`  `constructor(private featureFlagService: FeatureFlagService) {

`    `this.isNewFeatureEnabled = this.featureFlagService.isFeatureEnabled('newFeature');

`  `}

} 
