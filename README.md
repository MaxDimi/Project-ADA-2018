# Analysing IRA Tweets 

Sub-Subject : 
-------------

## => Influence  of  Russian  trolls on American elections

# Abstract
Among the enormous volume of tweets exchanged during the 2016 US presidential election campaign, millions were sent by alleged Russian troll accounts. Those accounts have been accused of manipulating the campaign and its outcome.

Given how dramatic and dangerous the consequences of a country influencing the democratic process of another can be, we want to get a better insight on the methods and the real effects of the trolls.

On one side, we will compare their activities with the evolution of popularity of the candidates along the campaign. We will also take a look at the major events of the election and determine if they were influenced by the trolls and vice-versa.

On the other side, we will study the methods employed by the Russians to disrupt the presidential election. We will examine their vocabulary, the subjects they discuss as well as the media and people they refer to.


# Research questions
* Is there a relation between the candidates popularities and the activities of the trolls?
* Did the trolls influence the major events of the campaign? Is it the other way around?
* Which subjects are discussed by the trolls, and which semantics do they use?
* Which media do they tend to talk about and link in their posts?
* Do they tend to show direct support or hatred for specific people?
* Did the strategy of the trolls change over time?

# Dataset
The main dataset we are going to use for this project is the [Russian and Iranian Troll Tweets](https://drive.google.com/open?id=1GBsVXYvPrGcYI-wR4mWGO39fly1TMqjO) dataset from [Twitter](https://about.twitter.com/en_us/values/elections-integrity.html#data). It contains over 10 million tweets of accounts associated with IRA and Iranian trolls. It gives information about the account itself (Twitter handle, number of followers and following, account preferences...), and about the individual tweet (content, date and time of publication, type of post, number of retweets...).

Regarding the popularities of the candidates, we have identified an important amount of possible data source on [realclearpolitics.com](https://www.realclearpolitics.com/epolls/latest_polls/president/#). Finding the relevant and useable data is part of our future milestones. [Some websites](https://cesrusc.org/election/) propose their election forecast in csv format, making it easy for us to deal with it.

We can also take a look at the events after the campaign, with for example the evolution of the approval rate of Donald Trump proposed by [FiveFirtyEight](https://projects.fivethirtyeight.com/trump-approval-ratings/?ex_cid=rrpromo).

Finally, for the timeline of the campaign and its major events, [Wikipedia](https://en.wikipedia.org/wiki/United_States_presidential_election,_2016_timeline) has a lot of information.

_____________________________________________________________________________________________________________________________________

# A list of internal milestones up until project milestone 2
* Identify and gather relevant and useful data.
* Take a first look at those data and get an idea of their size, representation, basic statistics, missing values...
* Decide which tools are the best suited for our project.
* Clean the data and reduce them into smaller dataframes containing the relevant information.
* Read studies that have already been conducted on our subject.
* Adapt the orientation of our project and our milestones according to our findings 
  (-> A list of internal milestones up until project milestone 3)

# Questions for TAs
* What do you think of the scope of our project? Should we restrict/broaden it?
* What if we arrive at the conclusion that the Russian trolls did not have a significant impact on the election? Is the social aspect of the project sufficient?

# What have we done for milestone 2 ?
* Every of our previous objective is met.
* We've already covered part of our questions in the last Jupyter Notebook handed over : at least we've dug far enough into our datasets to get some elements of answer(s).
* While doing the work for milestone 2 we've noticed that extra studies were to be read in order to really tackle the roots of our questions
* We came up with new courses of actions to answer our questions : i.e. try to catch the spread of the tweets (and their retweets) in the world (mostly in america we guess) to see how does the trolls move and which part of the population is likely to be reached by such troll tweets.
* Different type of pre-analysis : semantic/textual (words, hashtags, languages), retweets quantity, support vs. hate. We also started the automatisation of the translating task (see below).

# What are the objectives after milestone 2 ?
Here below, we state whether or not we think our initial objectives can be fulfilled in a satisfactory manner : 
- Questions 1. and 2. YES : Trends, approval votes, polls are available on the internet (csv files or web scrapping) and the variety of data we have is enough to comment with significance about underlaying links between troll tweets and events/intentions of votes during the campaign. One bottleneck will be to find out (if there's any relationship between troll tweets and campaign's events) if trolls did impact the campaign or did the campaign intefere with casual troll tweets (that maybe existed way before and in the same fashion). 
- Questions 3. , 4. and 5.  YES : We have full access to trolls contents'. Nevertheless there exist many tweets not in english. To address this difficulty we've already set up some automatisatic language processing in order to translate. Once the translation is done, it's quite easy to compute several measures of similarity, correlations ... etc with 'group by' statements.
- Question 6. maybe NO : We can't tell for now. We first have to answer questions 1) to 5) to see if there's really a strategy that's hiding behind troll tweets.
_____________________________________________________________________________________________________________________________________

# A list of internal milestones up until project milestone 3
* Enrich the datasets we were provided with the data structures one can find by pursuing the url links mentionned above (Dataset) ;     it requires us to either find a direct download
link or to perform web scrapping . We must embed a visualization of the presidential campaign and its major events. We also have to load the approval rates for Donald Trump and Hillary Clinton. 
* Now that we have a far better knowledge of our datasets we can build statistical tests, run them and interprate them.
* We need to filter out some non-relevant tweets that are not likely to drive the elections on one side or another.
* We have to create a timeline wherein the flow of relevant trolls is presented side by side with the timeline of events :              a first interpretation of the global traffic of the identified trolls has been done in milestone 2 and seems to corroborate a strange correlation between the number of trolls tweets and big events during the campaign. 
* Tackle every question while adopting a critical point of view. 
* Create user-friendly visualizations that are easy to read.

# Questions for TAs
* Are you aware of the way our provided dataset (from Ada's course, Twitter Project on Mattemost) was built ? 
Which filter did GoogleAPI's use in order to detect troll accounts/ troll tweets and how did they manage to collect all those records?

_____________________________________________________________________________________________________________________________________

# What have we done for milestone 3 ?

* Temporal Analysis : Global / Time Window

This part mostly consisted in 

* Time Slicing : we detected several time windows wherein the activity of IRA's trolls differ both in volume and content

* Events Matching : we spotted many correlations between peaks of political troll tweets and political events that happened around the world during 2009-2018.  

* Evolution of Support : with the help of our Sentimental Analysis (see below) we managed to introduce sentimental "deltas" (weekly) to assess the support (globally positive/negative) for US candidates during the campaign period. 
    
* Textual Analysis :

This part mostly consisted in 

* Sentimental Analysis : with two different approaches we implemented the 'sentimental' scan of tweets' contents and classify a tweet as positive / negative for either Trump, Clinton or Obama. 

* Words and Hashtags used in Tweets : we analyzed the most frequents words / hashtages used in troll tweets and compared them with the most common words / hashtags used in general on Twitter

* Tweets Translation : we translated several tweets whose contents were in russian in order to get an insight for them. 
    
* Retweets Analysis / URLS in Tweets  :

This part mostly consisted in 

* Users Interactions by Retweets : we analyzed the links (by retweets analysis) that existed between troll accounts ; that lead to clusters and interpretations about IRA's troll farm.

* URLS : what are the urls / medias used by troll accounts
    
 Finally we interested ourselves about the differences between english / russian troll accounts structures. 
 
                
 ====> Link to our DataStory : https://abaracadacabara.github.io <=====
                            
  
# ROLES :
---------

Every team member did perform several analysis, wrote code and sought after informations (events timelines, typical distributions
of tweets' words/hashtags ... etc) on the Internet. 

Nevertheless we can distinguish the effort of everyone by the following work classification :

* Henri Moumal : JavaScript of DataStory, Textual Analysis , Merge Notebooks, DataStory
* Guillaume Van Dessel : Temporal Analysis, Textual Analysis, Tweets' content, Timeline researchs, Interpretation of the data.
* Maxime Dimidschstein : Wrangling / Cleaning the Data, URLS , Retweets Analysis and between Users links.

# CONCLUSION :
--------------

To conclude, what our analysis pointed out was the fact that there are many and many things one adventurous mind could say 
while performing classical data analysis on IRA's tweets dataset. As mentionned in both our Jupyter Notebook and DataStory, we lack of the so called *21st century fuel* : **data** . Mostly data about the effects of an (over)exposure to fake news/trolls on the opinion of people. Such informations sometimes exist but are either non-free or incomplete. After realizing the impossibility of totally fulfilling the original requirements (by this we mean : answering ***all*** our initial questions) we started to think differently. We managed to discover as many as possible pieces of evidence, traces of possible inferences of IRA's trollers. 

At the end of the day what we would like to underline is the correct identification of the troll accounts : our analysis showed so many correlations and confounding events that we can hardly say that those accounts were not willing to spread misinformation towards the internet (here through Twitter).  

Here are, for each analysis, the facts one can bring home : 

- The temporal analysis showed that the volume of activity of the trollers matches very well mediatic (political) events ; especially 
regarding US 2016 presidential elections and Crimean's armed  conflict (Donbass' war). 

- Textual analysis shed light on the fact that trollers tend to use a vocabulary that is, in general, more *negative*. Their favourite word is *Trump* ! 

- Russian speaking accounts interact more between each other and focus on spreading messages from their government's news media. Meanwhile, English speaking accounts look more casual, and manage to get retweeted more frequently.

This concludes a gigantic project that taught us what is the job of a data scientist ; its difficulties but also its pleasures that are to discover hidden patterns and have better understanding of the world !
