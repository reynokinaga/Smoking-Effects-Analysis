Data Exploration Assignment
In this group project, you will be:

1. Finding and downloading a data set.
2. Exploring that data set
3. Coming up with an interesting story to tell using that data (and figuring out who your audience is to tell it to). The story should help us learn how the world works, or provide actionable recommendations that the chosen audience can use
4. Developing a data dashboard
5. Developing a memo
6. Doing a presentation of your data, story, and dashboard

The dashboard and memo should stand on their own; it shouldn’t be necessary to hear the presentation (or the other one of memo/dashboard) to get the story from them. All three main elements (dashboard, memo, presentation) will be trying to get across the same main story but from different directions. You may reuse visuals between the dashboard and memo, but they aren’t required to be the exact same.

Finding a Data Set
You can use whatever data set you want! However, I have two recommendations of good places to look.

Kaggle Dataets
I highly recommend looking at Kaggle Datasets (you will need an account to download anything). Kaggle is a site designed to help teach machine learning, and people post all sorts of interesting data sets on their site.

Search through the available data sets, and click on them to get more information. It should give you information about the variables in the data, information about that data, and some sample rows, so you can start brainstorming what you might do with the data before having to download it.

<img width="1142" height="576" alt="image" src="https://github.com/user-attachments/assets/205c651f-59c5-4e42-aa39-2ce559fe11af" />

Example of Kaggle Dataset

Do be aware that a lot of the data sets on Kaggle are not suitable - for example, the many many data sets of images to be used for training image-classification algorithms (I guess you could use those if you wanted, but you’d better be a ML image processing whiz!). So you may have to try a few options. Be sure it has the variables you want!

Most Kaggle datasets are CSV files, which can be read directly into Excel, R (read_csv() in the tidyverse), or Tableau (“Text File”). Some are JSON files, which can be read into R (readJSON() in rjson, see this guide) or Tableau (“JSON File”). Others are SQL, which is tougher for R but still possible (see this guide for R), and there’s a direct option for it in Tableau.

IPUMS
For something a little more “standard”, with plenty of microdata about people’s earnings and work, family structure, etc. etc., check out IPUMS, and in particular I would point you towards IPUMS CPS, which has data from the Current Population Survey, a monthly survey performed by the Bureau of Labor Statistics that is used to calculate trends in employment and the general health of the labor market, among other things. You will need to create an IPUMS account to download anything.

Once there, you will want to “Get Data”


IPUMS intro page

Then, you’ll need to “Select Samples” to pick the years and months of data you want (be aware - too many samples and the file can get really really big!), and you can select variables from the dropdown menus, and click the + icon to put it in your “Cart”. Be sure to click the variable names to read their documentation before using them.

When it comes to samples, there are two main kinds - the ASEC (Annual Social and Economic Supplement) is only given in March, and is a more extensive set of questions relating to earnings and some other features. The other kind is the standard CPS monthly file, which contains less information but comes out every month.


IPUMS sample and variable

Once you have your samples and variables, click on View Cart and then Create Extract. On this page you can filter your data using SELECT CASES. You can also attach characteristics using ATTACH CHARACTERISTICS (for example, if you want “education of this person’s mother” (who they live with) instead of “their own education” you can do that here).

You can also change the “Data Format,” which I recommend doing. If you are going to port it directly into Excel, I recommend making it a CSV. If you are going to open it in R (either to work in R or do some processing first), I recommend the “Stata” format, which can then be read into R using read_dta() in the haven package. If you are going directly into Tableau, I recommend the SAS format, which can be imported into Tableau as a “Statistical File”.

Exploring that Data Set
Look around! Use our tools from EDA to make some initial calculations and graphs, see what kind of story you can tell.

You and your group should work together to plan out a story and the kinds of visualizations you’ll be using to tell that story.

Your story doesn’t necessarily have to have business implications, but if it does that will probably be better preparation for you!

Developing a Data Dashboard
Use R flexdashboard (Shiny optional) or Tableau to develop a data dashboard that effectively tells the story. There’s no requirement on the number of visualizations, but it should be enough to effectively get the point across, and give you something to talk about for 15 minutes.

Keep in mind:

