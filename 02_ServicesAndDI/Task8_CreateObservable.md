# Create an Observable
- Open _book-api.service.ts_
- Change return type of `getAll` to `Observable<Book[]>` instead of `Book[]`.
- Make use of the creation operator `of`.
- Use the Observable in `book.component.ts` and set books array in `subscribe`.
- Make sure that the books are still rendered.

## Hints

```ts
// book.component.ts
export class BookComponent implements OnDestroy {
  books: Book[] | undefined;
  subscription: Subscription;

  constructor(private readonly bookApiService: BookApiService) {
    this.subscription = bookApiService.getAll().subscribe(books => this.books = books);
  }

 ...
  ngOnDestroy() {
    this.subscription?.unsubscribe();
  }
}
```

```ts
//book-aoi.service.ts
export class BookApiService {
  books: Book[] = [...]

  getAll(): Observable<Book[]> {
    return of(this.books);
  }
}
```

[Solution](https://github.com/martinakraus/bookmonkey-client/commit/d87b56e9a305709ff0cdfc5e0a6ed855366e18ab)
