# CSS / SCSS guidelines

## Naming

Always use hyphen casing for selector names.

```
# Bad
.my_box {}
.myBox {}

# Good
.my-box {}
```

## IDs

Don't use IDs for styling.

```
# Bad
#container {}

# Good
.app-container {}
```

## Selectors

Always use spaces before curly brackets.

```
# Bad
.box{
}

# Good
.box {
}
```

Always use new lines before nested selectors.

```
# Bad
.box {
  color: red;
  .icon {
    //...
  }
}

# Good
.box {
  color: red;
  
  .icon {
    //...
  }
}
```

Always use semicolons for the last statement.

```
# Bad
.box {
  background: #fff;
  color: red
}

# Good
.box {
  background: #fff;
  color: red;
}
```

Always put each selector on its own line.

```
# Bad
.box, .block {
  // ..
}

# Good
.box,
.block {
  // ..
}

```

## Values

Use shorthands.

```
# Bad
margin: 10px 20px 10px 20px;

# Good
margin: 10px 20px;
```

```
# Bad
margin: 0 20px 10px 20px;

# Good
margin: 0 20px 10px;
```

Use space after colon.

```
# Bad
margin:0;

# Good
margin: 0;
```

Ommit units for zero values.

```
# Bad
margin: 0px;

# Good
margin: 0;
```

Always use short color values

```
# Bad
color: #ffffff;

# Good
margin: #fff;
```

Always use lower case hex characters

```
# Bad
color: #FFF;

# Good
margin: #fff;
```

## Order

Always correct order for nested selectors.
1. Pseudo-elements
2. "State"-classes
3. Nested classes or html tags

```
# Bad
.box {
  color: red;
  
  &.--active {
  }
  
  .icon {
  }
  
  &::after {
  }
}

# Good

.box {
  color: red;
  
  &::after {
  }
  
  &.--active {
  }
  
  .icon {
  }
}
```

## SCSS

(Almost) always use variables.

```
# Bad
color: #f00;

# Good
color: palette("red");
```

```
# Bad
font-size: 24px;

# Good
font-size: $h3-font-size;
```
