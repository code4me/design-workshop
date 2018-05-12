## Answer to exercise 3.2

Add the following below the Team field in the HTML:

``` html
{{if member}}
<div class="row">
  <label>Member</label>
  <div class="value">{{:member.name}}</div>
</div>
{{/if}}
``` 

