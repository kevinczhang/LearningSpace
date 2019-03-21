# Complex animation sequences

So far, we've learned simple animations of single HTML elements. Angular also lets you animate coordinated sequences, such as an entire grid or list of elements as they enter and leave a page. You can choose to run multiple animations in parallel, or run discrete animations sequentially, one following another.

### Animate multiple elements using query\(\) and stagger\(\) functions <a id="animate-multiple-elements-using-query-and-stagger-functions"></a>

 The [`query()`](https://angular.io/api/animations/browser/testing/MockAnimationDriver#query) function allows you to find inner elements within the element that is being animated.

 The [`stagger`](https://angular.io/api/animations/stagger)`()` function allows you to define a timing gap between each queried item that is animated and thus animates elements with a delay between them.

### Parallel animation using group\(\) function <a id="parallel-animation-using-group-function"></a>

group\(\) can configure animations that happen in parallel.  The [`group()`](https://angular.io/api/forms/FormBuilder#group) function is used to group animation _steps_, rather than animated elements.

```typescript
animations: [
  trigger('flyInOut', [
    state('in', style({
      width: 120,
      transform: 'translateX(0)', opacity: 1
    })),
    transition('void => *', [
      style({ width: 10, transform: 'translateX(50px)', opacity: 0 }),
      group([
        animate('0.3s 0.1s ease', style({
          transform: 'translateX(0)',
          width: 120
        })),
        animate('0.3s ease', style({
          opacity: 1
        }))
      ])
    ]),
    transition('* => void', [
      group([
        animate('0.3s ease', style({
          transform: 'translateX(50px)',
          width: 10
        })),
        animate('0.3s 0.2s ease', style({
          opacity: 0
        }))
      ])
    ])
  ])
]
```

### Sequential animation using sequence\(\) function <a id="sequential-vs-parallel-animations"></a>

A second function called [`sequence`](https://angular.io/api/animations/sequence)`()` lets you run those same animations one after the other. Within [`sequence`](https://angular.io/api/animations/sequence)`()`, the animation steps consist of either [`style`](https://angular.io/api/animations/style)`()` or [`animate()`](https://angular.io/api/animations/browser/testing/MockAnimationDriver#animate) function calls.

* Use [`style`](https://angular.io/api/animations/style)`()` to apply the provided styling data immediately.
* Use [`animate()`](https://angular.io/api/animations/browser/testing/MockAnimationDriver#animate) to apply styling data over a given time interval.



