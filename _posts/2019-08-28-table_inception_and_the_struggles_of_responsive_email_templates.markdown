---
layout: post
title:      "Table Inception and the struggles of responsive email templates"
date:       2019-08-28 15:13:19 -0400
permalink:  table_inception_and_the_struggles_of_responsive_email_templates
---


The other day I was tasked with creating a responsive email template for one of our clients. At that time, if the email was opened on a phone, it was just scaled down to fit on the screen making the banners and text very small. Not the best user experience. 

Initially, I figured this was no big deal, just throw some media queries in and call it good. Then I started looking at the template code... 
It was table nested inside table nested inside table, I could hardly make sense of it. Plus, all of the styling was done inline -- WHAT?! Who wrote this?! What is this madness?!

![](https://media.giphy.com/media/9PviGIUMJeJtVPrT1u/giphy.gif)

I was immediately on a mission to rewrite the whole thing, but not before I asked my boss who had created this monstrosity. That's when I learned... unfortunately, this is more-or-less how email templates need to be written in order to be properly read by all of the different email clients.

![](https://media.giphy.com/media/jlbYyYfKpwRDG/giphy.gif)

He then pointed me to our [Litmus](https://litmus.com/) account, this site lets you build out your template and then see how it displays on all of the different email clients on desktop, Android and iOS. I quickly became aware of how finicky they all are. At first, I tried using one of Litmus' templates and just editing it to fit my needs, but this didn't work. Even though it showed up great on the Litmus previews, when I actually sent it to myself to test on my device, simple CSS properties like 'color' weren't working and nothing was even close to responsive. 

I started digging around even more on the internet, turns out Gmail doesn't respond to media queries, cool. Also, a lot of email clients only use inline styling -- so all the pretty CSS I had written now had to bed split up and embedding into all my elements. Thankfully, I was able to find this [awesome inliner tool ](https://www.campaignmonitor.com/resources/tools/css-inliner/) to do all that hard work for me. 

After several more failed attempts, I was starting to believe we couldn't make responsive email templates -- which is also ridiculous because I open them up every day on my phone. 

![](https://media.giphy.com/media/l2JdSg1IVUWEYEM9i/giphy.gif)

Finally, I read about the fluid-hybrid method (also called the spongy method). This is a design that uses a mix of percentages and max-width to create a fluid design without using media queries. Basically how it works is, anything that typically would use a media query to be resized, give it a width of 100% but also set a max-width so you're never looking at anything bigger than your screen. 

For a one-column layout, you may want to set your max-width to 600px, for a two-column layout maybe you set each content area to have a max-width of 300px. What this does is if you have a screen that is >600px, both of your content areas will fit perfectly beside each other. Once your screen size goes down to 599px and lower, your content areas will now stack on top of each other and each take up the entire width of the screen. It seems so simple, doesn't it? Well, there's more...

Outlook doesn't like to play nice, so you also need to have some conditional CSS to force it to collapse borders on all tables to prevent unwanted gaps. Inside of the conditional Outlook table, you will create an 'outer' table that will have a width:100% max-width:600px set to it. Inside your 'outer' table you can then create a new row for each main section of your template. Inside of each row you will again have to create a new cell containing a new table and set all of their widths. To see a great example of how this works, check out this amazing [tutorial](https://webdesign.tutsplus.com/tutorials/creating-a-future-proof-responsive-email-without-media-queries--cms-23919) on how to build all sorts of email layouts. 

After you make your layout and style it how you want, it is good to go back in and add some media queries, that way the clients that use them can do so seamlessly. 

Once you have added the media queries, throw all of your code into the inliner tool mentioned above and then put that into Litmus to see your final results. There may still be some tweaking here and there that needs to be done, some very simple CSS properties like padding and background-color don't work or are a bit buggy in some email clients, so you may need to have other options in those cases. You can use this [checklist](https://www.campaignmonitor.com/css/) to see what properties work in each client.

All-in-all what I've learned from this experience is that responsive email templates are a pain but they can be done. Fluid-hybrid method to the rescue!

![](https://media.giphy.com/media/g4eOulPFxnIEE/giphy.gif)



