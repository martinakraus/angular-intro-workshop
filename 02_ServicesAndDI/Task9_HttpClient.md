# Load data from local API
- Provide the `HttpClient` in your `AppModule` with the `provideHttpClient`-Function within the _providers_-Collection.
- Inject `HttpClient` via `constructor(private http: HttpClient)` in `BookApiService`
- Start our HTTP-Server `bookmonkey-api` in your shell.
- Load data from local API in `BookApiService` service via `http.get(URL)`

### Remember to start Backend API
If not already installed
```bash
# console session
npm i -g bookmonkey-api
bookmonkey-api
# OR
npx bookmonkey-api
```

## Hints
```typescript
// book-api.service.ts
getAll(): Observable<Book[]> {
  return this.httpClient.get<Book[]>(this.baseUrl);
}
```

```typescript
// app.module.ts
@NgModule({
  ...
  providers: [provideHttpClient()]
})
export class AppModule {
}
```



[Solution](https://github.com/martinakraus/bookmonkey-client/commit/2ccbecac7632294ff656b761629bab03b759a3a6)
