# Create a BookModule
Now we want to structure our app into features.
Therefore we introduce a new NgModule.

- Create a module using the Angular CLI: `ng generate module book`.
- Create a component that will take all the code of _AppComponent_: `ng generate component book/book --flat`.
- Move all book related code to the `book/`-folder.
    - _book.ts_
    - _book-card/_
    - _book-filter/_
- Add the Component-Types _BookCardComponent_ & _BookFilterPipe_ to the declarations of _BookModule_.
- Open _app.module.ts_.
- Remove all book related code.
    - Remove _BookCardComponent_ & _BookFilterPipe_ from declarations.
- Add _BookModule_ to the `imports`-Collection.
- Transfer all properties and methods of _AppComponent_ to _BookComponent_.
- Transfer the content of _app.component.html_ to _book.component.html_.
- Transfer the content of _app.component.scss_ to _book.component.scss_.
- Open app.component.html
- Add `<app-book></app-book>` to the template.
- Check if all `import`-statements are correct.

> *Often the import-Statements are updated automatically by your editor, but sometimes the end result is not perfect. If you experience that your app does not compile, check & correct the import-Statements.*
- *If it still not works, reboot the Angular CLI.*
- *If it still not works, consult your trainer.*
