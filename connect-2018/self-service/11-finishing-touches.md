# 11. Finishing touches

In this final step we will deal with the global navigation menu.

## What we want to achieve

We removed the search and time spent icons from the navigation bar, but we still want these to be accessible
via the dropdown menu.

We will make it look like this:

![Dropdown menu](images/globalnet-dropdown-menu-design.png)

## Styling the search bar

The big search bar on the homepage and the little one in the dropdown menu have exactly the same styling.
Therefore, the CSS to style it should be added to the `CSS` field of the Self Service Design: 

``` css
.widget-search {
  .search-component {
    .search-container {
      .search-phrases {
        background: white;
        padding: 0;
      }

      .search-fields {
        height: inherit;
      }

      .search-q {
        height: inherit;
        padding-left: 1.5rem;
        border-radius: 2px;
        border-color: #ccc;
        &:focus {
          box-shadow: 0 2px 2px 0 rgba(0,0,0,0.16);
        }
      }
    }

    .search-btn {
      height: inherit;
      top: 0;
      right: 0;
      width: 4.5rem;
      display: flex;
      align-items: center;
      justify-content: center;
    }

    &:not(.with-inactive-search-btn) {
      .search-btn {
        background: #999999;
        color: white;
        border-color: transparent;

        &:hover {
          background: #333333;
        }
      }
    }
  }
}
```

## Customizing the global navigation menu

**Exercise 11.1**

The `Global navigation HTML` field of the Self Service Design uses the `{{brand}}` widget to render a link to the homepage with the account name.

Can you replace this with a logo that links to the homepage instead? The result should look similar to this:

![Menu with logo](images/menu-with-logo.png)

[**View answer**](answers/answer-11.1.md)

**Exercise 11.2**

Add the search bar to the global navigation menu, so that it looks like this:

![Menu with search bar](images/menu-with-search-bar.png)

[**View answer**](answers/answer-11.2.md)

**Exercise 11.3**

The 'My Timesheet' link in the navigation menu is by default hidden on larger screens.
We want to always display it, no matter the screen size. Can you make this change?

[**View answer**](answers/answer-11.3.md)

## The final result

Congratulations, you finished the Self Service Design for GlobalNet!

The design should now look very similar to the screenshots we showed at [the beginning](1-introduction.md).
 
