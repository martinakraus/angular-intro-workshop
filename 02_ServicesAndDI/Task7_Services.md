# Create a BookApiService
- Create a service handling Book-API operations 
- Execute the following Angular CLI command: `ng generate service book/book-api`.
- Implement the method `getAll()` that yields an array of Books.
- Inject `BookApiService` into the _BookComponent_.
- Get rid of the example books of _BookComponent_ by using the `BookApiService`

## Hints

#### Generate with ng-cli:

```
ng generate service book/book-api
```

```
// book.component.ts
constructor(private readonly bookApiService: BookApiService){}
```

[Solution](https://github.com/martinakraus/bookmonkey-client/commit/e485590f235750b57a4add8d093815c588e537eb)
