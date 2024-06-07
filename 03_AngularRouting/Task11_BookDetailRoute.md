# Add BookDetail Route
1. Create a new Component BookDetail with angular-cli `ng generate component book/book-detail`
2. Extend Book with routerLink to create URL with ISBN parameter
3. Extend the Routes with a BookDetail route
4. Extend BookData service with getBookByIsbn(isbn: string)
5. Load data from service via getBookByIsbn(isbn: string) into BookDetail
6. Extend the BookDetail Template to display all data of a specific book in the view

## Hints

#### Implement the Component
BookDetailComponent

```ts
export class BookDetailComponent implements OnInit {
  route = inject(ActivatedRoute);
  bookApiService = inject(BookApiService);
  book$!: Observable<Book>;

  ngOnInit() {
    this.book$ = this.route.params.pipe(
      switchMap(params => this.bookApiService.getByIsbn(params?.['isbn']))
    );
  }
}
```

#### Navigate with the Router-Service to BookDetailComponent

```ts
// book.component.ts
export class BookComponent {
  books$ = inject(BookApiService).getAll();
  router = inject(Router);

  goToBookDetails(book: Book) {
    this.router.navigate(['books', book.isbn])
  }
}
```


#### Extend your Routing Module
Routes

`{ path: 'books/:isbn', component: BookDetailComponent }`
#### Extend and use the Service with a getBookByIsbn(isbn: string)

`HTTP GET http://localhost:4730/books/:isbn`

[Solution](https://github.com/martinakraus/bookmonkey-client/commit/9aa886d0bf75871677176ea5e18d09302eeb8bd1)
