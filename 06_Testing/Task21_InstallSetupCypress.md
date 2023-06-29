# Install Dependencies

```bash
ng add @cypress/schematic
```

# Setup Test Command

```
// package.json

"scripts": {
  /* ... */
  "cypress:open": "cypress open",
}
```

# Run cypress initially

```bash
# start cypress app
# add initial directories for cypress
npm run cypress:open
```

# Configure TypeScript

Please create a `tsconfig.json` and place it in the cypress folder.

```json

{
  "compilerOptions": {
    "strict": true,
    "target": "es5",
    "lib": ["es5", "dom"],
    "types": ["cypress"]
  },
  "include": [
    "**/*.ts"
  ]
}
```
