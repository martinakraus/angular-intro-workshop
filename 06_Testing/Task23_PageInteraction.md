### Story

As a user I want to check if a book can be created.

### Task

1. Open _cypress/integration/books.spec.ts_
2. Set up a test
    - click the create button
    - fill in the books formula
    - save the new book
    - navigate back to the start page
    - assert that one more book is in the list as before

## Hints

```typescript
beforeEach(() => {
    cy.visit('http://localhost:4200');
    cy.get('<selector for book item>').as('books');
  });

  it('should increase the number of books by 1', () => {
    let countBefore = 0;
    cy
      .get('@books')
      .then(books => (countBefore = books.length))
      // navigate to create form
      .then(() => {
        // cy.get('<form-control>').type('value')
        // ...
        // submit form
      })
      // navigate to books list
      // assert books length
  })
```

## Generate random ISBN

```typescript
const randomISBN = Math.floor(1000000000000 + Math.random() * 900000);
```
