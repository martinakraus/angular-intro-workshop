# Use router with automatic component input bindings
- Enable the component input bindings within the `AppRoutingModule`
- Remove the `ActivatedRoute` in _BookDetailComponent_.
- 
- Define an `@Input` property binding for isbn.


## Hints

```typescript
// app-routing.module.ts

@NgModule({
  imports: [RouterModule.forRoot(routes, {bindToComponentInputs: true})],
  exports: [RouterModule]
})
export class AppRoutingModule {
}
```

```typescript
// book-detail.component.ts
export class BookDetailComponent implements OnInit {
  @Input() isbn = '';

  bookApiService = inject(BookApiService);
  book$!: Observable<Book>;

  ngOnInit() {
    this.book$ = this.bookApiService.getByIsbn(this.isbn);
  }
}
```

[Solution](https://github.com/martinakraus/bookmonkey-client/commit/aea680c1350a92d558267b5e3d10af9fa83a1975)

