# Widgets

## Variables

Every widget must have variables to toggle their `:visible` or `:reveal` attributes.
These variables should be named as `<widget name>-<colletion>-visible` or `<widget name>-<collection>-reveal`

*Example*
```yuck
(defvar volume-rancid-visible true)
(defvar volume-rancid-reveal true)
```

## Interaction

No commands as raw strings should be written directly in a widget. Only call scripts and pass arguments as yuck strings.

Any commands run by one of the following attributes, or as part of a `defpoll` or `deflisten` variable, should be extracted to a script.

`:onhover`

`:onhoverlost`

`:onclick`

`:onmiddleclick`

`:onrightclick`

`:onchange`

`:onaccept`

`:onchecked`

`:onunchecked`

`:onscroll`

`:ondropped`
