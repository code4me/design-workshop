# 3. Using JsRender

Let's first practice a little with JsRender syntax.

Create a new PDF Design of category Change Summary and give it a name.

You will see that the HTML and CSS fields are prepopulated and are exactly the same as that of the Default Change Summary.

**Exercise 3.1**

Adjust the task list, so that it displays, below the Impact field, the name of the team to which each task is assigned.

[**View answer**](answers/answer-3.1.md)

**Exercise 3.2**

Below the team, also display the currently assigned member.
The row should only be displayed if the task is assigned to a team member.

To test if it works for tasks without member, edit one of the tasks:

* Go to https://wdc.4me-demo.com/tasks/21356/edit, which is one of the implementation tasks of Change #1673
* Clear the member field and save the task.
* Generate a sample of your PDF design for Change #1673.

[**View answer**](answers/answer-3.2.md)

**Exercise 3.3**

Continuing the previous exercise, can you change it so that the Member row is always displayed, but shows a hyphen (-)
when the task is not assigned to a team member?

[**View answer**](answers/answer-3.3.md)

**Exercise 3.4**

Add a row that lists all Service Instances (SIs) linked to each task.

[**View answer**](answers/answer-3.4.md)

## Going up the data hierarchy

You may have noticed in the exercise above, that within the `{{for service_instances}}` loop you refer to the name of each SI
by simply writing `{{:name}}`. Within the loop, the current SI is the 'data context', 
and within that context you only have direct access to the `{{:name}}` and `{{:id}}` of the current SI.

But what if you want to refer to the id of the current task instead, or the name of the recipient?  

There are several ways to do this, either by [accessing parent data](http://www.jsviews.com/#parentdata) or by going
all the way back [to the root](http://www.jsviews.com/#contextualparams@root) of the data.

Some examples:

* From within the `{{for service_instances}}` block, you can write `{{:#parent.id}}` to get the id of the current task.

* You can also name the current task explicitly, for example:

```
{{for tasks itemVar="~task"}}
...
  {{for service_instances}}
    {{:~task.id}}
  {{/for}}
...
{{/for}}
```

* You can write `{{:~root.change.subject}}` anywhere to display the subject of the Change.

**Exercise 3.5**

Display the current team member in bold (using the `<strong>` HTML tag) if it is the same as the recipient of the change summary.

Note: You can test this by assigning a task to the current user. For example, go to https://wdc.4me-demo.com/tasks/21357/edit
and assign it to Howard Tanner (of the Operations team). Next, generate a sample for Change #1673.

[**View answer**](answers/answer-3.5.md)

[Continue to the next chapter](4-the-printed-page.md).
