# 2. How it works

For this part of the workshop, we will work in the Widget Data Center demo account.

In Chrome, go to https://wdc.4me-demo.com and log in as howard.tanner@widget.com.
Go to the Settings and select PDF Designs from the menu (https://wdc.4me.local/pdf_designs).

The PDF Designs console lists a Default Change Summary and a Default Project Summary. 
Select the Default Change Summary. 

You will see two fields:

* HTML
* CSS

Similar to the Self Service Design, these two fields together 
can be used to completely customize the contents and look&feel of the PDF.

## JsRender

Also similar to the Self Service Design, you can add dynamic content to the HTML 
by using the `{{...}}` syntax. In this case, however, the curly braces are not used to insert widgets,
but is actually the syntax of a small templating language called [JsRender](http://www.jsviews.com/#jsrapi).

For example, the syntax `{{:change.subject}}` means 'display the subject of the Change'.

If you scroll down to line 138 of the HTML field, you see the following:

``` html
<section>
  <h2>Implementation</h2>

  {{for change.tasks}}
  {{if status_key != 'completed' && status_key != 'canceled' && status_key != 'failed' 
        && service_instances.length}}
  <div class="implementation-task with-divider">
    ...
  </div>
  {{/if}}
  {{/for}}
``` 

The `{{for change.tasks}} ... {{/for}}` block loops over the list of tasks,
and evaluates the contents of the block once for each task.

The `{{if status_key ...}} ... {{/if}}` block displays its contents *only* if the specified condition holds.
In English, this condition can be read as 'the task should not yet be finished and should affect at least 1 Service Instance'.

This is already most of the JsRender syntax. During the exercises, you will encounter more examples.

## The Design process

Now click on the "Generate sample…" link.

A new window opens in which you can select a Change and decide whether to create a PDF or HTML sample of the selected Change.

Select one of the Changes, set the format to PDF and click the "Generate Sample" button.
After a while, a PDF document appears in the browser. 

The PDF format is good for checking a finished design, because it looks exactly like the one an actual approver receives.
When you are busy implementing a new design, however, the HTML format may be more useful.

For one thing, generating a HTML sample is much faster. But more importantly, when you generate a HTML sample, 
you can then use the Developer Tools of the browser to quickly experiment and try out design ideas, 
like we did during the Self Service Design part of this workshop.

### Technical side note: Under the hood

If you have ever printed a web page in Chrome, you may have seen that you can save the page to PDF.
Actually, this is exactly how 4me generates PDF documents. 

On the 4me servers, we create a web page in which we inject your custom HTML and CSS. 
Next, we let a special version of Chrome render the web page and save it to a PDF document.      

[Continue to the next step](3-using-jsrender.md).
