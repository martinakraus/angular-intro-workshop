### Add a Library

- Add a Angular Library to the Workspaces:
`nx g @nx/angular:library ui --tags=ui --directory=libs/ui`
- Add a Component to the created Library:
`nx g @nx/angular:component header --project=ui --standalone`
- Export the `HeaderComponent` trough your public API in the `index.ts`
- Use the `HeaderComponent` from your `UI`-Library inside the Application `my-first-app` by inserting it inside the `AppComponent` (you can remove the existing Component `NxWelcomeComponent`)
- Make sure, that you are using the correct `Path-Alias`

__NOTE Nx 15 and lower use @nrwl/ instead of @nx/__
You can check your Nx Version with `nx --version`

* Run the application to verify everything is working

`nx serve my-first-app`

## Hints

```typescript
// index.ts

export * from './lib/ui.module';
export { HeaderComponent } from './lib/header/header.component';
```

```html
// app.component.html

<my-monorepo-header></my-monorepo-header>
```

```typescript
// app.component.ts
import { Component } from '@angular/core';
import { HeaderComponent } from "@my-monorepo/ui";

@Component({
  standalone: true,
  imports: [ HeaderComponent ],
  selector: 'my-monorepo-root',
  templateUrl: './app.component.html',
  styleUrls: [ './app.component.scss' ],
})
export class AppComponent {
  title = 'my-first-app';
}

```

## Solution 
[GitHub](https://github.com/martinakraus/my-monorepo/commit/20247e535141bc6b006e91897d91504c682e373b)


### Official Documentations

- [Nx Lib Generator](https://nx.dev/nx-api/angular/generators/library)
- [Nx Component Generator](https://nx.dev/nx-api/angular/generators/component)

