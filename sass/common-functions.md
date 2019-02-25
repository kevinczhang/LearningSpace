# Common functions

```css
$quoted: quote($sometext); // adding ""
$unquoted: unquote($sometext); // remove ""

$value: if(true, $color1, $color2);

$rnd: round(3.14);
$top: ceil(3.14);
$bot: floor(3.14);
$per: percentage(.14);

String Interpolation:

$root: "/images";

#form {
    background: url("#{root}background.jpg");
}

$name: "my-class";

.#{$name} {
    color: Blue;
}
```

