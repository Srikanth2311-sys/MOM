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
Angular Esstentials:
tsconfig.json file is the central configuration file that tells the TypeScript compiler how to compile your Angular application's code, where to find the files, and what features to include or exclude.
angular.json file is the central configuration file for an Angular CLI-based project, defining the workspace, project, and architect configurations, as well as the schematics and CLI settings. It's a crucial file for managing the build, serve, test, and other tasks in your Angular application.

bootstrapApplication(App, appConfig)=> added providers  and use comp decorator to load app component 
index.html => <app-root></app-root>(browser does not understand now main.ts comes in pic with app config)
Comp-decorator =>PIE_BC_DE_TSS

