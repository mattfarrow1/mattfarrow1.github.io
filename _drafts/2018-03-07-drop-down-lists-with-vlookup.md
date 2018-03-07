---
layout: post
title:  Combining Drop-Down Lists with VLOOkUP
tags: [excel]
---

Responding to a question on Twitter, I was asked how to have an email address be automatically populated when a name was selected from a dropdown menu. 

{: .center}
![]({{ site.url }}/img/vlookup/1.jpg)

My answer was to use the VLOOKUP formula—which coincidentally I'd just covered last fall at our annual Apra North Texas conference. I'll write that presentation up at some point in the future.

I won't cover how to build a drop-down menu in this post, but [here is a link](https://support.office.com/en-us/article/create-a-drop-down-list-7693307a-59ef-400a-b769-c5402dce407b) to Microsoft support document detailing their creation.

### Building the Formula

I'll be using Excel for this post, but the same steps should work in Google Sheets.

Before we can get started, we need a reference list that contains all of the possible data that we might want to populate. In this example, let's set up an email address, hourly rate, and the contractor's state.

{: .center}
![]({{ site.url }}/img/vlookup/2.jpg)

This table could be somewhere on your main sheet, but I prefer to have it live on its own sheet and label it with something easy to remember such as "Reference." This isn't a sheet I'll be using very often so I'd prefer to have it out-of-sight (in fact, you could even hide the sheet once you have it populated.) 

Then, we can jump back over to main sheet that contains our drop-down menu. In the column where we want to populate the email address, we'll use a VLOOKUP formula in cell B2 to look at the name we selected from the drop-down and then go grab the appropriate email address.

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

What we're asking Excel to do in cell B2 is simply:
- Look at cell A1 and then go find that same exact value in the table on the Reference sheet somewhere in the range A1:D11.
- Once you've found that match, give me the value that is in column 2 on the Reference table (in this case, the email address.)

{: .center}
![]({{ site.url }}/img/vlookup/6.jpg)

Voila!

This looks like it will work perfectly. Now, if simply I copy and paste the formula down the list, something perhaps a little unintuitive will happen. (For this example, I've turned on "Show Formulas" for clarity.)

{: .center}
![]({{ site.url }}/img/vlookup/7.jpg)

Did you notice what happened?

The first part of the formula looks good; as we move down, we want Excel to shift down with us to look at each new name. However, in the second part of the formula — the one where we define the reference table — Excel has tried to help us by shifting the boundaries of the reference table down as well. Now the problem will become Excel won't be able to find the lookup value in the reference table.

This is happening because we wrote our formula using relative values, meaning Excel will try and shift them appropriately as we copy and paste them. In this case, we want the lookup range to shift down a row each time we copy it, but we never want the reference table to shift. 

The solution is to convert the reference table into what is known as an absolute value, meaning no matter what we do — don't ever change. To do that, we change:

`=VLOOKUP(A2,Reference!A1:D11,2,FALSE)`

Into:

`=VLOOKUP(A2,Reference!$A$1:$D$11,2,FALSE)`

{: .center}
![]({{ site.url }}/img/vlookup/8.jpg)

While this looks complicated, all we've done is told Excel, "Whenever you see a `$` sign, leave the following value alone, no matter what I do. 

Observant readers might wonder why I put `$` signs in front of both the letter and number and not one in front of the letter/number pairing. The answer is, we can get very granular about what we have Excel lock down for us. Excel will allow us to define the row, or the column or both values as absolute values depending on where you put the `$` signs.

In our example, we're using `A2` as our lookup value. Right now it works perfectly when we copy our formula down to the next row. But what about if we copied it to the next column over — say in the case of looking up the hourly rate?

Excel is going to again try and be helpful and will change `A2` to `B2` on you. We can solve this problem by updating our original formula to `$A2`. Now, Excel will always reference the cell in the first (`A`) column, but will shift down relatively as we copy the formula down the page from row 3 to 4 and so on. 

Let's go ahead and update our formula to populate the email address and hourly rate for all of our contractors and copy the formula down the length of our table.

{: .center}
![]({{ site.url }}/img/vlookup/10.jpg)

Well, that's not very pretty. 

### Combining Formulas

Although the structure of the table works, it isn't very visually pleasing to look at a long list of `#N/A` in cells where we haven't defined a contractor. Obviously, we won't be filling in every row on this sheet — we've left ourselves room based on how many contractors are working on this project. 

So how to get clean this up?

After thinking it over, I decided that the cleanest[^1] solution would be to wrap our `VLOOKUP` formula inside of an `IF` formula. An `IF` formula simply asks, "If this situation exists, then do `X`. If not, do `Y`."

`=IF(Logical Test, Value if True, Value if False)`

Now we can tell Excel, look at the column containing the name of the contractors. If that field is blank, don't do anything. If it isn't blank, execute our original `VLOOKUP`. Here's what that looks like:

`=IF($A2,="","",VLOOKUP($A2,Reference!$A$1:$D$11,2,FALSE))`

All I've done is inserted our previous `VLOOKUP` formula into the `IF` formula for the `Value if False`.

{: .center}
![]({{ site.url }}/img/vlookup/11.jpg)

Now our cells look blank if no contractor has been filled in, but as soon as we do, the remaining cells populate as well. 

{: .center}
![]({{ site.url }}/img/vlookup/12.jpg)

{: .center}
![]({{ site.url }}/img/vlookup/13.jpg)

{: .center}
![]({{ site.url }}/img/vlookup/14.jpg)

At the end of the day, this is a niche project, but a good reminder of the power behind spreadsheet programs like Microsoft Excel. 

[^1]: You might disagree with my use of the adjective "cleanest" here, but in my mind, I'm thinking about the end result, not the complex formula. 