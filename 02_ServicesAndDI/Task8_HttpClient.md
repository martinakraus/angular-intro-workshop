# Load data from local API
- Import the `HttpClientModule` in your `AppModule` and add it to the _imports_-Collection.
- Inject `HttpClient` via `constructor(private http: HttpClient)` in `BookApiService`
- Start our HTTP-Server `bookmonkey-api` in your shell.
- Load data from local API in `BookApiService` service via `http.get(URL)`
- Do not forget to unsubscribe

## Hints
### API starten
If not already installed
```bash
# console session
npm i -g bookmonkey-api
bookmonkey-api
# OR
npx bookmonkey-api
```

```typescript
import { HttpClientModule } from '@angular/common/http';
```

```typescript
import { HttpClient } from '@angular/common/http';
import { Observable } from 'rxjs';
```

```typescript
return this.http.get<Book[]>('http://localhost:4730/books')
```

```typescript
this.bookApiService.getBooks().subscribe(successFn);
```



[Solution](https://stackblitz.com/github/workshops-de/angular-workshop/tree/solve--load-data-from-local-api)
