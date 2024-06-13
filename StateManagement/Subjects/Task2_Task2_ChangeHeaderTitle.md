### Change Header title on Navigation to a new Component

1. Expose your Subject as an Observable to your HeaderComponent `header.asObservable()`
2. Inject the `HeaderService` inside each component you would like to set a new header (AboutComponent, BookComponent, BookDetailComponent)
3. Navigating to the AboutComponent the header should display: 'About Us'
4. Navigating to the BookComponent the header should display: 'All Books'
5. Navigating to a specific BookDetailComponent the header should display the booktitle of the specific book.
6. Don't forget to use the async pipe (if you haven't already) inside the `HeaderComponent` to subscribe to the `header$`-Observable

## Hints

```typescript
//header.service.ts

private header = new Subject<string>();
header$ = this.header.asObservable();
```

```typescript
// about.component.ts 

ngOnInit() {
	this.headerService.setHeader('About Us');
}

```
