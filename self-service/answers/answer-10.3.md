## Answer to exercise 10.3

Change the card row in the Homepage HTML field to this:

``` html
<div class="row justify-content-center text-center">
  <div class="col-sm col-lg-3 mt-5">
    <a class="card" href="/self-service/notifications">
      <div class="card-header">
        <i class="ii icon-notification"></i>
        <div>My Notifications</div>
      </div>
      <div class="card-body">
        <div>{{my_notifications_count}}</div>
      </div>
    </a>
  </div>
  <div class="col-sm col-lg-3 mt-5">
    <a class="card" href="/self-service/inbox">
      <div class="card-header">
        <i class="ii icon-inbox"></i>
        <div>My Inbox</div>
      </div>
      <div class="card-body">
        <div>{{my_inbox_count}}</div>
      </div>
    </a>
  </div>
  <div class="col-sm col-lg-3 mt-5">
    <a class="card" href="/self-service/requests">
      <div class="card-header">
        <i class="ii icon-request"></i>
        <div>My Requests</div>
      </div>
      <div class="card-body">
        <div>{{my_requests_count}}</div>
      </div>
    </a>
  </div>
</div>
```

To keep the correct colors, we have to be more specific in the CSS: the CSS rule for links is currently more specific
than the rule for `.card` elements. To fix this, adjust the card CSS from this:

``` css
.card {
  ...
}
```

to this:

``` css
a.card {
  ...
}
``` 
