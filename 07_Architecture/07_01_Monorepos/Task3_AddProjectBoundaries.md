### Enforce Module Boundaries

- Install Nx-Eslint Plugin:
`npm i @nx/eslint-plugin @nx/devkit`
- Add a tag to the `project.json` of each Project: 
```
'scope:ui'
'scope:my-first-app'
'scope:my-second-app'
```
- Open the `.eslintrc.json` and insert restrictions as follows:

```
1. The UI Library is only allowed to import code from itself
2. `my-first-app` is  allowed to import code from the UI-Library
3. `my-second-app` is only allowed to import code from itself
```

* lint all applications:

`nx run-many -t lint`


## Hints

```typescript
// .eslintrc.json
...
"@nx/enforce-module-boundaries": [
    "error",
    {
        "enforceBuildableLibDependency": true,
        "allow": [],
        "depConstraints": [
            {
                "sourceTag": "scope:ui",
                "onlyDependOnLibsWithTags": ["scope:ui"]
            },
            {
                "sourceTag": "scope:my-first-app",
                "onlyDependOnLibsWithTags": ["scope:my-first-app","scope:ui"]
            },
            {
                "sourceTag": "scope:my-second-app",
                "onlyDependOnLibsWithTags": ["scope:my-second-app"]
            }
        ]
    }
]
...
```

## Solution

[GitHub](https://github.com/martinakraus/my-monorepo/commit/24097bd66ad9e208f339276984bd588040ca22e8)

### Official Documentations

- [Enforce Module Boundaries](https://nx.dev/core-features/enforce-module-boundaries)
