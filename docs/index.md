## Welcome to Mobin Docs





** Let's start with Rxjava2 documents**
=========

**RxJava2 useful operations**



**1.Buffer:** this method gathers items emitted by observable into a batch and emits the batch instead of items one by one. *Ex.* `buffer(3)` emits a batch including 3 items of emitted data.

**2.Debounce:** this method emits the data when a specified time span is passed. it will be useful when an observable emits data rapidly and you want to receive them in a specific timely manner. *Ex.* Let’s say user want to search for `RxJava`. Without debounce, there would be multiple calls to server for keywords `R`, `Rx`, `RxJ` and so on. Instead we can give user a time period say 300 milli sec to type and send the query the to server. Most probably user can type upto `RxJ` in the given time period.
Here, we have used `debounce(300, TimeUnit.MILLISECONDS)` which means the query will be emitted every 300 milli seconds

**3.Filter:** this method allows the observable to emit only the values those pass the test. 

**4.Skip:** `skip(n)` skips the N first items emitted by an observable.finally the rest of items will be emitted.

**5.SkipLast:** `skipLast(n)` skips the n last items emitted by an observable.finally the rest of items will be emitted.

**6.Take:** `take(n)` acts exactly opposite to skip. It takes first N emissions of an Observable.

**7.TakeLast:** `takeLast(n)` takes last N emissions of an Observable.

**8.Distinct:** this method is avoiding duplicate the data those emitted by an observable *Ex.* 
in: 20 , 20 , 100 , 200 , 100 , 300 , 20   
out: 20 , 100 , 200 , 300

**9.Reduce:** this method applies a function on the first item that emitted by an observable and applies the result on the second item. this process continious until the last emission. once all the data is emitted , it emits the final result.

**10.Concat:** this method combines the result(output) of two or more observables. so when the first observable emitted , the second one starts to emit. it means the concat function follows sequential execution.
*Ex.* 
`combine(getFirstObservable , getSecObservable);`
out : item1 , item2 of firstOb
item1 , item2 of secOb

**11.Merge:** this method looks like the concat method. but it does'nt follow the sequential execution. so the data those emitted are completely random.
*Ex.* 
`merge(getFirstObservable , getSecObservable);`
out : item1 of firstOb ,  item2 of secOb , item3 of secOb , item4 of firstOb ...


## hope you enjoy it :)

