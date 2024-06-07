# Pipes and Directives

## Add a date-Pipe to your BookCard
- Open _src/app/book-card/book-card.component.html_.
- Add a simple HTML Tag and bind an date-Object to it.

### Hints

  ```html
  <!-- book-card.component.html -->
  
  <h3>Moby Dick</h3>
  <h4>Herman Melville</h4>  
  <h5>{{ publishDate | date }}</h5>

  <!--
  ... link, abstract ...
  -->
  ```

```ts
// book-card.component.ts
import { BookCardComponent } from "./book-card.component";

export class BookCardComponent {
  ...
  publishDate = new Date();
}
```

## Implement a custom Directive
- Create a new directive by executing the following command `ng generate directive hover-highlight`. (Just one file will be generated)
- Add two `@HostListeners` for `mouseenter` and `mouseleave` (Make sure to import the HostListener from `@angular/core`)
- Implement a function `changeBackgroundColor` which takes a string and uses the `setStyle`-Function on the `Renderer2`-Class
- The function takes the `nativeElement` (using ElementRef), the Style-Attribute which should be set `backgroundColor` and the actual value
- Call the function `changeBackgroundColor` From within the two HostListeners

### Hints

  ```html
  <!-- app.component.html -->
...
<app-book-card
        appHoverHighlight
        [content]="book"
        (detailClick)="goToBookDetails($event)"
></app-book-card>
...
  ```

```ts
// hover-highlight.directive.ts
import { Directive, ElementRef, HostListener, Renderer2 } from '@angular/core';

@Directive({
  selector: '[appHoverHighlight]'
})
export class HoverHighlightDirective {
  constructor(private el: ElementRef, private renderer: Renderer2) {
  }

  @HostListener('mouseenter') onMouseEnter() {
    this.changeBackgroundColor('aqua');
  }

  @HostListener('mouseleave') onMouseLeave() {
    this.changeBackgroundColor('transparent');
  }

  private changeBackgroundColor(color: string) {
    this.renderer.setStyle(this.el.nativeElement, 'backgroundColor', color);
  }
}
}
```


[Solution](https://github.com/martinakraus/bookmonkey-client/commit/88ebc5d4d23168163c813c2f24e18600288c3c62)
