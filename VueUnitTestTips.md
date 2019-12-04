# Unit Test Tips for Vue.js
## Sinon: Default sandbox
> Sandboxes removes the need to keep track of every fake created, which greatly simplifies cleanup.

> Since sinon@5.0.0, the sinon object is a default sandbox. Unless you have a very advanced setup or need a special configuration, you probably want to just use that one.

![example](images/testing/sandbox_example_new.png)
<br><br>
When testing, we can do `sinon.restore` in `afterEach` block:<br>
![usage](images/testing/sandbox_usage_new.png)
[Official Website](https://sinonjs.org/releases/latest/sandbox/)

## $watch
Assume we wanna do something when `inputValue` changes:
![example](images/testing/watch_example.png)
In testing:
![test](images/testing/watch_test.png)
More details:
[Reactivity in Depth](https://vuejs.org/v2/guide/reactivity.html)
[Vue.set definition](https://vuejs.org/v2/api/#Vue-set)
[Reference](https://alexjover.com/blog/test-computed-properties-and-watchers-in-vue-js-components-with-jest/)

## Testing with vue-router
```
router.push(location, onComplete?, onAbort?)
```
> In 2.2.0+, optionally provide onComplete and onAbort callbacks to router.push or router.replace as the 2nd and 3rd arguments. ... In 3.1.0+, you can omit the 2nd and 3rd parameter and router.push/router.replace will return a promise instead if Promises are supported.

Assume we have a method:
![example](images/testing/router_example.png)
In testing:
![test](images/testing/router_test.png)
[Reference](https://router.vuejs.org/guide/essentials/navigation.html)

## chai-as-promise
Assume we wanna test error case thrown by a promise:
![example](images/testing/chai-as-promise_example.png)
In testing:
![usage](images/testing/chai-as-promise_usage.png)
[Official website](https://www.chaijs.com/plugins/chai-as-promised/)
** We might have a better way to test error case: 
[Example](https://www.chaijs.com/api/bdd/#method_throw)
