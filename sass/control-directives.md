# Control Directives

## @if

```css
h1 {
    @if $size > 14px {
        color: Blue;
    }
    @else if $size < 14px {
        color: Red;    
    }
    @else {
        color: Green;
    }
}
```

## @for

```css
$page-width: 1000px;
@for $col from 1 through 4 {
    .col#{$col}{
        width: $page-width / $col;
    }
}
```

## @each

```css
@each $item in black, white, red, yellow {
    .#{$item} {
        background-color: #{item};
    }
}
```

## @while

```css
$i: 1;
@while $i < 5 {
    h#{$i} {
        font-size: $i * 4px;
        $i: $i + 1;
    }
}
```

