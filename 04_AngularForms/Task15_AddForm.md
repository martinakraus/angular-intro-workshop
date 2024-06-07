# Add a BookNew Form and Route
- Create a new Component `BookNewComponent` for the Book-Feature with `ng generate component book/book-new`
- Configure a new Route inside the `book/book-routing.module.ts` File, displaying the `BookNewComponent` (path: new)
- Add a link from `BookComponent` with `routerLink` to the `new` route.
- Add `ReactiveFormsModule` to the imports-Array of the `BookModule`
- Inside the `book-new.component.ts`-File:
    - inject the `FormBuilder` from `@angular/forms`
    - Create a `FormGroup` by calling the `group`-Function on the injected `Formbuilder`
    - The formGroup should have Controls for  `isbn`,`author`,`title`,`subtitle`, and`abstract`
- Inside the `book-new.component.html`-File:
    - Add a `<form>`-Tag and bind the created `form` Property to the `[formGroup]`-Directive
    - For each created Control inside the FormGroup create one `<input>`-Tag and bind the FormControl-Keys to the `fromControlName`-Directive
    - Also add a Submit-Button with `type=submit`
    - In order to get notified is the user clicks on this button need to register to the `(ngSubmit)`-Event inside the `<form>`-Tag and bind it to a `submit()`-function
    - you need to implement this function as well inside the `book-new.component.ts`-File. Inside this function you can just log the `form` on the `console`

Run the application inside the Browser: You should see your form. After you filled it out and clicked on the Submit-Button you should see the whole `FormGroup`-Object inside your Browser Developer Console.

## Hints

```html
<form [formGroup]="form" (ngSubmit)="submit()">

  <input type="text" formControlName="author">
  <input type="text" formControlName="title">
  <input type="text" formControlName="subtitle">
  <input type="text" formControlName="abstract">
	....
  <button type="submit">Save</button>
</form>
```


```typescript
@Component({..})
export class BookNew Component {
  form: FormGroup;

  constructor(private formBuilder: FormBuilder) {
    this.form = this.formBuilder.group({
     author: [''],
     title: [''],
     subtitle: [''],
     abstract: [''],
    });
  }
}
```


## Bonus: Using TypeForm

```typescript

// Bonus TypeForm
type BookForm = {
isbn: FormControl<string| null>,
title: FormControl<string| null>,
author: FormControl<string| null>,
cover: FormControl<string| null>,
}

this.form = new FormGroup<BookForm>({
isbn: new FormControl<string | null>(''),
title: new FormControl<string | null>(''),
author: new FormControl<string | null>(''),
cover: new FormControl<string | null>(''),
})
```

Automatic generate a Form Type
```ts
export type IForm<T> = {
  [K in keyof T]-?: FormControl<T[K] | null>;
};
```



[Solution](https://github.com/martinakraus/bookmonkey-client/commit/77e6c49ad046b0d6f6bfafbe94db4005edb6ce29)
