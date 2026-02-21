Angular Project – Quick Reference README

---
1. Project Structure

Folder structure may vary depending on Angular version.

Root Level Files

angular.json

tsconfig.json

package.json

src/

public/ (newer versions)


Version Differences

Newer Angular versions create a public/ folder that includes favicon.ico.

Older versions placed assets differently.

Minor naming updates such as .component suffix improvements and structural refinements.



---

2. Important Configuration Files

tsconfig.json

Used to configure TypeScript compilation.

Converts TypeScript to JavaScript

Managed internally by Angular CLI

Controls strict mode, target version, module system


angular.json

Controls Angular CLI behavior.

Used for:

Build

Serve

Test

Deploy

Assets configuration

Environment configuration



---

3. Application Bootstrap Flow

All source code exists inside the src/ folder.

Application startup sequence:

index.html
   ↓
main.ts
   ↓
bootstrapApplication() or bootstrapModule()
   ↓
AppComponent loads

Flow Explanation:

1. index.html is the entry HTML file.


2. main.ts bootstraps the Angular application.


3. AppComponent becomes the root component.


4. Angular renders the component tree.




---

4. Angular Decorators

Decorators define metadata and behavior for classes and members.

What is a Decorator?

A decorator tells Angular what a class, method, property, or parameter represents.


---

4.1 Class Decorators

Used on classes.

@Component

@Directive

@Pipe

@Injectable

@NgModule



---

4.2 Property Decorators

Used on class properties.

@Input

@Output

@HostBinding



---

4.3 Method Decorators

Used on methods.

@HostListener


Note: Lifecycle hooks are not decorators. They are interface methods.


---

4.4 Parameter Decorators

Used in constructor parameters.

@Inject

@Optional

@Self

@SkipSelf

@Host

@Attribute



---

4.5 Query Decorators

Used to access template elements.

@ViewChild

@ViewChildren

@ContentChild

@ContentChildren



---

4.6 Other Core APIs

EnvironmentInjector

ViewContainerRef



---

5. Component Configuration

Example:

@Component({
  selector: 'app-user',
  standalone: true,
  templateUrl: './user.component.html',
  styleUrls: ['./user.component.css'],
  imports: []
})

Configuration Properties

selector
Custom HTML tag used in templates.

standalone: true
Makes component self-contained without NgModule.

templateUrl
Refers to HTML file.

styleUrls
Refers to CSS file.

imports
Imports child components or directives.



---

6. Data Binding

Angular supports multiple binding types.


---

6.1 String Interpolation

<span>{{ userSelected.name }}</span>

userSelected = DUMMY_USERS[Math.floor(Math.random() * DUMMY_USERS.length)];

Used to display data in template.


---

6.2 Property Binding

<img [src]="imagePath">

get imagePath() {
  return `assets/users/${this.userSelected.avatar}`;
}

Binds DOM property to component property.


---

6.3 Event Binding

<button (click)="onSelectUser()">

onSelectUser() {
  console.log('clicked');
}

Triggers method when event occurs.


---

7. Change Detection

Earlier:

Angular uses Zone.js

Listens to async events

Runs full change detection cycle


Now:

Signals introduced

More reactive and fine-grained updates

No need to rely completely on Zone.js



---

8. Angular Signals

Signals provide reactive state management.

Basic Example

import { signal, computed } from '@angular/core';

userSelected = signal(DUMMY_USERS[randomUser]);

userSelected.set(newValue);

const username = computed(() => userSelected().name);

Template usage:

<span>{{ userSelected().name }}</span>


---

9. Input Binding

Traditional Input

Child component:

@Input({ required: true }) avatar!: string;

Parent component:

<app-user [avatar]="users[2].avatar"></app-user>


---

Input as Signal

Child component:

import { input } from '@angular/core';

avatar = input<string>('default');

Parent:

<app-user [avatar]="users[2].avatar"></app-user>


parent
<app-user (selected)="handleSelected($event)"></app-user> => 
handleSelected(userId: string) {
  console.log('Selected (classic output):', userId);
}
child 
<button  (click)="onSelectUser()">
  @Output() userSelected = new EventEmitter<string>();
selectedUserId = output<string>({ alias: 'selected', description: 'Emits when user is selected' });
 onSelectUser(){
   this.userSelected.emit(this.id);
   this.selectedUserId.emit(this.id);
  }
---

10. Angular Lifecycle Hooks

Lifecycle hooks define stages of a component’s life.

Order of execution:

1. constructor


2. ngOnChanges


3. ngOnInit


4. ngDoCheck


5. ngAfterContentInit


6. ngAfterContentChecked


7. ngAfterViewInit


8. ngAfterViewChecked


9. ngOnDestroy



