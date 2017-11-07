[![Published on
webcomponents.org](https://img.shields.io/badge/webcomponents.org-published-blue.svg)](https://www.webcomponents.org/element/billy-hardy/dynamic-repeat)

You can use **dynamic-repeat** exactly the same way you'd use **dom-repeat**,
    but with several differences. You can pass multiple templates into **dynamic-repeat**
    and, based on the precedence, the correct template will be chosen to render each item.
    The `items` array should be an array of objects containing the properties `prop` and `type`.
    If a template is found for `prop`, that is used. It then checks `type`, and finally checks
    for a default template. Mark templates with the `for` attribute.

<!---
```
<custom-element-demo>
<template>
<script src="../webcomponentsjs/webcomponents-lite.js"></script>
<link rel="import" href="dynamic-repeat.html">
<next-code-block></next-code-block>
</template>
</custom-element-demo>
```
-->
```html
<script>
window.onload = () => {
    dynamicRepeat.items = [{
value: "test@test.com",
       prop: "email",
       type: "string",
    }, {
value: "Female",
           prop: "gender",
           type: "string",
    }, {
value: "!QAZ2wsx#EDC4rfv",
           prop: "password",
           type: "encrypted",
    }, {
value: "29",
           prop: "age",
           type: "number",
    }];
};
</script>

<dynamic-repeat id="dynamicRepeat">
    <template for="email">mailto: [[item.value]]</template>
    <template for="string">"[[item.value]]"</template>
    <template for="encrypted">****</template>
    <template>[[item.value]]</template>
</dynamic-repeat>
