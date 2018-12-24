---
description: >-
  Angular templates are dynamic. When Angular renders them, it transforms the
  DOM according to the instructions given by directives. A directive is a class
  with a @Directive() decorator.
---

# Directives

## Directives overview

There are three kinds of directives in Angular:

1. Components—directives with a template.
2. Structural directives—change the DOM layout by adding and removing DOM elements.
3. Attribute directives—change the appearance or behavior of an element, component, or another directive.

## Attribute directive

 An attribute directive minimally requires building a controller class annotated with `@`[`Directive`](https://angular.io/api/core/Directive), which specifies the selector that identifies the attribute.

```bash
ng generate directive highlight
```

{% code-tabs %}
{% code-tabs-item title="app/app.component.ts" %}
```typescript
import { Component } from '@angular/core';

@Component({
  selector: 'app-root',
  templateUrl: './app.component.html'
})
export class AppComponent {
  color: string;
}
```
{% endcode-tabs-item %}

{% code-tabs-item title="app/app.component.html" %}
```markup
<h1>My First Attribute Directive</h1>

<h4>Pick a highlight color</h4>
<div>
  <input type="radio" name="colors" (click)="color='lightgreen'">Green
  <input type="radio" name="colors" (click)="color='yellow'">Yellow
  <input type="radio" name="colors" (click)="color='cyan'">Cyan
</div>
<p [appHighlight]="color">Highlight me!</p>

<p [appHighlight]="color" defaultColor="violet">
  Highlight me too!
</p>
```
{% endcode-tabs-item %}

{% code-tabs-item title="app/highlight.directive.ts" %}
```typescript
/* tslint:disable:member-ordering */
import { Directive, ElementRef, HostListener, Input } from '@angular/core';

@Directive({
  selector: '[appHighlight]'
})
export class HighlightDirective {

  constructor(private el: ElementRef) { }

  @Input() defaultColor: string;

  @Input('appHighlight') highlightColor: string;

  @HostListener('mouseenter') onMouseEnter() {
    this.highlight(this.highlightColor || this.defaultColor || 'red');
  }

  @HostListener('mouseleave') onMouseLeave() {
    this.highlight(null);
  }

  private highlight(color: string) {
    this.el.nativeElement.style.backgroundColor = color;
  }
}
```
{% endcode-tabs-item %}

{% code-tabs-item title="app/app.module.ts" %}
```typescript
import { NgModule } from '@angular/core';
import { BrowserModule } from '@angular/platform-browser';

import { AppComponent } from './app.component';
import { HighlightDirective } from './highlight.directive';

@NgModule({
  imports: [ BrowserModule ],
  declarations: [
    AppComponent,
    HighlightDirective
  ],
  bootstrap: [ AppComponent ]
})
export class AppModule { }
```
{% endcode-tabs-item %}
{% endcode-tabs %}

 It's the brackets \(`[]`\) that make it an attribute selector. 

### Built-in _attribute_ directives 

* [`NgClass`](https://angular.io/guide/template-syntax#ngClass) - add and remove a set of CSS classes
* [`NgStyle`](https://angular.io/guide/template-syntax#ngStyle) - add and remove a set of HTML styles
* [`NgModel`](https://angular.io/guide/template-syntax#ngModel) - two-way data binding to an HTML form element \(FormsModule is required to use ngModel\)

##  Structural Directives

 Structural directives are responsible for HTML layout. They shape or reshape the DOM's _structure_, typically by adding, removing, or manipulating elements.  Structural directives are easy to recognize. An asterisk \(\*\) precedes the directive attribute name.



### Built-in _structural_ directives 

* [`NgIf`](https://angular.io/guide/template-syntax#ngIf) - conditionally add or remove an element from the DOM
* [`NgSwitch`](https://angular.io/guide/template-syntax#ngSwitch) - a set of directives that switch among alternative views
* [`NgForOf`](https://angular.io/guide/template-syntax#ngFor) - repeat a template for each item in a list

```typescript
<div *ngIf="hero" class="name">{{hero.name}}</div>

<ul>
  <li *ngFor="let hero of heroes">{{hero.name}}</li>
</ul>

<div [ngSwitch]="hero?.emotion">
  <app-happy-hero    *ngSwitchCase="'happy'"    [hero]="hero"></app-happy-hero>
  <app-sad-hero      *ngSwitchCase="'sad'"      [hero]="hero"></app-sad-hero>
  <app-confused-hero *ngSwitchCase="'app-confused'" [hero]="hero"></app-confused-hero>
  <app-unknown-hero  *ngSwitchDefault           [hero]="hero"></app-unknown-hero>
</div>
```

