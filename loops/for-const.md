---
description: for const of loops
---

# for-const

This JavaScript build in feature allows you to loop over arrays, maps, sets and other lists.

## Example

{% code title="index.js" lineNumbers="true" fullWidth="false" %}
```javascript
const xs = [1, 2, 3]

for (const x of xs) {
    console.log(x);
}
```
{% endcode %}

{% code title="terminal" %}
```bash
$ node .
1
2
3
```
{% endcode %}

## return statement

The `return;` statement completely stops code execution:

* current item inside the loop
* the loop itself
* code beneath the loop

<pre class="language-javascript" data-title="index.js" data-line-numbers><code class="lang-javascript">const numberList = [1, 2, 3];

for (const number of numberList) {
  console.log("start: ", number);
  
<strong>  if (number === 2) return;
</strong>  
  console.log("end: ", number);
  console.log("\n"); // creates a empty line
}

console.log(numberList);
</code></pre>

{% code title="terminal" %}
```bash
$ node .
start: 1
end: 1

start: 2
```
{% endcode %}

## break statement

The `break;` statement completely stops code execution:

* current item inside the loop
* the loop itself

<pre class="language-javascript" data-title="index.js" data-line-numbers><code class="lang-javascript">const numberList = [1, 2, 3];

for (const number of numberList) {
  console.log("start: ", number);
  
<strong>  if (number === 2) break;
</strong>  
  console.log("end: ", number);
  console.log("\n"); // creates a empty line
}

console.log("all items: ", numberList);
</code></pre>

<pre class="language-bash" data-title="terminal"><code class="lang-bash">$ node .
start: 1
end: 1

start: 2

<strong>all items: [1, 2, 3]
</strong></code></pre>



## continue statement

The `break;` statement completely stops code execution:

* inside the loop

<pre class="language-javascript" data-title="index.js" data-line-numbers><code class="lang-javascript">const numberList = [1, 2, 3];

for (const number of numberList) {
  console.log("start: ", number);
  
<strong>  if (number === 2) continue;
</strong>  
  console.log("end: ", number);
  console.log("\n"); // creates a empty line
}

console.log("all items: ", numberList);
</code></pre>

{% code title="terminal" %}
```bash
$ node .
start: 1
end: 1

start: 2
start: 3
end: 3

all items: [1, 2, 3]
```
{% endcode %}
