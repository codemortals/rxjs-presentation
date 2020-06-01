# RxJS Presentation

## Examples

### [Range](src/range.html) - increment and use operators like `take`, `filter`, `map`

Simple example rxjs with no operators

```typescript
rxjs.range(1, 200)
  .pipe(
      // ...
  )
  .subscribe(x => console.log('output:', x));
```

Console output

```console
output: 1
output: 2
output: 3
...
output: 200
```

### [Click event](src/click.html) - with `takeUntil`

Simple example rxjs with no operators

```typescript
rxjs.fromEvent(buttonGo, 'click')
  .pipe(
      // ...
  )
  .subscribe((e) => console.log('MOUSE CLICKS', e.clientX, e.clientY));
```

Console output

```console
MOUSE CLICKS 28 26
MOUSE CLICKS 18 16
MOUSE CLICKS 12 16
MOUSE CLICKS 29 16
```
### [Mouse movement](src/mouse.html) - with `filter`, `throttleTime`, `map`

Simple example rxjs with no operators

```typescript
rxjs.fromEvent(document, 'mousemove')
  .pipe(
      // ...
  )
  .subscribe((e) => console.log('MOUSE MOVEMENTS', e.x, e.y));
```

Console output

```console

```
