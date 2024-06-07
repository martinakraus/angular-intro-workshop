# Extend BookApiService
In order to send the book to our Backend we need to extend our BookApiService for another Request.

- Extend the `BookApiService` with a `create` method
- The method `create` should take a book (`Book`) as a parameter and send it with a POST request.
- Inject the service inside of the `BookNewComponent`
- Extract the form data from the `FormGroup` (you can use the  `getRawValue`-Function from the `FormGroup` for this)
- Extend the FormGroup with a FormControl for `isbn` (Otherwise the backend will return an error about the missing isbn property)
- Call the `create` method from the `BookApiService` and give in the extracted form data

## Hints

```typescript
// book-api.service.ts
create(book: Book): Observable<Book> {
  return this.http.post<Book>('http://localhost:4730/books', book)
}
```

```typescript
// book-new.component.ts
form = this.formBuilder.nonNullable.group({
  isbn: ['', [Validators.required]]
  title: ['', [Validators.required]],
  subtitle: [''],
  author: ['', [Validators.required]],
  abstract: [''],
});

constructor(private formBuilder: FormBuilder, private bookApiService: BookApiService) {...})

submit() {
  this.bookApiService.create(this.form.getRawValue() as Book).pipe(take(1)).subscribe()
}
```



[Solution](https://github.com/martinakraus/bookmonkey-client/commit/9d68f275e0eac0bcd703d10f28a81dd57b0079ea)
