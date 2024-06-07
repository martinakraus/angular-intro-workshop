# Use Built-in Control Flow Syntax

1. Create an array with sample books in your `AppComponent` component
2. In order to use the new Built-in Control Flow Syntax we need to add an isbn property to the current book model
3. Iterate over books with `@for`
4. Use `*@if` to render the List of `BookCardComponents` just if `books` is defined

Bonus:
1. Add an `@empty`-Block

## Hints
```
@if (books) {
  @for (book of books; track book.isbn) {..}
}
```

```
…
  books: Book[] = [
    {
      title: "Design Patterns",
      abstract: "Elements of Reusable Object-Oriented Software",
      author: "Martina Kraus",
      isbn: "1"
    },
    {
      title: "REST und HTTP",
      abstract: "Entwicklung und Integration nach dem Architekturstil des Web",
      author: "Martina Kraus",
      isbn: "2"
    },
    {
      title: "Eloquent JavaScript",
      abstract: "A Modern Introduction to Programming",
      author: "Martina Kraus",
      isbn: "3"
    }
  ]
…
```

[Solution](https://github.com/martinakraus/bookmonkey-client/commit/5669b83008c6e253122bf749ff03059a61f52e49)
