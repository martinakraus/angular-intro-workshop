# Implement a Custom Validator
- Create a folder `validators` and add a file `author.validator.ts`
- Create a function called `validAuthorName()` that returns a `ValidatorFn`: `return (control:AbstractControl) : ValidationErrors | null => {..}`
-  Exract the value from the control and check if there are any digits inside the given string. (Hint: you can use a Regex for is: `/[0-9]+/.test(value)`
-  If the value contains any digits return an `ValidationError`: `{ invalidAuthor: true }` otherwise return a `null`-Value
-  Add custom Validator as a second Validator to your Author-`FormControl`
-  Add another `<small>`-Tag beneath the `<input>`-Tag for the Author.
-  This Tag should be displayed as soon as the custom Validator `validAuthorName` sets the `FormControl` in an error State (`form.get('author')?.hasError('invalidAuthor')`) with the text "Der Name eines Autors darf keine Zahlen beinhalten"

## Hints
```typescript
// author.validator.ts
import {AbstractControl, ValidationErrors, ValidatorFn} from '@angular/forms';

export function validAuthorName(): ValidatorFn {
    return (control:AbstractControl) : ValidationErrors | null => {
        const value = control.value;
        if (!value) {
            return null;
        }

        const hasNumeric = /[0-9]+/.test(value);
        return hasNumeric ? { invalidAuthor : true }: null;
    }
}
```

```typescript
// book-new.component.ts

this.form.nonNullable.group({
      author:  ['', [Validators.required, validAuthorName()]],
      title: ['', [Validators.required]],
      ....
    }, )
```

[Solution](https://github.com/martinakraus/bookmonkey-client/commit/eb28fabbcaf88889595e79fd3de26f62a2f39f12)
