# Build a simple canDeactivate guard
1. Create a guard with `ng generate guard book/confirm-deactivate`
2. Open a confirm box (Can be easily implemented with Browser API and the `confirm('Are you sure?')` Boxs)
3. Return the confirm value
4. use it for your `BooksDetail` route


## Hints

```typescript
export const confirmDeactivateGuard: CanDeactivateFn<BookDetailComponent> = (component: BookDetailComponent, currentRoute, currentState, nextState) => {
    // Add confirm box
};
```


Add guard to route:

```ts
{
    path: 'details/:isbn', 
    component: BookDetailComponent,
    canDeactivate: [confirmDeactivateGuard]
}
```

[Solution](https://github.com/martinakraus/bookmonkey-client/commit/a8c2d0e3671888e25554199a5ff01d80a8d96f50)

