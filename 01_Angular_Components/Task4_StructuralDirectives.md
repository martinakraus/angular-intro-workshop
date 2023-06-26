# Use *ngFor
1. Create an array with sample books in your `AppComponent` component
2. Iterate over books with `*ngFor`
3. Use `*ngIf` to render the List of `BookCardComponents` just if `books` is defined

Bonus:
1. Implement `else`-Handler with `ng-template` 

## Hints

`*ngFor="let book of books"`

```
…
  books: Book[] = [
    {
      title: "Design Patterns",
      abstract: "Elements of Reusable Object-Oriented Software",
      author: "Martina Kraus"
    },
    {
      title: "REST und HTTP",
      abstract: "Entwicklung und Integration nach dem Architekturstil des Web",
      author: "Martina Kraus"
    },
    {
      title: "Eloquent JavaScript",
      abstract: "A Modern Introduction to Programming",
      author: "Martina Kraus"
    }
  ]
…
```

[Solution](https://stackblitz.com/github/angularjs-de/angular-workshop/tree/Use-ngFor)
