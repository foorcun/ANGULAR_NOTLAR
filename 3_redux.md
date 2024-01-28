
# installation

```.sh
ng add @ngrx/store
```

# component create

```.sh
ng g c components/count
ng g c components/addCount
```

# app.component.html

```.sh
<app-add-count></app-add-count>
<hr>
<app-count></app-count>
```
eger prefix fur yapmissam:
```.sh
<fur-add-count></fur-add-count>
<hr>
<fur-count></fur-count>
```



# app > store folder olustur

```.sh
mkdir store
```

## counter.action.ts file olustur

```.sh
import { createAction } from '@ngrx/store';

export const countIncrement = createAction('[Count Component] Count Increment');
```

## counter.reducer.ts
```.sh
import { createReducer, on } from '@ngrx/store';
import { countIncrement } from './counter.action';

export const initialCount = 0; // asıl data

export const CounterReducer = createReducer(
  initialCount, // asıl data initial olarak veriliyor
  on(countIncrement, (state) => (state += 1)) // reducer state i alip degistiriyor
);

```


# app.module.ts

```.sh
import { CounterReducer } from './store/counter.reducer';
```
importta bulunan kodu asagidaki ile guncelle:
```.sh
    StoreModule.forRoot({ number: CounterReducer }),
```

## add-counter.component.ts

```.sh
import { Store } from '@ngrx/store';
import { countIncrement } from '../../store/counter.action';
```
```.sh
constructor(private store: Store<any>) {}

  addCount() {
    this.store.dispatch(countIncrement());
  }
```

## count.component.ts

```.sh
import { Store } from '@ngrx/store';
import { Observable } from 'rxjs';
```
```.sh
  number$: Observable<number>
  constructor(private store: Store<{ number: number }>) {
    this.number$ = this.store.select('number');
  }
```
not: en baslata field property olarak number: number =0; yapilmisti. <br>
field property number: number =0; bu kodlara donustu. <br>
not2: degisken isiminin sonuna $ isareti best practise olarak oneriliyor


# add-count.component.html

```.sh
<h1>Add Count Component</h1>
<button (click)="addCount()">Count Add</button>
```

# count.component.html

```.sh
<div style="margin-left: 5%;">
  <h1>Count Component</h1>
  <h1 style="color: red">{{number$ | async}}</h1>
</div>
```

# call flow - aciklama

## reducer flow (changing the state)
event (button click in the ) add-count.component.html > addCount() <br>
add-count.component.ts addCount() > 
countIncrement() is an action method, kind of a reducer identifier.<br>
CounterReducer is triggered because in the "on(countIncrement, ..." >
initial data is "initialCount" is changed with this logic: (state) => (state += 1)


## selector (reading the state)

count.component.html  \<h1 style="color: red">{{number$ | async}}\</h1> <br>
count.component.ts 
```.sh
  number$: Observable<number>;
  constructor(private store: Store<{ number: number }>) {
    this.number$ = this.store.select('number');
  }
```
number nerden geliyordersek:
app.module.ts
```.sh
    StoreModule.forRoot({ number: CounterReducer }),
```
not: bu su anlama geliyor. CounterReducer a initial data olarak verilen (ki initialCount,)
number olarak store a alinsin.
