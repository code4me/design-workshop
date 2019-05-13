## Answer to exercise 3.3

You can use the [`{{else}}`](http://www.jsviews.com/#elsetag) tag for this:

``` html
<div class="row">
  <label>Member</label>
  <div class="value">
    {{if member}}
    {{:member.name}}
    {{else}}
    -
    {{/if}}
  </div>
</div>
``` 

It is also possible to use the [onError](http://www.jsviews.com/#onerror@onerror) property of JsRender 
and write the following:

``` html
<div class="row">
  <label>Member</label>
  <div class="value">{{:member.name onError="-"}}</div>
</div>
``` 
