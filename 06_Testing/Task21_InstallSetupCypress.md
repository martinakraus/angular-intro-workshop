# Install Dependencies

```bash
npm install cypress -D

npx cypress open
```

# Configure E2E Testing


Whenever you run Cypress for the first time, 
the app will prompt you to set up either E2E Testing or Component Testing. 
Click on "E2E Testing" to start the configuration wizard.

- You need to manually configure your `tsconfig.json`-File as follows:

```typescript
//cypress/tsconfig.json
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



[Solution](https://github.com/martinakraus/angular-advanced-workshop/commit/342e8baa8f67f775d7ac0de5c5aa8745b26c607f)
