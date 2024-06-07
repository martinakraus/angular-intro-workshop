# Add basic routing
- Create new component `AboutComponent` with `ng generate component about`
- Add a new Module `AppRoutingModule` (if you haven't already.)
    - This time, we need to do it manually, by creating a file (app-routing.module.ts) and setting up the code on our own.
- Add Angular's `RouterModule` to the `imports`- & `exports`-Collection.
- Add a constant `routes`.
- Pass `routes` to the `RouterModule`'s `forRoot` function.
- Configure the start route, redirecting to `/about`.
- Configure a book route, displaying the `BookComponent` (path: _books_).
- Configure an about route, displaying the `AboutComponent` (path: _about_).
- Switch to _AppModule_.
- Add the `AppRoutingModule` to the `imports`-Colleciton.
- Switch to _app.component.html_.
- Replace its content with `router-outlet`.
- Add a simple `NavigationComponent`, containing 2 links
    - Books
    - About
- Use the directive `routerLink` for the 2 links to navigate betweem the views.

> Don't forget to remove <app-book> from your AppComponent's template, otherwise you will see it twice.

## Hints

#** NavigationComponent **
```html
<nav>
  <a routerLink="/books">Books</a>
  <a routerLink="/about">About</a>
</nav>
```

**App Routes:**

```ts
// app-routing.module.ts
import { RouterModule } from '@angular/router';

const routes: Routes = [
  {
    path: '',
    pathMatch: 'full',
    redirectTo: '/about'
  },
  {
    path: 'books',
    component: BookComponent
  },
  {
    path: 'about',
    component: AboutComponent
  }
];

// ...

@NgModule({
  imports: [RouterModule.forRoot(routes)],
  exports: [RouterModule]
})
// ...
```

**Router outlet:**

```html
<!--app.component.html-->
<router-outlet></router-outlet>
```

[Solution](https://github.com/martinakraus/bookmonkey-client/commit/c46ac75534c32e1e6a6757cf896ee02829af6bed)
