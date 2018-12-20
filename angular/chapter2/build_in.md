## Built-in attribute directives

The target of a data binding is something in the DOM. 

{% method %}
## Property

Element property<br>
Component property<br>
Directive property

You should omit the brackets when all of the following are true:

* The target property accepts a string value.
* The string is a fixed value that you can bake into the template.
* This initial value never changes.

{% sample lang="js" %}
Here some examples

```html
<img [src]="heroImageUrl">
<app-hero-detail [hero]="currentHero"></app-hero-detail>
<div [ngClass]="{'special': isSpecial}"></div>

<app-hero-detail prefix="You are my" [hero]="currentHero"></app-hero-detail>
```

{% common %}

{% endmethod %}