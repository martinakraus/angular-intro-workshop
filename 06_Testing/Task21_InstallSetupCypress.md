# Install Dependencies

```bash
npm install cypress -D

npx cypress open
```

# Configure E2E Testing


Whenever you run Cypress for the first time, 
the app will prompt you to set up either E2E Testing or Component Testing. 
Click on "E2E Testing" to start the configuration wizard.

# Run cypress

```bash
# start cypress app
# add initial directories for cypress
npx cypress open
```

// cypress/tsconfig.json
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
