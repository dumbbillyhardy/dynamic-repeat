You can use **dynamic-repeat** exactly the same way you'd use **dom-repeat**,
    but with several differences. You can pass multiple templates into **dynamic-repeat**
    and, based on the precedence, the correct template will be chosen to render each item.
    The `items` array should be an array of objects containing the properties `prop` and `type`.
    If a template is found for `prop`, that is used. It then checks `type`, and finally checks
    for a default template. Mark templates with the `for` attribute.
