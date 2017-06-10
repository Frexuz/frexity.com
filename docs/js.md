# JavaScript guidelines

## Quotes

Always use single quotes.

```
# Bad
var text = "hello";

# Good
var text = 'hello';

# Good (works well with HTML)
var html = '<div class="box">A nice box</div>';
```

## Semi colons

Always use semi colons to end statements.

```
# Bad
var text = 'hello'
var world = 'world'

# Good
var text = 'hello';
var world = 'world';
```

## Hashes

Always use spaces inside curly brackets.

```
# Bad
{one: 'hello'}

# Good
{ one: 'hello' }
```

Always use spaces after colons.

```
# Bad
{ one:'hello' }

# Good
{ one: 'hello' }
```

Always use spaces after commas.

```
# Bad
{ one: 'hello',two: 'world' }

# Good
{ one: 'hello', two: 'world' }
```

## Functions

No spaces inside parantheses.

```
# Bad
function( one )

# Good
function(one)
```

Always use spaces after parantheses.

```
# Bad
function(one){...

# Good
function(one) {...
```

Always use spaces after commas.

```
# Bad
function(one,two)

# Good
function(one, two)
```

## Conditionals

Always use multiline conditionals

```
# Bad
if (true) return;

# Good
if (true) {
  return;
}
```

Always use newlines for else/elseif statements.

```
# Bad
if (true) {
  // ..
} else {
  // ..
}

# Good
if (true) {
  // ..
}
else {
  // ..
}
```

Always use space before parantheses.

```
# Bad
if(true) {
  // ..
}

# Good
if (true) {
  // ..
}
```

## Guards / returns

Always use guards for single conditional body of a function.

```
# Bad
function test() {
  if (true) {
    // do something
  }
}

# Good

function test() {
  if (!true) {
    return;
  }
  
  // do something
}
```

## Variables

Always use camelCasing for variable names.

```
# Bad
var helloworld = 'hello world';
var hello_world = 'hello world';
var HelloWorld = 'hello world';

# Good
var helloWorld = 'hello world';
```

Always use a single comma separated `var` to assign multiple variables.

```
# Bad
var hello = 'hello';
var world = 'world';
var test = 'test';

# Good
var hello = 'hello',
  world = 'world',
  test = 'test';
```

## Operations

Always use triple equals.

```
# Bad
if (myVar == true) {
    return;
  }

# Good
if (myVar === true) {
    return;
  }
```
