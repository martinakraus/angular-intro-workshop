# Add Form Validation
Let's add some Form Validation!

- Inside the `book-new.component.ts`-File add the `Validators.required` as a second Parameter inside the FormControls of `title` and `author`
- Now we can add some template logic whenever one or more Validators are in an error state:
  - Add a `<small>`-Tag with a `*ngIf`-directive beneath the `<input>`-Tags of the `title` and `author`-Input
  - The condition if the `<small>`-Tag is displayed should be based on the Error State of the FormControl: `form.get('<keyOfFormControl>')?.hasError('required')`
  - Disable the `<button>`-Tag as long as the whole `form` is not in a valid state by using the `disabled`-Property:  `[disabled]="newForm.invalid"`
## Hints

```typescript
constructor(private formBuilder: FormBuilder) {
  this.form = this.formBuilder.group({
    author: ['', [Validators.required]],
    title: ['', [Validators.required]],
    subtitle: [''],
    abstract: [''],
  });
}
```
​
```html
<form [formGroup]="form" (ngSubmit)="create()">
  <label>
    <span>Title</span>
    <input formControlName="title" />
    @if (form.get('title')?.dirty && form.get('title')?.hasError('required')) {
      <small>Please insert a title.</small>
    }
  </label>
  <label>
    <span>Author</span>
    <input formControlName="author" />
    @if (form.get('author')?.dirty && form.get('author')?.hasError('required')) {
       <small>Please insert a Author.</small>
    }
  </label>
  ....
  <button type="submit" [disabled]="form.invalid">Save</button>
</form> 
```



[Solution](https://github.com/martinakraus/bookmonkey-client/commit/2326e8719759e8bdf4e530691ded43d7543fee41)
