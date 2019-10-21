# Unit Test Tips for Vue.js

## Sinon: Sandbox
> Sandboxes removes the need to keep track of every fake created, which greatly simplifies cleanup.

![example](images/testing/sandbox_example.png)
<br><br>
When testing, we can do `sandbox.restore` in `afterEach` block:<br>
![usage](images/testing/sandbox_usage.png)

## Testing with vue-router
```
router.push(location, onComplete?, onAbort?)
```
> In 2.2.0+, optionally provide onComplete and onAbort callbacks to router.push or router.replace as the 2nd and 3rd arguments. ... In 3.1.0+, you can omit the 2nd and 3rd parameter and router.push/router.replace will return a promise instead if Promises are supported.

Assume we have a method:<br>
![example](images/testing/router_example.png)<br>
In testing:<br>
![test](images/testing/router_test.png)<br>
[Reference](https://router.vuejs.org/guide/essentials/navigation.html)

## $watch
Assume we wanna do something when `inputValue` changes:
![example](images/testing/watch_example.png)<br>
In testing:<br>
![test](images/testing/watch_test.png)<br>
More details:<br>
[Reactivity in Depth](https://vuejs.org/v2/guide/reactivity.html)<br>
[Vue.set definition](https://vuejs.org/v2/api/#Vue-set)<br>
[Reference](https://alexjover.com/blog/test-computed-properties-and-watchers-in-vue-js-components-with-jest/)

## chai-as-promise
Assume we wanna test error case:<br>
![example](images/testing/chai-as-promise_example.png)<br>
In testing:<br>
![usage](images/testing/chai-as-promise_usage.png)<br>
[Official website](https://www.chaijs.com/plugins/chai-as-promised/)
