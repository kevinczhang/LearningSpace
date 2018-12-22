# Data binding

In fact, once you start data binding, you are no longer working with HTML attributes. You aren't setting attributes. You are setting the properties of DOM elements, components, and directives.

## HTML attribute vs. DOM property

The distinction between an HTML attribute and a DOM property is crucial to understanding how Angular binding works.

**Attributes are defined by HTML. Properties are defined by the DOM \(Document Object Model\).**

A few HTML attributes have 1:1 mapping to properties. id is one example.

Some HTML attributes don't have corresponding properties. colspan is one example.

Some DOM properties don't have corresponding attributes. textContent is one example.

Many HTML attributes appear to map to properties ... but not in the way you might think!

That last category is confusing until you grasp this general rule:

**Attributes initialize DOM properties and then they are done. Property values can change; attribute values can't.**

## Binding targets ****

 The target of a data binding is something in the DOM.

### Property <a id="property"></a>

Element property  
Component property  
Directive property

You should omit the brackets when all of the following are true:

* The target property accepts a string value.
* The string is a fixed value that you can bake into the template.
* This initial value never changes.

```markup
<img [src]="heroImageUrl">
<app-hero-detail [hero]="currentHero"></app-hero-detail>
<div [ngClass]="{'special': isSpecial}"></div>

<app-hero-detail prefix="You are my" [hero]="currentHero"></app-hero-detail>
```



