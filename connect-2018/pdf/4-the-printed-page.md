# 4. Designing for the printed page

So far, the Change Summaries all fit on a single A4 page. What happens if the Change Summary becomes longer?

## Page breaks

Let's add a long note to one of the Changes and see what happens.

Go to https://wdc.4me-demo.com/changes/1673/edit.

Paste the following dummy text in the note field:

> Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nunc blandit vulputate diam nec vestibulum. Maecenas porttitor metus vel odio tincidunt tempor vel et ex. Phasellus auctor suscipit eros et bibendum. Etiam commodo magna ante, eget congue nisi pretium sed. Vestibulum ante ipsum primis in faucibus orci luctus et ultrices posuere cubilia Curae; Duis elementum at elit placerat consequat. Maecenas fermentum, turpis nec mollis semper, sapien est finibus ligula, nec convallis orci turpis at nibh. Sed ultricies facilisis lorem, id mattis arcu rutrum congue. Nam suscipit congue augue, quis tempus ante porttitor nec. Vivamus id dui ut massa auctor pharetra. Suspendisse potenti.
>  
>  Phasellus bibendum purus sed elit vulputate ullamcorper. Sed mi erat, luctus ac diam non, egestas consectetur dui. Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Praesent aliquam leo eget volutpat pellentesque. Vivamus luctus ac dui eu maximus. Duis aliquam mauris ac lorem tincidunt consectetur. Aenean at sapien odio. Sed justo odio, lacinia a maximus eget, feugiat sed justo. Nunc convallis augue nec dictum elementum.
>  
>  Quisque mollis ut lorem vitae viverra. Cras a ex nisl. Nulla et velit sed tellus euismod dignissim sit amet nec magna. Nam egestas rhoncus tortor, vel pellentesque lorem mattis a. Phasellus semper erat eget velit porttitor tristique vitae vel metus. In rutrum mauris non nunc sollicitudin posuere. Nunc posuere commodo diam. Duis tincidunt imperdiet felis ut pellentesque. Quisque sed erat fringilla, lacinia sem sed, eleifend augue. Donec nibh lorem, rhoncus lacinia gravida a, efficitur et sapien. Nunc tempus hendrerit imperdiet. Praesent iaculis nunc quis tincidunt blandit. Praesent vitae rutrum ex, a luctus lorem. In accumsan suscipit risus, at finibus justo hendrerit eget. Aliquam semper quam ac ornare bibendum.
>  
>  Aliquam ac dapibus massa. Integer aliquet quis leo nec porta. Praesent suscipit erat eu turpis volutpat, quis fringilla ante sodales. Praesent iaculis neque et felis sagittis molestie. Curabitur rhoncus ipsum quis porta tristique. Lorem ipsum dolor sit amet, consectetur adipiscing elit. In tempor ac mi sed rhoncus. Sed at ultrices mi. Maecenas urna ligula, lobortis eu enim at, molestie auctor neque. Curabitur id metus lorem. Suspendisse facilisis placerat ipsum sit amet imperdiet. Phasellus nec efficitur eros. Suspendisse vitae tempor quam. In sodales ex magna.
>  
>  Vivamus eu sem ac elit vulputate consectetur. Suspendisse cursus justo quis nisl pulvinar placerat. Proin vitae felis ac libero condimentum ultrices eu gravida ligula. Maecenas a tristique enim. Etiam ac ullamcorper leo, eget cursus tellus. Aliquam viverra ex dui, commodo vestibulum velit porttitor sed. Nullam porta, turpis vitae hendrerit imperdiet, orci urna vestibulum ex, sit amet tristique velit velit vitae leo. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Maecenas at dolor augue. Aliquam elit lectus, sagittis eu odio condimentum, placerat eleifend lectus. Sed eget nunc gravida tellus iaculis tincidunt. Aliquam in orci placerat dui aliquet cursus luctus quis diam.
>  
>  Cras blandit orci felis, nec sollicitudin neque tempor eget. Ut efficitur, odio et auctor fermentum, elit tortor placerat ipsum, sed dictum orci diam vitae ante. Vivamus accumsan porta sodales. Cras vitae lobortis lorem. Vestibulum nec lacus sed lectus euismod pulvinar. Donec at varius urna. Nulla facilisi. Etiam in lorem at quam porta luctus. Nam vestibulum velit nisl, a mattis justo aliquam sed. Quisque vestibulum commodo sollicitudin. In pulvinar neque eu ultricies ullamcorper.

Now generate a PDF sample for your PDF Design based on Change #1673.

You should see, that the long note starts on the second page.

The reason this happens, is because of the following CSS defined on line 90 of the CSS field:

``` css
.note {
  page-break-inside: avoid;
  
  ...
}

```

The `page-break-inside: avoid` declaration instructs the browser to try to keep all the text of a note on one page. 
Since the note does not fit on page 1, it is moved to the second page.

**Exercise 4.1**

One of the tasks in the PDF is split over two pages as well. Can you fix that?

[**View answer**](answers/answer-4.1.md)

## A repeating page header

Suppose you want to add a header (or footer) that is repeated on every page, such as a logo.

You can achieve this with the following technique:

* Wrap the *entire* HTML of the PDF Design in a `<table>` with a `<tbody>`.
* Add a `<thead>` at the beginning of the table, in which you put the content that you want to be repeated at the top of every page.
* Add a `<tfoot>` at the beginning of the table, in which you put the content that you want to be repeated at the bottom of every page.

The result looks like this:

``` html
<table>
  <thead>
    <tr>
      <td>
        ... Content of header ...
      </td>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>
        ... Content of your PDF Design go here ...
      </td>
    </tr>
  </tbody>
  <tfoot>
    <tr>
      <td>
        ... Content of footer ...
      </td>
    </tr>
  </tfoot>
```

Finally, add the following to the `CSS` field:

``` css
thead {
  display: table-header-group;
}
tfoot {
  display: table-footer-group;
}
```

**Exercise 4.2**

Try this technique and add the `<h1>` text "Change Summary for Approver" to the header of every page.

[**View answer**](answers/answer-4.2.md)

[Continue to the final step](5-task-list.md).
