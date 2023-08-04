---
description: Const and Let inside of scopes and reassigning them
---

# Scopes & Reassigning

## Constant scope

The constant `variable` is defined outside the if-statement but can still be accessed inside of it.

<pre class="language-js" data-title="index.js" data-line-numbers><code class="lang-js">const variable = 'test';

<strong>if (true) {
</strong><strong>  console.log(variable);
</strong><strong>} 
</strong></code></pre>

{% code title="terminal" %}
```bash
$ node .
"test"
```
{% endcode %}

## Reassign in different scope

In here, `variable` is defined at the top of your code, and is reassigned a different value inside an if-statement, the new value is still accessable outside (and bellow) the if-statement.

### Truely if-statement

<pre class="language-js" data-title="index.js" data-line-numbers><code class="lang-js">let variable = 'test';

<strong>if (true) {
</strong><strong>  variable = 'maybe';
</strong><strong>}
</strong>
console.log(variable);
</code></pre>

{% code title="terminal" %}
```bash
$ node .
"maybe"
```
{% endcode %}

### Falsely if-statement

<pre class="language-js" data-title="index.js" data-line-numbers><code class="lang-js">let variable = 'test';

<strong>if (false) {
</strong><strong>  variable = 'maybe';
</strong><strong>}
</strong>
console.log(variable);
</code></pre>

{% code title="terminal" %}
```bash
$ node .
"test"
```
{% endcode %}

## Constant in wrong scope

The constant `variable` is defined in a lower scope than the `console.log` and is therefor not accessable and will throw a run time error.

{% code title="index.js" lineNumbers="true" %}
```js
if (false) {
  const variable = 'maybe';
}

console.log(variable);
```
{% endcode %}

<pre class="language-bash" data-title="terminal"><code class="lang-bash">$ node .
<strong>Uncaught ReferenceError: variable is not defined
</strong></code></pre>

## Reassigning

Giving a variable a new value is not possible with `const`, only with `let`. Even if this sounds like an advantage for the `let`-keyword, you shouldn't use it if you don't need to as it uses more ram.

{% code title="const reassigning" lineNumbers="true" %}
```javascript
const username = "Luna";
username = "mwlica"; // ❌
```
{% endcode %}

{% code title="let reassigning" lineNumbers="true" %}
```javascript
let username = "Luna";
username = "mwlica"; // ✅
```
{% endcode %}

{% code title="let without reassinging" lineNumbers="true" %}
```javascript
let username = "Luna"; // ❌
```
{% endcode %}

