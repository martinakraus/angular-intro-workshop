s# Create a BookApiService
- Create a service handling Book-API operations 
- Execute the following Angular CLI command: `ng generate service book/book-api`.
- Implement the method `getAll()` that yields an array of Books.
- Inject `BookApiService` into the _BookComponent_.
- Get rid of the example books of _BookComponent_ by using the `BookApiService`

## Hints

#### Generate with ng-cli:

```
ng generate service books/book-api
```

```
// book.component.ts
constructor(private bookData: BookApiService){}
```

[Solution](https://stackblitz.com/github/workshops-de/angular-workshop/tree/solve--create-a-BookApi-service)
