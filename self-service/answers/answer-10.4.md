## Answer to exercise 10.4

Add the following to the Homepage CSS field:

``` css
a.card:hover {
  color: #333333;
  border-color: #999999;
}
```

Alternatively, you can use some SCSS syntax and write this instead:

``` css
a.card {
  ...
    
  &:hover {
    color: #333333;
    border-color: #999999;
  }
}
```
