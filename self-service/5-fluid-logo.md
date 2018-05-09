# 5. The logo

As our next step, we'll add the logo.

## What we want to achieve

We put the logo directly above the search bar, also centered on the page. 
Like the search bar, it should resize according to the width of the browser window.

![Logo and search bar](images/logo-and-searchbar.png)

## Upload the logo to the Media Library

First, log in to https://globalnet.4me-demo.com as frederic.anderson@globalnet.com
and go to the Media Library. Create a new Media File and upload the following image: 

![GlobalNet logo](images/globalnet-logo.png)

## Another row in the grid

**Exercise**
 
 Add the logo to the `container` as another row with a single column.

Use an `<img>` element for the logo itself.

Don't worry about the size of the image just yet.

**Solution**

The Homepage HTML field should now contain the following.    

``` html
<div class="container">
  <div class="row no-gutters align-items-center main-content">
    <div class="col">
      <div class="row">
        <div class="col-sm">
          <img src="...">
        </div>
      </div>
      
      <div class="row">
        <div class="col">
          {{search placeholder="How can we help you?"}}
        </div>
      </div>
    </div>
  </div>
</div>
```  

## Image size

Unfortunately, the image is too big, and it does not resize when you resize the browser window.
In other words, it is not responsive.

This is another place where Bootstrap can help. It defines a helper class that you can add to the `<img>`
to make it responsive, as defined here: https://getbootstrap.com/docs/4.1/content/images/.

**Exercise**
 
Go on and make the appropriate change.

**Solution**

Add the `img-fluid` class to the `<img>` tag, as follows:

``` html
<img class="img-fluid" src="...">
```  

[Continue to the next step](6-media-queries.md).
