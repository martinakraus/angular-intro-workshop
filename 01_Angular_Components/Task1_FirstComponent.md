- Open a second terminal.
- Switch to the directory where your Angular project is located.
- Create a new component by executing the following command `ng generate component book-card`.
- Recognize that four or three files are generated.
- Recognize that `app.module.ts` is updated (Later we will learn why this is needed).
- Recognize that your component has the selector `<app-book-card>`.

- Open _src/app/book-card/book-card.component.html_.
- Set up a simple HTML template visualizing book-information by using **static data**.
    - title
    - author
    - details-link
    - abstract

  ```html
  <!-- book-card.component.html -->
  
  <h3>Moby Dick</h3>
  <h4>Herman Melville</h4>  

  <!--
  ... link, abstract ...
  -->
  ```

- Use your component in `app.component.html`.
- Replace the existing content of `app.component.html` with `<app-book-card></app-book-card>`.
- Ensure that your component is displayed in the browser.
- Check [localhost:4200](http://localhost:4200).


[Solution](https://stackblitz.com/github/workshops-de/angular-workshop/tree/solve--your-1st-component)
