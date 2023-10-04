### Task

1. Open _cypress/e2e/books.cy.ts_
2. Place mocked books inside _cypress/fixtures/books.json_
3. Instrument mocked books to create a stubbed XHR-Request handled by cypress
4. Write a test in the newly generated spec file, ensuring that the stubbed response is used as expected

## Hints

### Cypress API

```typescript
cy.intercept('<METHOD>', 'URL', {fixture:'<FIXTURE-FILE-without-file-extention>'});
cy.visit();
```

### Mock Data

**cypress/fixtures/books.json**
```json
[
  {
    "title": "Design Patterns",
    "subtitle": "Elements of Reusable Object-Oriented Software",
    "isbn": "978-0-20163-361-0",
    "abstract": "Capturing a wealth of experience about the design of object-oriented software, four top-notch designers present a catalog of simple and succinct solutions to commonly occurring design problems. Previously undocumented, these 23 patterns allow designers to create more flexible, elegant, and ultimately reusable designs without having to rediscover the design solutions themselves.",
    "numPages": 395,
    "author": "Erich Gamma / Richard Helm / Ralph E. Johnson / John Vlissides",
    "publisher": "Bernd",
    "prize":"$9.99",
    "cover":""
  },
  {
    "title": "REST und HTTP",
    "subtitle": "Entwicklung und Integration nach dem Architekturstil des Web",
    "isbn": "978-3-86490-120-1",
    "abstract": "Das Buch bietet eine theoretisch fundierte, vor allem aber praxistaugliche Anleitung zum professionellen Einsatz von RESTful HTTP. Es beschreibt den Architekturstil REST (Representational State Transfer) und seine Umsetzung im Rahmen der Protokolle des World Wide Web (HTTP, URIs und andere).",
    "numPages": 330,
    "author": "Stefan Tilkov / Martin Eigenbrodt / Silvia Schreier / Oliver Wolf",
    "publisher": "Steffanie",
    "prize":"$10.88",
    "cover":""
  }
]
```

[Solution](https://github.com/martinakraus/angular-advanced-workshop/commit/d6a73283f8da7f2eae6493b6c8e1ffb6199184b8)
