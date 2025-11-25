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
🌟 Angular Essentials –
✅ tsconfig.json

Controls how TypeScript compiles your Angular code.

✅ angular.json

Controls how Angular CLI builds, serves, and configures your project.

✅ bootstrapApplication(AppComponent, appConfig)

Starts the standalone Angular app and loads global providers/config.

✅ Browser Load Flow

Browser loads index.html → main.ts → bootstrapApplication → AppComponent.

✅ @Component Decorator (PIE_BCD_TSS)

Component = Selector + Template + Styles + Class + Inputs + Outputs + Bindings.



Micro Frontend [MFE] with module federation in webpack 5 
----------------------------------------------
types :  Mono repo [shell app [header code as MFE hosted at 4300]=>consume header code   => host app hosted at 4200] => Micro frontend [sharing code from one server to another server with same repo]
		mutli repo [we can have two or more repo [shell app with header code at MFE 4300 repo] [host application at 4200 with repo2 ]]
		
ng new mono-workspace --create-application=false
ng g application host-app --routing --style=scss
ng g application mfe-app --routing --style=scss
ng s host-app -o and ng s mfe-app -o 
npm i webpack webpack-cli --save-dev
add MFE ng add @angular-architects/module-federation --project host-app --port 4200 X
npm install --save-dev @angular-builders/custom-webpack @module-federation/enhanced

