# Exercise 2: Developer tools

## Introduction

As you have seen in the previous exercise, implementing and adjusting a design involves a lot of switching back and forth:

* In one browser tab, load the Self Service Design section of the Settings console.
* In another browser tab, load the Self Service portal.
* In the first tab, adjust something in the HTML and/or CSS. 
* Press Save.
* Switch to the second tab and refresh the browser.
* If it doesn't look right, switch back to the first tab.
* Adjust something in the HTML and/or CSS.
* Press Save.
* Switch to the second tab, and so on....
  
While this approach works, it is also (a bit) slow and can be frustrating.
In practice, implementing a design will likely involve a lot of trial-and-error,
essentially a long series of mini-experiments to see what works, what looks nice, and so on.
Having to switch tabs, press Save and refresh the browser for each of these mini-experiments
is a hassle and makes the feedback loop (time between making a change and seeing the effects of that change)
too long.

Fortunately, the Developer Tools that ship with all modern browsers can make
the feedback loop a lot shorter.

With the browser developer tools, you can make *live* adjustments to the HTML and CSS of a website,
which means that the effect of your changes is immediately visible.
This makes it very easy to experiment and try out different things.

Besides being a great tool for adjusting your design, the developer tools are also
very good for *learning* about other designs.
Want to know how Google did that nice shadow effect in their search bar?
Just open the developer tools and look it up.
Web developers use this technique a lot to learn about ideas and "borrow" them.

In this exercise, we will use the developer tools of Chrome.

(If you don't have Chrome: other modern browsers, such as Firefox, Safari and Edge,
all have similar developer tools, but the details of what you see and what you can do may vary.)

**Note**: Although the developer tools make it easy to try out adjustments to your design,
those adjustments are not *saved*. If you are happy with an adjustment and want to save it,
you will still have to make the corresponding adjustment in the Self Service Design form.  

## Exploring Self Service Designs

We will spend some time getting familiar with the developer tools, using it
to learn about the Self Service Designs that come included with your 4me Demo environment
and perform some mini-experiments on it.

Of all the sample designs, the one of the "Widget International" account is the most detailed one
and provides a good starting point for your own design.

Let's explore that design.

### Exercise 2.1

* Log in as howard.tanner@widget.com on widget.4me-demo.com
* Go to widget.4me-demo.com/self-service
* Open the developer tools (shortcut F12 on Windows or Cmd+Option+I on Mac)
* Go to the Elements tab, if it's not already open.
* Notice that you see the HTML structure of the page on the left,
  and the CSS rules that apply to the currently selected HTML element on the right
    (if you don't see them, make sure to select the Styles sub-tab).
* In the upper-left corner of the developer tools there is a small icon, the element inspector.
* Click it and then move the mouse over the page.

What happens on the page? What happens in the Elements tab?

**Note**: you can also open the developer tools by right-clicking somewhere on the page and selecting "Inspect" from the menu.  

### The Styles tab 

Using the element inspector, find and select the large white horizontal bar
that runs all the way from the left to the right of the screen.

(You might end up too "deep" in the HTML structure. If that happens, use the
HTML structure shown in the Elements tab to go up until you have selected the right element.)

---

In the Styles sub-tab on the right you can see the CSS rules and properties that apply to this element.

All the rules that affect the current element are shown.

First, the rules that directly apply to the element are displayed, ordered from
most specific to most general.
After that, the properties that are *inherited* from ancestor HTML elements are shown.

In short, you are seeing the Cascade of CSS (Cascading Style Sheets).

In the Styles tab, you can change a lot of the CSS, for example:
* change the value of a property
* toggle a property (on/off)
* add a new property
* add a new rule

### Exercise 2.2

* What happens when you toggle the checkbox in front of the `background` property?
* Can you change the color of the white horizontal bar to yellow?
* Can you make it slightly transparent?
* Can you make the font of the 3 headers ("Request Something", etc) larger?
* Can you change the color of the short description texts to red?
* Can you change the color of the headers from blue to black?

### Exercise 2.3

Can you change the background image of the whole page to
https://4me-demo-assets.s3-accelerate.amazonaws.com/self-service/background-widget-europe.jpg?
(If you see an animated background, resize your browser until it is less than 1600px wide).

Optional questions:
* What is the value of `background-size` property? 
* What does it mean? 
* What happens when you set the value to `contain`? What does it mean?
* It doesn't look very nice with this value, but it becomes somewhat better
  when you also change `background-repeat` to `repeat`.
  For what kinds of background would you use this combination of properties?  

### Exercise 2.4

When you use the element inspector and move the mouse over the page,
you can see that boxes in various colors appear on the page.

* How many different colors do you see? 
* Can you discover any elements that have *all* the colors?
* What do the colors mean?

**Note**: you can also move the mouse over the elements in the Elements tab
to make the boxes appear on the page.

### Exercise 2.5

You will have noticed that there is a gap between "My inbox" on the left and
the My Notifications, My Watchlist and Password reset links on the right.
(If you don't see it, make your browser window wider than 1200px.)

Using the Elements tab, can you find what's in the gap?
Why is it not shown on the page? Can you show it by toggling a property?

### Exercise 2.6

* Can you make the 3 blue links (starting with "My Notifications") less high?
* Can you increase the space between the links?

## Optional exercises

If you have time left, give the exercises below a try.

### Exercise 2.7

Find the image element with Howard Tanner's avatar. Play with its `border-radius`.
What happens if you set it to `100%`?

### Exercise 2.8

When you hover over one of the three links, you can see that it changes color.
This is achieved with a *pseudo-class*, which is a CSS selector that only applies
to an HTML element in a certain state - in this case, the *hover* state.

To see this, use the element inspector to select one of the links.
Next, find the "Toggle Element State" button in the Styles tab (it has the text `:hov`)
and toggle the `:hover` state.

Observe what happens:
* on the page
* in the elements tab
* in the styles tab

Can you implement such a hover effect on the three cards ("Request Something", "My Requests", "Log a Security Incident") 
in the large horizontal bar?

Note: to add a new CSS rule, click the `+` icon in the right corner of the Styles tab.

### Exercise 2.9

Can you adjust the header so that it is 100% of the browser width?

In other words, make it so that the hamburger menu icon is all the way to the left,
and the avatar is all the way to the right.
