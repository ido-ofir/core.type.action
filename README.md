# core.type.action

enables buisness level actions

```js
let core = new require('core.constructor')();
 
core.plugin(
   require('core.type.action')
);
 
// define an action using core.Action method
core.Action({
    name: 'setEmail',
    dependencies: ['moduleA', 'moduleB'],
    schema: [
        {
            key: 'email',
            type: 'string'
        }
    ],
    run({ email }, promise){
        
        core.set('email', email);
        promise.resolve(email);
    }
});

// run an action using core.run method
core.run('setEmail', { email: 'koko@gmail.com' });
```
