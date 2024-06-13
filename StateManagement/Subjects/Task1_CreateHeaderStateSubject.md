### Create a HeaderService with a Subject

1. Create a `HeaderComponent`
2. Insert the `<app-header></app-header>` to your `app.component.html`
3. Create a `HeaderService` to your AppModule.
4. Add a Subject<string>  `header = new Subject<string>()` to your `HeaderService`.
5. Implement a `setHeader(): void` Function in your Service wish emits the Value 'I'm a title'
6. Inject the `HeaderService` inside your `HeaderComponent`
7. Inside your `HeaderComponent` subscribe to the Subject from the `HeaderService`
8. Bind the value you get inside you `next` handler to your `header.component.html` template.
9. Call the `setHeader()` function inside your `HeaderComponent` to set a title (we will do this just for now, later we will set the Header from other Components)


## Hints

```typescript
//  header.service.ts
header = new Subject<string>();

setHeader(title: string) {
 this.header.next(title);
}

// header.component.html
<h1>{{ header }}</h1>

// header.component.ts
// We subscribe to the subject (inside the component)
ngOnInit() {
  this.headerService.header.subscribe((header) => {
    this.header = header;
  });

 this.headerService.setHeader('I am a title');
}


```
