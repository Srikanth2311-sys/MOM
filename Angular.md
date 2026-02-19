### 🧩 What  
**Angular**: JS frontend framework  
- Collection of pkgs and rules  
- Collection of tools [CLI, debugging tools, IDE, plugins]

---

### ❓ Why  
It helps for complex projects  
- Declarative code focuses only on describing what should change in the UI, rather than how — unlike imperative code which requires step-by-step instructions  
- Separation of concerns via components  
- OOPS concepts and principle [DI/classes]  
- Use TypeScript  

---

### 🔄 Angular Evolution  
- Stable framework with strong **backward compatibility**  
- **Angular 14 & 15 (2022)**: Introduced **standalone components**  
- **Angular 16**: Introduced **signals** for reactive state management  

---

### 🚀 Creating a New Angular Project  
- You **cannot** create plain `.html` and `.js` files manually — Angular uses its own structure  
- Install Angular CLI globally:
  ```bash
  npm install -g @angular/cli
  ```
- Create a new project:
  ```bash
  ng new first-app
  ```

---

### 🛠️ Utility Libraries  
**Lodash**: Data Manipulation  
- Utility functions for arrays, objects, and more  

**Moment.js / Day.js**:  
- Date/time formatting and manipulation  

---
* **Angular Essentials** → Components handle user events and render/update the UI
* **tsconfig.json** → Defines TypeScript compiler rules and TypeScript-to-JavaScript conversion
* **angular.json** → Controls how Angular CLI builds, serves, tests, and deploys the app
* **App bootstrap flow** → `index.html` → `main.ts` → bootstraps `AppComponent`
* **Component decorator** → Marks a class as a component and links HTML, CSS, and logic
* **PIE_BCD_TSS mapping** → `Providers, Imports, Exports, Bootstrap, Declarations` → `@NgModule` | `Template, Styles, Selector` → `@Component`
* **App types** → Module-based apps use NgModules; standalone apps work without modules
* **Data binding** → `{{ }}` for interpolation, `[property]` for property binding
* **Getter usage** → `get userImagePath()` is accessed directly in templates
* **Event binding** → User actions handled using `(click)="onSelectUser()"`
* **zone.js** → Triggers global change detection on async events (clicks, timers)
* **Signals** → Reactive state management; updated via `set()` and read as functions
* **Signals vs zone.js** → Signals update only affected components, not the whole app
* **Computed signal** → `computed()` creates derived, cached values that update only when dependencies change
* **@Input vs input()** → `@Input()` = classic Parent → Child | `input()` = reactive signal-based Parent → Child
* **computed vs getter** → `computed()` = reactive & cached | `getter` = recalculated on every access
* **@Output()** → Allows child to emit events/data to the parent
* **Output binding example** → `(userSelected)="onSelectUser($event)"` listens in parent
* **@Output declaration** → `@Output() userSelected = new EventEmitter<string>();` or `userSelected = output<string>();`
* **Emit event** → `this.userSelected.emit(this.id);`
* **Input example** → `@Input() name!: string;`




Micro Frontend [MFE] with module federation in webpack 5 
----------------------------------------------
### **Monorepo**

One repo with multiple Angular apps (Host 4200 + Remote 4300) sharing workspace and loading MFEs via Module Federation.

### **Micro Frontend (MFE)**

Architecture where independent Angular apps expose features and are dynamically loaded by a host at runtime.

### **Multi-repo**

Host and MFE live in separate repos (Host 4200, Remote 4300) but connect using Webpack Module Federation.

---

### **Create Workspace**

`ng new mono-workspace --create-application=false` → creates empty Angular workspace for multiple apps.

### **Generate Apps**

`ng g application host-app` + `ng g application mfe-app` → creates Host and MFE apps inside workspace.

### **Serve Apps**

`ng s host-app --port 4200` + `ng s mfe-app --port 4300` → run Host and Remote apps locally.

---

### **Add Module Federation (Recommended)**

`ng add @angular-architects/module-federation --project host-app` and same for mfe → auto-configures host + remote federation.

---

### **Optional Advanced Webpack**

`npm i -D webpack webpack-cli @angular-builders/custom-webpack @module-federation/enhanced` → enables custom webpack + enhanced federation.

---.

Folder Structure varies from version to version, it consists src folder with configuration files like tsconfig.json, angular.json
for newly version it creates public folder with fav.icon file, in older version its does not , there many other small chnages like .componet suffix . 
tsconfig.json: mainly used to convert typescript to JS using underlaying Angular cli.
angular.json: mainly used to build, server, test and deploy the application.
all the source code exsists in src folder => App bootstrap → index.html → main.ts → bootstraps AppComponent => loads app component
---
In App component we use decorator for class, property ,method ,parameter and Query 
decorator => tells what class function or property should represents 
Class decorator =>@Component,@Pipe,@Directive,@Injectable,@NgModule.
Property decorator => @Input @Output ,@HostBinding
Method Decorators => @HostListener, custom method decorators[lifecycle hooks aren't decorators].
Parameter Decorators=> @Inject, @Optional,@Self, @SkipSelf,@Host
Query Decorators=>@ViewChild,@ViewChildren, @ContentChild, @ContentChildren
@EnvironmentInjector, @Attribute(),@ViewContainerRef
-----
@Component({configuration object }) [make component to link html/css/logic]
Selector => it is identifier used in html file
standalone: true, Self-contained  without registering ngmodule
templateURL :refer to markup and styleurl => it refer to css file.
imports : imports child components
--

String interpolation => {{userSelected.name}} => userSelected =DUMMY_USERS[Math.floor(Math.random() * DUMMY_USERS.length)];
PropertyBinding =><img [src]="imagePath"> => get imagePath() { return `assets/users/${this.userSelected.avatar}`; }
event listener =>  <button (click)="onSelectUser()"> =>onSelectUser = () => console.log("clicked")
zone js listen to events check change detection completely, now we can use signal get subscribe on val change.
signal <span>{{ userSelected().name }}</span>  => userSelected =signal(DUMMY_USERS[randomUser]); =>set ,computed()
[C]@Input({required: true}) avatar!: string; => [P]=> <app-user [avatar]="users[2].avatar"></app-user>  [P]=>  users = DUMMY_USERS;
instead Input as signal import input from ngcore =>[C]avatar =input<String>('test');=> [P]<app-user [avatar]="users[2].avatar"></app-user>
