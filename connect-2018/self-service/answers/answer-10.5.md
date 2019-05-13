## Answer to exercise 10.5

The cards HTML will become like this:

``` html
<div class="row justify-content-center text-center">
  <div class="col-sm col-lg-3 mt-5">
    <a class="card" href="/self-service/notifications">
      <div class="card-header">
        <i class="ii icon-notification"></i>
        <div>My Notifications</div>
      </div>
      <div class="card-body count-{{my_notifications_count}}">
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
      <div class="card-body count-{{my_inbox_count}}">
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
      <div class="card-body count-{{my_requests_count}}">
        <div>{{my_requests_count}}</div>
      </div>
    </a>
  </div>
</div>
```

The following CSS rule accomplishes the desired effect:

``` css
a.card .card-body:not(.count-0) {
  color: #1c74bc;
  font-weight: bold;
}
```
