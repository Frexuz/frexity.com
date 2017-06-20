# Ruby guidelines

## List of stuff you should know as your second language :D

- Array methods: https://ruby-doc.org/core-2.2.0/Array.html
- Hash methods: https://ruby-doc.org/core-2.4.0/Hash.html

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

## Method names

Don't use predicate words like `get`, `set`, and `is`

```
# Bad
def get_user(user_id)
  # ..
end

def is_admin(user)
  # ..
end

# Good
def user_by_id(id)
  # ..
end

# Good
def admin?(user)
  # ..
end
```

Name it `_count` for it is a number.

```
# Bad
@required_photos = @property.total_rooms

# Good
@required_photos_count = @property.rooms_count`
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

## Guards / returns

Always use a **guard** and return early, rather than using returning code paths inside conditionals.

```
# Bad
def filter(query)
  if query
    process_query(query)
  else
    query = []
  end
end

# Good
def filter(query)
  # Guard
  return [] unless query
  
  # Normal code path
  process_query(query)
end
```

## PORO - Plain Old Ruby Classes

Always use for **Services**, **Queries** and similar helper classes.

Example:
```
class FilterService

  def initialize(query)
    @query = query
  end

  def filter
    # .. do stuff with @query
  end

end

Usage:

@filter_service = FilterService.new(params[:q]) <- reusable object
@filter_service.filter # execute the filter
@filter_service.query # check the current query value

or just

@filter_results = FilterService.new(params[:q]).filter
```
