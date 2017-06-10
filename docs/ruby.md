# Ruby guidelines

## Using keyword arguments

Using named arguments when there is more than one argument

```
# Bad
def hello_message(first_name, last_name)
  "Hello, #{first_name} #{last_name}"
end

# Good
def hello(first_name:, last_name:)
  "Hello, #{first_name} #{last_name}"
end

# Good
def hello(name)
  "Hello, #{name}"
end
```

## Spacing

Always use spaces before/after closing ruby tags.

```
# Bad
<%=user.name%>

# Good
<% user.name %>
<%= user.name %>
```

Always use spaces after hash keys.

```
# Bad
<%= content_tag(:div, 'hello', class:'box' %>

# Good
<%= content_tag(:div, 'hello', class: 'box' %>
```

Always use spaces inside hashes, and after colons and commas.

```
# Bad
{first_name:'Kristian',last_name:'Gerardsson'}

# Good
{ first_name: 'Kristian', last_name: 'Gerardsson' }
```

No spaces inside arrays, but after commas.

```
# Bad
[ 'Kristian','Gerardsson' ]

# Good
['Kristian', 'Gerardsson']
```

Use spaces around operations

```
# Bad
(order.price*order.units)*1.25

# Good
(order.price * order.units) * 1.25
```
