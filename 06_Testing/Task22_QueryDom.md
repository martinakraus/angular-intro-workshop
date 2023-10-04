## Story

- As a user I want to see the heading of my app.
- The Heading of this app is displayed inside the `MainNavigationComponent`
- You can add a `data-testid`-Attribute to the `span`-Tag for querying easier

## Task

- Add a new file containing all book related specifications: _cypress/e2e/books.cy.ts_

## Hints

```typescript
//book.cy.ts
// Open
cy.visit('/');

// Query
cy.get('<INSERT THE CORRECT DOM QUERY HERE GETTING THE TITLE OF THE APP>').contains('BOOK MONKEY');
```

```html
//src/app/common-components/main-navigation/main-navigation.component.html
...
<span data-testid="app-title">BOOK MONKEY</span>
...
```

[Solution](https://github.com/martinakraus/angular-advanced-workshop/commit/6a6b883d0aa8bea723c0c47ce813958176ba24e9)