The story you’re trying to tell is central. Don’t just throw a bunch of stuff on a dashboard
Each individual visualization should get attention and be well-designed and make sense. No Tableau bubble charts I beg you
Using Tableau is fine, but if you pick Tableau because it’s “the easy option” that doesn’t bode well for your project. Tableau visuals need plenty of work, thought, and care to be as effective as possible too!
Unless you have a good reason to do so (say, taking advantage of similar structure to get across a complex idea easily, or you have one giant super-detailed and explorable visualization that covers the whole thing), vary the kinds of visualizations on your dashboard. If I see a wall of bar graphs I’m gonna tune out, as would any other viewer
Interactivity of some sort on a dashboard is usually what people expect. It’s not required for the assignment, but think carefully about how it might help. But don’t add interaction that doesn’t help tell the story! That can just be distracting.
Presentation
Prepare a 15-20 minute presentation targeted at a non-technical audience (i.e. very little stats knowledge. They probably know what an “average” is). You can use some slides if you like, but generally you will be presenting your dashboard directly.

20 minutes is a hard cutoff. I will stop you after 20 minutes and anything you haven’t said yet won’t count! And 20 minutes is a maximum, not a target - shorter is perfectly fine.

You don’t all have to present, and there are no bonus points for being a presenter. You could just have one or two people do all the actual presenting (although I’d expect everyone else would be contributing to preparing the presentation). Or you could have everyone take turns if you want. Up to you.

Things to address:

What your data is and where it comes from
What your story is
How you set out to tell that story, and what interesting question it answers
Walk us through the results on your dashboard and explain how they relate to your story
Give the audience a sense of what they are learning about the world, or what useful things they can do with the actionable recommendations you provide
Memo
Prepare an RMarkdown knitted HTML document containing text and data (i.e. visuals and tables). It should be roughly two pages of text not counting the visuals (I say roughly because HTML doesn’t have page numbers - you can copy/paste everything to Word or do output: word_document to get a pagecount)

You can imagine this memo going to the same audience you’re targeting your presentation to. It should be very clearly written for a non-technical reader (how non-technical? If you use, say, the term “statistically significant” you’d better clearly explain what you mean, and anything beyond that you’re gonna have to work for it!).

The writing and visuals should go together - your writing can spend time explaining how you can get from the results you see to actual useful information.

The final paragraph of your memo should very explicitly say what the key takeaways from your memo are - what are the recommendations, and/or what have we learned about how the world works?

Common Pitfalls
These apply to both the presentation and memo:

Are your recommendations actually actionable? For example, if the recommendation following “We found that sales for Kellogg cereal brands were higher than for Post cereal brands” is “so we recommend Post try to increase sales” that’s not very helpful - did they really need you to figure out that higher sales would be good? Or, if the recommendation following “interest was highest around the Super Bowl” is “so try to have a second Super Bowl each year” that’s not helpful either - they can’t do that.
Along those lines, while I don’t expect you to do data work that formally separates correlation from causation (that’s hard!), I do expect you to put a little thought into whether your conclusions are likely to be confusing correlation and causation. For example, if the recommendation following “we found that people who camped out for a ticket to the music festival bought more merch at the festival” is “so we recommend slowing down the ticket booth so more people have to camp out” that’s not helpful - those people probably were willing to wait and also bought merch because they’re hardcore fans (correlation) but you’re assuming a causal interpretation that you can’t really support with your data (waiting causes more merch sales)
Don’t waste a lot of time explaining how you cleaned the data or walking us through code - very rarely does the audience care
Give your audience a bucket to put information in! Before describing a visualization, help us contextualize what we’re about to see and give us an obvious reason why we’d want to know what you’re going to tell us.
Grading
15% Coherent and well-supported story/recommendatoins
30% Visualization quality (in dashboard and memo)
5% Layout and interactivity of dashboard
20% Clear and compelling presentation
20% Clearly written and compelling memo
10% Peer review
With rare exception, every person in your group will get the same grade on everything except the peer review. Those rare exceptions largely consist of close variants of “your groupmates all tell me you didn’t do any work” in which case you will probably get a 0.

If you are in a group where one of your groupmates is totally checked out and not helping, let me know about it as soon as possible. I’d rather not have to hear about it for the first time on the peer review forms.

Peer Review
For the peer review, you will have 9 points per groupmate to confidentially allocate among your groupmates. Each point is worth 1 percentage point of the assignment grade. It is possible to get a better-than-perfect peer review score.
