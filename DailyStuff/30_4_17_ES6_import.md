# 30th April 17' | ES6 import, export

## Ok so import export. Let's remember all the types.

### # Destructuring in ES6 [codepen link](http://codepen.io/kumar935/pen/JNNXvL)

### # ES6 import and export

So ways to export and import:


1.

__Export__: `export default something;`. `something` can be a function and object or a variable, or an expression like {var1, var2}.

__Import__: `import something from 'module-name'. 


2.

__Export__: `export {something, somethingElse};`

__Import__: `import {something, somethingElse as moreConvenientName} from 'module-name';` or just `import * as convenientName from 'module-name';` (convenientName will be the object of all the exports from the module)


3.

__Export__: whatever

__Import__: `import 'module-name';`


More ways to export/import. (Wonder how these can be used)

`export {stuff as default, thing, anotherThing};`

`export * from 'somewhere';`

`export {import1 as name1, import2 as name2} from 'wherever';`

`import defaultMember, {otherMember, anotherMember} from 'module-name';`






