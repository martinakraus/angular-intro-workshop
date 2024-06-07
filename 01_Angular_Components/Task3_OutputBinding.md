# Apply an Output-Binding
It is time to allow our component to communicate with other components.

- Open _src/app/book-card/book-card.component.ts_
- - Bind to the event `click` of the `<a>`-Tag (aka. Detailslink).
- Assign the method `handleDetailClick($event)` to the Event-Binding.
- Switch to the component class.
- Implement the new method `handleDetailClick(click: MouseEvent)`.
- Log the value of the parameter `handleDetailClick` to the console.
- Prevent the page to reload by preventing the default behaviour of the link's click event _(see hint)_.
- Initialize a property `detailClick` with an `EventEmitter`.
- Type the `EventEmitter` to accept a `Book` as event payload.
- Annotate `detailClick` with the `@Output` decorator.
    - Make sure `@Output` & `EventEmitter` are imported from `@angular/core`.
- Emit the `detailClick`-Event within `handleDetailClick`.
- Switch to _src/app/app.component.html_
- Bind to the `detailClick`-Event of _<app-book-card>_ to a method `goToBookDetails($event)`
- Implement `goToBookDetails($event)` by logging book passed by _<app-book-card>_

## Hints
```ts
// src/app/book-card/book-card.component.ts

// Output-Binding
@Output() detailClick = new EventEmitter<Book>();

// Emit an event and prevent the default behavior of the a-Tag
handleDetailClick(click: MouseEvent){
  click.preventDefault();
  this.detailClick.emit(this.content);
}
```

```ts
// src/app/app.component.ts

// handling detailClick-Event
goToBookDetails(book: Book) {
  console.log('Navigate to book details, soon...');
  console.table(book);
}
```

[Solution](https://github.com/martinakraus/bookmonkey-client/commit/780755893c5c0ffee6caa946584157d2cf7f42e7)
