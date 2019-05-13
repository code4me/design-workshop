# 9. Dropdown menu

Currently, the global navigation menu is not a 'proper' dropdown menu. 
It opens when you click on the hamburger icon and then stays open until you click on the icon again.

A common wish is to turn the menu into a dropdown menu.

Several other demo accounts in 4me already make use of the dropdown menu, so we'll borrow from them.

In Chrome, log in to https://widget.4me-demo.com as beatrice.baldwin@widget.com and go to My Inbox.

If you click on the hamburger icon, you will see that:

* the dropdown menu appears;
* the rest of the page is slightly darkened (the *backdrop*).

Click outside the menu to close it. 

## How it works

With the menu still closed, open the Developer Tools and look up the `<body>` element. 
You will see that its `class` attribute lists several classes, such as `chrome`, `user-lng-en-US` and `homepage`.

Now click on the hamburger icon again so that the dropdown menu appears.
Notice that an extra class is added to the body: `global-nav-is-open`.

Click somewhere on the backdrop. Notice that the `global-nav-is-open` class disappears.

We use this class in the CSS rules to control whether the global navigation menu and the backdrop are visible.
The CSS looks similar to this:

``` css
body:not(.global-nav-is-open) .global-navigation {
  display: none; // Hide the global navigation when the .global-nav-is-open class is not present on the body 
}

body:not(.global-nav-is-open) #itrp-backdrop {
  display: none; // Hide the backdrop
}

body.global-nav-is-open .global-navigation {
  display: block; // Show the menu
  position: fixed; // Fix its position...
  top: 40px; // ...to about 40px from the top of the screen (just underneath the hamburger menu)
  z-index: 1000; // Put the menu on top of everything.
}

body.global-nav-is-open #itrp-backdrop {
  display: block; // Show the backdrop
  position: fixed; // Fix its position...
  top: 0; bottom: 0; left: 0; right: 0; // ... to the entire browser window 
  z-index: 999; // Put the backdrop on top of everything, except the navigation menu
}
```

It is important to note that the HTML of the global navigation menu and the backdrop are always present on the page.
4me injects only a tiny bit of logic:

* Clicking on the hamburger icon adds the class `global-nav-is-open` to the `<body>` element.
* Clicking on the backdrop removes the class `global-nav-is-open`.   

This is enough to support many scenarios via pure CSS, including a dropdown menu or a menu that is always visible.
You could even create a horizontal menu with all menu items next to each other. 

## Animated menu on mobile

On mobile devices, a dropdown menu would not work. 
It is more natural for the menu to appear along the entire left-hand side of the screen, when you click on the hamburger menu.

To see this, click on the Toggle Device Toolbar icon in the Developer Tools and select a mobile device such as the iPhoneX.
Refresh the page and click on the hamburger menu icon.     

You will see that the menu slides in from the left with a brief animation. 
This is also achieved with CSS, using media queries and the properties `transition` and `transform`:

``` css
@media (max-width: 767px) { // Only on small screens
  body .global-navigation {
    position: fixed; // Fix the navigation menu...
    top: 0; // ... to the top of the screen
    height: 100vh; // Make it as high as the viewport 
    width: 14em; // Make it 14em wide
    left: -14em; // And put it just outside the visible window (so that it is initially hidden)
    transition: transform 300ms; // When the menu is 'transformed', animate the transition for a duration of 300 milliseconds  
  }

  body.global-nav-is-open .global-navigation { // When the menu is open...
    transform: translate3d(14em, 0, 0); // ...move the menu 14em to the right, so that it becomes visible.
  }
}
```

## Implement the dropdown menu in GlobalNet

Return to the Self Service Design of GlobalNet.

In the `CSS` field, add the following:

``` css
// Use a dropdown menu on larger screens
@media (min-width: 768px) {
  .global-navigation {
    min-width: 16em;
    max-width: 16em;
  }

  body.global-nav-is-open .global-navigation {
    position: fixed;
    left: 0;
    top: 40px;
    margin-left: 10px;
    min-height: 0;
    box-shadow: 1px 5px 10px 0px rgba(0,0,0,0.3);
    float: inherit;
    z-index: 1000;
    background: white;
  }
  body.global-nav-is-open #itrp-backdrop {
    display: block;
    background: rgba(0, 0, 0, 0.2);
  }
  body.global-nav-was-open .global-navigation {
    display: none;
  }
}

// Slide in from the left on smaller screens
@media (max-width: 767px) {
  .global-navigation {
    position: fixed;
    top: 0;
    bottom: 0;
    left: -14em;
    z-index: 1000;
    background: white;
    color: #40474d;
  }
}
```

Save the design and check the results in the browser. Use the developer tools to switch between large and small screens
and make sure the menu works correctly.

[Continue to the next chapter](10-highlights.md).
