## Answer to exercise 3.4

``` html
{{if service_instances.length}}
<div class="row">
  <label>Service Instances</label>
  <div class="value">
  {{for service_instances}}
  {{:name}}<br>
  {{/for}}
</div>
{{/if}}
```
