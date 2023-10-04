### Using Nx Dependency Graph

- Add another Angular Application to the workspaces
`nx g @nx/angular:app my-second-app --directory=apps/my-second-app --standalone`
- Use the `HeaderComponent` from your `UI`-Library also inside this Application `my-second-app` by inserting it inside the `AppComponent`
- Make sure, that you are using the correct `Path-Alias`
- Inspect your dependencies via Nx Graph: `nx graph`

__NOTE Nx 15 and lower use @nrwl/ instead of @nx/__
You can check your Nx Version with `nx --version`

* Run the application to verify everything is working

`nx serve my-second-app`

## Solution

[GitHub](https://github.com/martinakraus/my-monorepo/commit/e53f90425a9b50a024dee8591ee6596d132cdee5)

### Official Documentations

- [Nx App Generator](https://nx.dev/nx-api/angular/generators/application)
