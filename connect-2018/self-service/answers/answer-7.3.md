## Answer to exercise 7.3

The maximum margin size of 5 looks good, because it makes the whitespace between the cards the same as that between
the searchbar and the cards. The result is as follows:

``` html
<div class="row">
  <div class="col mt-5">
    {{search}}
  </div>
</div>

<div class="row justify-content-center">
  <div class="col-sm col-lg-3 mt-5">
    <div class="card">
      ...
    </div>
  </div>
  <div class="col-sm col-lg-3 mt-5">
    <div class="card">
      ...
    </div>
  </div>
  <div class="col-sm col-lg-3 mt-5">
    <div class="card">
      ...
    </div>
  </div>
</div>
```
