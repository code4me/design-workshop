## Answer to exercise 5.3

Add the following to the CSS field:

``` css
.task {
  display: flex;
  
  .icon {
    width: 32px;
    text-align: center;
  }
  
  .details {
    flex-grow: 1;
  }
  
  .line {
    display: flex;
    justify-content: space-between;
  }
}
``` 

