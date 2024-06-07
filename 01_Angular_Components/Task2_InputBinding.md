# Apply an Input Binding
Now, it is time to feed our component with data using an `@Input`-Binding.

- Open `src/app/book-card/book-card.component.ts`.
- Add a property `content`.
- Annotate the property `content` with `@Input`.
- Switch to the template of _BookCardComponent_ component.
- Bind the values coming with `content` using binding expression (e.g.`{{ content.title }}`).
- Switch to the `src/app/book-card/book-card.component.ts`.
- Initialize a property `book` with the properties _title_, _author_, _abstract_.
- Switch to the template of _AppComponent_.
- Bind the property `book` to the component `book-card` using its `@Input`-binding **[content]**.

## Make the Input binding type-safe:

- Create an _Interface_ called `Book`.
- Execute following command to create the interface: `ng generate interface book`.
- Open _src/app/book.ts_.
- Specify the following properties: _title_, _abstract_, _author_ all as `string`.
- Switch to the _AppComponent_.
- Annotate the property book with the interface `Book`.
- You might need to import `Book` from _'./book'_ if your editor misses to import the type automatically.
- Switch to the _BookCardComponent_.
- Annotate the `@Input` property content with the interface `Book`.
- Recognize that you now have auto-completion in both TypeScript- & Template-Files.

## Hints

```ts
// app.component.ts
export class AppComponent {
  book = {
    title: 'How to win friends',
    author: 'Dale Carnegie',
    abstract: 'In this book ...'
  };
}
```

```html
<!-- book-card.component.html -->
<h3>{{ content.title }}</h3>
<!-- ... -->
```

}

[Solution](https://github.com/martinakraus/bookmonkey-client/commit/dfd7dc8b976fb0fed58e01a86bb7d14da13d76e8)
