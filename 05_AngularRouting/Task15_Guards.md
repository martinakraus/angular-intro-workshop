# Build a simple canDeactivate guard
1. Create a guard with `ng generate guard books/confirm-deactivate`
2. Open a confirm box (Can be easily implemented with Browser API and the `confirm('Are you sure?')` Boxs)
3. Return the confirm value
4. use it for your `BooksDetail` route


## Hints

```typescript
export const canLeaveGuard: CanDeactivateFn<BookDetailComponent> = (component: BookDetailComponent, currentRoute, currentState, nextState) => {
    // Add confirm box
};
```


Add guard to route:

```ts
{
    path: 'details/:isbn', 
    component: BookDetailComponent,
    canDeactivate: [ canLeaveGuard ]
}
```


