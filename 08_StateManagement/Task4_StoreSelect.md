### Store Select

- Open _book-list.component.ts_
- Inject the `Store`
- Use the Store selecting the books instead of using the `BookApiService`

> _Now, we are disconnected from the API. Later on we will load the books via HTTP again._

- Create a new book.
- After navigating back to the book list you should see the created book selected from the store.

## Hints

__Current shape of the Store__

```js
{
  book: {                    // feature name
    bookCollection: {        // slice
      entities: []           // data
    }
  }
}
```

__Select data__

```ts
this.store.select(state => state.<feature name>.<slice>.<data>)
```
