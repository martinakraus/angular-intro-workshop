# Use Lazy Loading for BooksModule
- Remove BooksModule from `imports` in AppModule
- Change books route inside `app-routing.module.ts` with the new `loadChildren`-Function
- - Set base books path to `''`
- Create a new Routing Module `book-routing.module.ts` and register the routes `forChild`
- Don't forget to import the `BookRoutingModule` into the `BookModule`

- Restart your `ng serve` since it has new starting points to compile
- Make sure your `BooksComponent`-View holds a `<router-outlet></router-outlet>`

## Hints

```
// app-routing.module.ts
const routes: Routes = [
  {path: '', redirectTo: '/about', pathMatch: 'full'},
  {path: 'books', loadChildren: () => import('./books/books.module').then(m => m.BooksModule)}
];
```

```
// books-routing.module.ts
import { NgModule } from '@angular/core';
import { RouterModule, Routes } from '@angular/router'
import { BookComponent } from "./book.component";
import { BookDetailComponent } from "./book-detail/book-detail.component";

const routes: Routes = [
  {
    path: '',
    component: BookComponent
  },
  {
    path: ':isbn',
    component: BookDetailComponent
  },
];

@NgModule({
  imports: [RouterModule.forChild(routes)],
  exports: [RouterModule]
})
export class BookRoutingModule {
}
```
[Solution](https://github.com/martinakraus/bookmonkey-client/commit/65cb1ff6fa8c368b678024de081f8149212890b5)
