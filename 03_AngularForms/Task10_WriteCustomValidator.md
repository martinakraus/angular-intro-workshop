# Implement a Custom Validator
- Create a folder `validators` and add a file `author.validator.ts`
- Create the `isAuthorValidator` function that returns a ValidatorFn: `(control: AbstractControl): ValidationErrors | null`
- Think about a way to validate if the given value includes digits.
- If the value includes digits return a ValidationError
- Extend your template with an error message if the user types in a digit in the author input field

## Hints
```typescript
export function isAuthorValidator(): ValidatorFn {
    return (control: AbstractControl): ValidationErrors | null =>
    {
        const isAuthor = /***/
        return isAuthor ? {isAuthor: {value: control.value}} : null;
    };
}
```

```html
<small *ngIf="
    form.get('author')?.dirty &&
    form.get('author')?.hasError('isAuthor')"
             class="form-field-hint"
>
    Please insert an valid name
</small>
```
