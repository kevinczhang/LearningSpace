# Nesting

## Hierarchies imply the cascading:

```css
nav {
    font-size: 14px;
    ul {
        list-style-type:none;
        li {
            float: left;
        }
    }
}

// results:
nav {
    font-size: 14px;
}
nav ul {
    list-style-type:none;
}
nav ul li {
    float: left;
}
```

## & refer to parent:

```css
a {
    &:hover {
        text-decoration: underline;
    }
}
```

## Nested Properties

```css
.button {
    font: {
        family: Verdana, Helvetica, sans-serif;
        size: 14px;
    }
}
// Results:
.button {
    font-family: Verdana, Helvetica, sans-serif;
    font-size: 14px;
}
```

