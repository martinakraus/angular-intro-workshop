## Task

Refine the afterEach-Hook by instrumenting cy.request to remove the book created by your test.


## Hints

```typescript
cy.request('DELETE', 'http://localhost:4730/books/<isbn>');
```
