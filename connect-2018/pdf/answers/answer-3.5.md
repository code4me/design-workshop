## Answer to exercise 3.5

``` html
<div class="row">
  <label>Member</label>
  <div class="value">
    {{if member}}
      {{if member.id == ~root.recipient.id}}
        <strong>{{:member.name}}</strong>
      {{else}}
        {{:member.name}}
      {{/if}}
    {{else}}
      -
    {{/if}}
  </div>
</div>
```
