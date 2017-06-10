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

## Github

Always name branches with format `issX-some-name`. X is the issue number.

```
# Bad
git branch newdesign

# Good
git branch iss43-new-design
```
