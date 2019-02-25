# Directives

## @import

 Can import css file like import "foo.css" or sass file like import "foo".

```css
// Nested Import
#main {
    @import "colors"
}
```

## @extend

```css
// Inherits Styles from another
.button {
    color: Black;
}

.submit-button {
    @extend .button;
    @extend a:hover;
    border: 1px Black solid;
}
```

## @mixin

```css
@mixin font-large {
    font: {
        size: 14px;
        family: san-serif;
        weight: bold;
    }
}

// Use it with @include
#form {
    @include font-large;
}

// With parameter
@mixin rounded-corners-all($size: 5px) {
    border-radius: $size;
    -webkit- border-radius: $size;
     -moz- border-radius: $size;
}

// Use it with @include
#form {
    @include rounded-corners-all(15px) ; // 15px is optional
}
```

## @function

```css
// Value calculations
$app-width: 900px;
@function column-width($cols) {
    @return ( $app-width  / $cols) - ( $cols * 5px);
}

.col2 {
    width: column-width(2);
}
```

