---
layout: post
title:  Combining Drop-Down Lists with VLOOKUP
tags: [excel]
---

I saw a question on Twitter about whether someone could, in Google Sheets, have a sheet auto-populate information based on a name that was chosen from a drop-down menu. In this case, the request was to have an email address automatically populate, but this could work for any piece of data. 

{: .center}
![]({{ site.url }}/img/vlookup/1.jpg)

My suggestion was to use the VLOOKUP formula—which coincidentally I'd just covered last fall at our annual Apra North Texas conference. I'll write that presentation up at some point in the future.

I won't cover how to build a drop-down menu in this post, but [here is a link](https://support.office.com/en-us/article/create-a-drop-down-list-7693307a-59ef-400a-b769-c5402dce407b) to a Microsoft support document detailing their creation.

### Building the Formula

I'll be using Excel for this post, but the same steps work in Google Sheets.

Before we can get started, we need a reference list that contains all of the possible data that we might want to populate. In this example, let's set up an email address, hourly rate, and the contractor's state.

{: .center}
![]({{ site.url }}/img/vlookup/2.jpg)

This table could be somewhere on your main sheet, but I prefer to have it live on its own sheet and label it with something easy to remember such as "Reference." This isn't a sheet I'll be using very often so I'd prefer to have it out-of-sight — in fact, you could even hide the sheet once you have everything working so you don't accidentally modify the data. 

Once the reference sheet is built, we can jump back over to the sheet that contains our drop-down menu. In column `B` where we want to populate the email address, we'll use a VLOOKUP formula in cell `B2` to look at the name we selected from the drop-down (Guillermo in this example) and then go grab the appropriate email address.

{: .center}
![]({{ site.url }}/img/vlookup/3.jpg)

The structure for the VLOOKUP formula is as follows:

`=VLOOKUP(Value we want to match, Range to look for that value, Column to return, whether the match should be exact or not)`

{: .center}
![]({{ site.url }}/img/vlookup/4.jpg)

In this example, our formula will read as follows:

`=VLOOKUP(A2,Reference!A1:D11,2,FALSE)`

{: .center}
![]({{ site.url }}/img/vlookup/5.jpg)

What we're asking Excel to do in cell `B2` is simply:
- Look at cell `A2` which, in this case, lists the name "Guillermo" and then go find that same name in the table on the Reference sheet somewhere in the range `A1:D11`. The `false` at the end of the formula tells Excel that we want an exact match to the name, not an approximate match.
- Once you've found a match, give me the value that is in column 2 on the Reference table (in this case, the email address.)

{: .center}
![]({{ site.url }}/img/vlookup/6.jpg)

Voila!

This looks like it will work perfectly. Now, if simply I copy and paste the formula down the three examples, something that may seem a little unintuitive will happen. (For this example, I've turned on "Show Formulas" for clarity.)

{: .center}
![]({{ site.url }}/img/vlookup/7.jpg)

Did you notice what happened?

The first part of the formula that looks for the name looks good; as we move down, we want Excel to shift down with us to look at each new name. However, in the second part of the formula — the one where we define the reference table — Excel has tried to help us by shifting the boundaries of the reference table down as well. This means that at some point, Excel won't be able to find the lookup value in the reference table because it is looking in the wrong spot.

This is happening because we wrote our formula using relative values, meaning Excel will try and shift them appropriately as we copy and paste them. In this case, we want the lookup range to shift down a row each time we copy it, but we never want the reference table to shift. 

The solution is to convert the reference table into what is known as an absolute value, meaning no matter what where we copy the formula — don't ever change where you're looking. To do that, we change:

`=VLOOKUP(A2,Reference!A1:D11,2,FALSE)`

Into:

`=VLOOKUP(A2,Reference!$A$1:$D$11,2,FALSE)`

{: .center}
![]({{ site.url }}/img/vlookup/8.jpg)

While this looks complicated, all we've done is told Excel, "Whenever you see a `$` sign, leave the following value alone, no matter what I do. 

Observant readers might wonder why I put `$` signs in front of both the letter and number and not just one in front of the letter/number pairing. Excel allows us to get very granular about what is locked down — just the row, just the column or both the row and column — depending on where you put the `$` signs.

In our example, we're still using `A2` as our lookup value which works if we're just copying our formula down to the next row. But what if we copied it to  column `C` to calculate the hourly rate?

Excel is going to again try and be helpful and will change `A2` to `B2` on you. We can solve this problem by updating our original formula to `$A2`. Now, Excel will always reference the cell in the first (`A`) column, but will shift down relatively as we copy the formula down the page from row 3 to 4 and so on. 

Let's go ahead and update our formula to populate the email address and hourly rate for all of our contractors and copy the formula down the length of our table.

{: .center}
![]({{ site.url }}/img/vlookup/10.jpg)

Well, that's not very pretty. 

Although the structure of the table works, it isn't very visually pleasing to look at a long list of `#N/A` cells where we haven't defined a contractor. Obviously, we won't be filling in every row on this sheet — we've left ourselves room based on how many contractors are working on this project. 

So how do we clean this up?

### Combining Formulas

After thinking it over, I decided that the cleanest[^1] solution would be to wrap our `VLOOKUP` formula inside of an `IF` formula. An `IF` formula simply asks, "If this situation exists, then do `X`. If not, do `Y`."

`=IF(Logical Test, Value if True, Value if False)`

Now we can tell Excel, "Look at the column containing the name of the contractors. If that field is blank, don't do anything. If it isn't blank, execute our original `VLOOKUP`." Here's what that looks like:

`=IF($A2,="","",VLOOKUP($A2,Reference!$A$1:$D$11,2,FALSE))`

All I've done is inserted our previous `VLOOKUP` formula into the `IF` formula for the `Value if False`.

{: .center}
![]({{ site.url }}/img/vlookup/11.jpg)

{: .center}
![]({{ site.url }}/img/vlookup/12.jpg)

Now our cells look blank if no contractor has been filled in, but as soon as we do, the remaining cells populate as well. 

{: .center}
![]({{ site.url }}/img/vlookup/13.jpg)

{: .center}
![]({{ site.url }}/img/vlookup/14.jpg)

At the end of the day, this is a niche project, but a good reminder of the power behind spreadsheet programs like Microsoft Excel. 

[^1]: You might disagree with my use of the adjective "cleanest" here, but in my mind, I'm thinking about the end result, not the complex formula. 