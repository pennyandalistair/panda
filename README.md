# panda

This is the repository for our wedding website. We used Hugo and the creative theme, adding in a google form for RSVP and google maps to highlight the venue and hotel.

Hugo: http://gohugo.io/

Creative theme: https://github.com/digitalcraftsman/hugo-creative-theme

# Embedded Google form

It was a bit tricky to get the embedded google form to work nicely. The relevant code is in the `aside.html` layout file in the creative theme folder directly: /themes/creative/layouts/partials/aside.html

The steps were:

1. Create a Google form with all the elements you would like
2. Update the `aside.html` page to link to this form
3. Update the elements in the `aside.html` page to have the same `name` values as in the google form

After creating the form, copy the "form response" version of the link:

![Google Form link](/etc/ss3.png?raw=true "Form response link of Google form")

This needs to be placed in the `aside.html` file on line 12: https://github.com/pennyandalistair/panda/blob/434078be5203095df70c663592b99b74bb08bae3/themes/creative/layouts/partials/aside.html#L12

You may also need to update the `id` on the same line.

Next, each individual element needs to be updated. Let's look at my google form:

![Example Google Form](/etc/ss1.png?raw=true "Example Google Form being inspected")

In particular, you can see that the "Your Name" input box has `name="entry.751649853"`. When we are editing `aside.html`, we need to ensure that this is input box is named the same thing:

![Example code for "Your Name"](/etc/ss2.png?raw=true "Example code matching the Google form")

That should get you up and running!
