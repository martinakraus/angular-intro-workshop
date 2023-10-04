## Task

Refine the afterEach-Hook by instrumenting cy.request to remove the book created by your test.


## Hints

```typescript
cy.request('DELETE', 'http://localhost:4730/books/<isbn>');
```

[Solution](https://github.com/martinakraus/angular-advanced-workshop/commit/b7e4f2f91efaefcb0de469d7c82ac66b999534f8)
