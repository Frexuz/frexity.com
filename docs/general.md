# General guidelines

## Running development server

Always run **Guard** in a terminal.

```
# Bad
Not using Guard

# Good
bundle exec guard
```

## File names

Always use underscore in filenames.

```
# Bad
app-bar.js

# Good
app_bar.js
```

Always use explicit file extensions/pre-processors.

```
# Bad
app_bar.scss

# Good
app_bar.css.scss
```

## Variable names

Always use descriptive names, in any language.

```
# Bad
q = params[:q]

# Good
search_query = params[:q]

# Bad
val = $input.val();

# Good
inputValue = $input.val();

# Bad
@users.map_with_index do |user, i|

# Good
@users.map_with_index do |user, index|

# Bad
@users.map { |u| ...

# Good 
@users.map { |user| ...
```

Exceptions, these are good:

```
Rails forms
form_for @user do |f|

Rails migrations
create_table :users do |t|

JavaScript loops
for (var i = 0; ...
```

## Github

Always name branches with format `issX-some-name`. X is the issue number.

```
# Bad
git branch newdesign

# Good
git branch iss43-new-design
```
