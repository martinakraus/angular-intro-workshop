## Story

As a user I want to see the heading of my app.

## Task

- Add a new file containing all book related specifications: _cypress/e2e/books.cy.ts_

## Hints

```typescript
// Open
cy.visit('/');

// Query
cy.get('<INSERT THE CORRECT DOM QUERY HERE GETTING THE TITLE OF THE APP>').contains('BOOK');
```
