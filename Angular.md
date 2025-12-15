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
- **Angular Essentials** → Components handle user events and render/update UI
- **tsconfig.json** → Defines TypeScript compiler rules and TypeScript-to-JavaScript conversion
- **angular.json** → Controls how Angular CLI builds, serves, tests, and deploys the app
- **App bootstrap flow** → `index.html` loads `main.ts`, which bootstraps the app and loads `AppComponent`
- **Component decorator** → Identifies a class as a component and links it to HTML, CSS, and data
- **PIE_BCD_TSS mapping** → Providers, Imports, Exports, Bootstrap, Declarations belong to `@NgModule`, while Component, Template, Styles, Selector belong to `@Component`
- **App types** → Module-based apps use NgModules, while standalone apps work without modules
- **Data binding** → Interpolation `{{ }}` accesses public properties, and property binding uses `[src]`
- **Getter usage** → `get userImagePath()` can be accessed directly in the template
- **Event binding** → User events are handled using `(click)="onSelectUser()"`
- **zone.js** → Triggers change detection by notifying Angular of user events and timers
- **Signals** → Manage state and change detection, updated via `set()` and accessed as functions in templates
- **Signals vs zone.js** → Signals update only affected components instead of the entire app
- **Computed signal** → `imagePath = computed(() => 'assets/users/' + this.selectedUser().avatar)` recomputes only when the signal changes




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


