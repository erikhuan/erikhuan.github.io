---
layout: essay
type: essay
title: "Meteor Gotchas"
date: 2017-03-09
labels:
  - Software Engineering
  - Meteor
---

## Creating Meteor Projects

As with any typical Meteor project we must first go to our command line, find the file we want to create the project in, and then type 'meteor create filename'. Usually this runs with no problem. Following up we need to go in the file we just created and then type 'meteor npm install'. Depending on how you want the project setup you may want have some settings already planned for it. When install these files on Windows 10 your firewall might actually be blocking the install and thus you'll just be sitting there wondering what's happening. If you stay on the command line window you may get a popup from your firewall asking to grant access. Say yes and everything should be fine from there.

## Meteor and Semantic UI

If you are like me and just recently started learning Semantic UI, you will probably realize that a lot of your HTML tags are going to be mainly divs. When coding with Meteor, specifically in Intellij, this poses some problems. Normally if you wanted to declare say a form with Semantic UI you could type,

```
<div class="ui form">
  <div class="field">
    <label>User Input</label>
    <input type="text">
  </div>
  <div class="ui button" type="submit">Submit</div>
</div>
```

And poof, you have an input field and a submit button right underneath it. However, Meteor needs us to give it specific tags so our corresponding Javascript files will work with our HTML page. If we gave it the code above our page will only have the appearance of a form but not the functionality of one. Instead we need to properly declare the tags as such,

```
<form class="ui form">
  <div class="field">
    <label>User Input</label>
    <input type="text">
  </div>
  <button class="ui button" type="submit">Submit</button>
</form>
```

I learned this the hard way... After finishing my webpage I tried to test it by inputing some data and submitting it, but nothing happened. I was stuck there for the longest time figuring out why nothing worked when I followed some example code from the Semantic UI website. It was only until after I asked for help did someone point out that I needed to declare my submit button with the button tags. On <a href="http://semantic-ui.com/collections/form.html">Semantic UI's Form</a> website page, the first example is using button tags, but all other examples afterwards use div tags. I found this odd since I was trying to learn Semantic UI and the examples themselves were actually slightly misleading.