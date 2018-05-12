## Answer to exercise 11.2

Add the following `{{search}}` widget to the `Global navigation HTML` field, so that it looks like this:

``` html
<div class="logo">
  <a href="/self-service">
    <img src="[URL from media library]">
  </a>
</div>
{{search placeholder="Search…"}}
{{navigation_menu}}
```

In the `CSS` field, change the `.global-navigation` rule to:

``` css
.global-navigation {
  .logo {
    margin: 20px;
  }
  
  img {
    width: 100%;
  }
  
  .widget-search {
    margin: 0 10px; // abbreviation of "0 margin on top and bottom, 10px margin on left and right".
  }
}
```
