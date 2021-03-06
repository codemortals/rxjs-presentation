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

### [Click event](src/click.html) - with operators `takeUntil`

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
### [Mouse movement](src/mouse.html) - with operators `filter`, `throttleTime`, `map`

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
MOUSE MOVEMENTS 501 571
MOUSE MOVEMENTS 733 362
MOUSE MOVEMENTS 749 164
```

### [Subject](src/subject.html)

Simple example rxjs with no operators

```typescript
const subject = new rxjs.Subject();
subject.subscribe((e) => console.log('Subject Subscription 1', e));
subject.subscribe((e) => console.log('Subject Subscription 2', e));
subject.subscribe((e) => console.log('Subject Subscription 3', e));
subject.next('Message 1');
```

Console output

```console
Subject Subscription 1 Message 1
Subject Subscription 2 Message 1
Subject Subscription 3 Message 1
```

### [Behavior Subject](src/behavior.html)

Simple example rxjs with no operators

```typescript
const behaviorSubject = new rxjs.BehaviorSubject('Message');
behaviorSubject.subscribe((e) => console.log('Behaviour Subject Subscription 1', e));
behaviorSubject.subscribe((e) => console.log('Behaviour Subject Subscription 2', e));
behaviorSubject.next('Message 1');
behaviorSubject.next('Message 2');
behaviorSubject.subscribe((e) => console.log('Behaviour Subject Subscription 3', e));
```

Console output

```console
Behaviour Subject Subscription 1 Message
Behaviour Subject Subscription 2 Message
Behaviour Subject Subscription 1 Message 1
Behaviour Subject Subscription 2 Message 1
Behaviour Subject Subscription 1 Message 2
Behaviour Subject Subscription 2 Message 2
Behaviour Subject Subscription 3 Message 2
```

### [Replay Subject](src/replay.html)

Simple example rxjs with no operators

```typescript
const replaySubject = new rxjs.ReplaySubject(3);
replaySubject.subscribe((e) => console.log('Replay Subject Subscription 1', e));
replaySubject.subscribe((e) => console.log('Replay Subject Subscription 2', e));
replaySubject.next('Message 1');
replaySubject.next('Message 2');
replaySubject.next('Message 3');
replaySubject.next('Message 4');
replaySubject.subscribe((e) => console.log('Replay Subject Subscription 3', e));
```

Console output

```console
Replay Subject Subscription 1 Message 1
Replay Subject Subscription 2 Message 1
Replay Subject Subscription 1 Message 2
Replay Subject Subscription 2 Message 2
Replay Subject Subscription 1 Message 3
Replay Subject Subscription 2 Message 3
Replay Subject Subscription 1 Message 4
Replay Subject Subscription 2 Message 4
Replay Subject Subscription 3 Message 2
Replay Subject Subscription 3 Message 3
Replay Subject Subscription 3 Message 4
```
