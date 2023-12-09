
# StratoxContainer
JavaScript container library designed for seamless communication between your libraries.

### Initialize
```js
import { StratoxContainer } from './node_modules/stratox/src/StratoxContainer.js';
const container = new StratoxContainer();
```

### Examples
```javascript
// Example 1
container.set("someObject", { test: "Container 1" });

console.log(container.get("someObject").test);
// Log response: Container 1

// Example 2
container.set("passingAFunction", function(arg1, arg2) {
	alert(arg1+" "+arg2);
});

container.get("passingAFunction", "Hello", "world!");
// Alert response: Hello world!
```
### Method list
#### Set a container or factory
```javascript
set(key, value, overwrite);
```
 - **key:** Unique container key/string identifier
 - **value:** Mixed value of whatever you want to share, e.g. String, number, object, function.
 - **overwrite:** Attempting to set a container multiple times will trigger a warning unless manual consent is provided by setting "overwrite" to true.

#### Set factory only
```javascript
setFactory(key, value, overwrite);
```
 - **key:** Unique factory key/string identifier
 - **value:** callable
 - **overwrite:** Attempting to set a container multiple times will trigger a warning unless manual consent is provided by setting "overwrite" to true.

#### Get a container or factory
```javascript
get(key, ...args);
```

 - **key:** Unique container key/string identifier
 - **args:** pass arguments to possible factory/function

#### Check if container/factory exists
```javascript
has(key);
```
 - **key:** Unique container key/string identifier

#### Check if is strict a "container".
```javascript
isContainer(key);
```

 - **key:** Unique container key/string identifier

#### Check if is strict a "factory/function".
```javascript
isFactory(key);
```
 - **key:** Unique factory key/string identifier


