# Bug
Cannot successfully run `graphql codegen`, as `prisma-binding` throws an error

## Reproducing the bug
Clone repo and run following commands

```
yarn
yarn codegen
```

## Expected result
It should generate `schema.ts` file with typescript types/interface for `schema.graphql`, based on `.graphqlconfig.yml`

## Actual Result
Throws an error:

```
$ graphql codegen
warning command prepare both exists in plugin /Users/minheq/Documents/Repositories/prisma-binding-bug/node_modules/graphql-cli-prepare and is shipped with the graphql-cli.
The plugin is being ignored.
✖ Generating bindings for project app...
TypeError: Cannot read property 'type' of undefined
    at getWhere (/Users/minheq/Documents/Repositories/prisma-binding-bug/node_modules/prisma-binding/dist/utils.js:44:9)
    at /Users/minheq/Documents/Repositories/prisma-binding-bug/node_modules/prisma-binding/src/utils.ts:41:12
    at Array.map (<anonymous>)
    at getTypesAndWhere (/Users/minheq/Documents/Repositories/prisma-binding-bug/node_modules/prisma-binding/src/utils.ts:38:21)
    at Object.getExistsTypes (/Users/minheq/Documents/Repositories/prisma-binding-bug/node_modules/prisma-binding/src/utils.ts:9:17)
    at PrismaTypescriptGenerator.renderExists (/Users/minheq/Documents/Repositories/prisma-binding-bug/node_modules/prisma-binding/src/PrismaTypescriptGenerator.ts:71:20)
    at PrismaTypescriptGenerator.render (/Users/minheq/Documents/Repositories/prisma-binding-bug/node_modules/prisma-binding/src/PrismaTypescriptGenerator.ts:19:32)
    at /Users/minheq/Documents/Repositories/prisma-binding-bug/node_modules/prisma-binding/src/bin.ts:69:34
    at step (/Users/minheq/Documents/Repositories/prisma-binding-bug/node_modules/prisma-binding/dist/bin.js:33:23)
    at Object.next (/Users/minheq/Documents/Repositories/prisma-binding-bug/node_modules/prisma-binding/dist/bin.js:14:53)
```
