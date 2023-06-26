# Add a BookNew Form and Route
- Create a new Component `BookNewComponent` with the Angular CLI
- Add the Component to the `AppComponent`.
- Add `ReactiveFormsModule` to `AppModule`
- Inside the created Component, create a form containing inputs for author, title, subtitle, abstract.

Bonus:

- Extend `BookApiService` and post the book to the `bookmonkey-api`
- Make UntypedFormGroup typesafe

## Hints

```sh
ng g c book/book-new
```

```typescript
import {Validators, FormBuilder, FormGroup} from '@angular/forms';
```

```html
<form [formGroup]="newForm" (ngSubmit)="submit()">

  <input type="text" formControlName="title">
	....
	
	<button type="submit">Save</button>
</form>
```

```typescript
constructor(private formbuilder: FormBuilder) {
}

newForm = this.formbuilder.group({
      isbn: ['', [Validators.required]],
      title: ['', [Validators.required]],
      author: [''],
      abstract: ['']
    }, );
```

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



[Solution](https://stackblitz.com/github/workshops-de/angular-workshop/tree/solve--add-a-BookNew-form-and-route?file=README.md)
