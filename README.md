# Who Are We Celebrating In The Streets Of NYC?

## Introduction

Hello! My name is Anusha Subramanian and I'm a Data Journalist at Columbia Journalism School. I'm primarily interested in anything 
that provides critical commentary on the human condition and specifically interested in public health, culture with a South Asian focus, 
education and lots and lots of food. You can find my work [here](https://anusha0712.github.io) and this project's 
completed story [here](https://anusha0712.github.io/deplatforming/).

Universities and higher education institutions are hot beds of political activism, especially the fight for free speech. It's where a lot of change is conceptualized, accountability is 
demanded and young idealism stands strong in the face of cynicism. However, political activism and censorship attempts have historically grown together
and college campuses are no exception. The rhetoric of free speech has always existed along side the discussion of whether certain views "deserve"
the platform to be expressed. This was the impetus for this project.

Freedom of Individual Rights and Expression, a nonpartisan advocacy organization released the "Campus Deplatforming Database" in 2024, 
cataloging incidents of attempted and successful censorship of access to public events on college campuses. "Deplatforming" is a specific form of 
censorship that takes place when an ideology is denied access to a platform to express it's views. This includes incidents such as speakers being disinvited, 
commencement speakers being changed, plays, musical performances and art exhibits being cancelled or postponed or protestors disrupting speakers or events.
Deplatoforming does not include expression dissent or peaceful student protests. 

You can explore the database [here](https://www.thefire.org/research-learn/campus-deplatforming-database). It contains a log of deplatforming events on campus from 1998 to 2025. It's updated regularly by FIRE and while the methodology says that the incidents are self-reported, the reality is that FIRE staffers gather most of these through media reports, 
letters to campuses and student reports. FIRE also employs full fact-checking and independent verification procedures before the incident makes it into the database. 

## Goals

My goal is to analyze cases of campus deplatforming events over the years and learn more about how censorship has changed across higher education institutions. 

Some questions that guided my exploratory data analysis were:

1. Has censorship grown over the years? 

2. Has there been an uptick in certain topics? 

3. Is the Right of Left attempting to censor more? 
    - who is more successful in their attempts?

4. In what situations does the campus administration reinvite/relocate of offer remediation after a censorship attempt?

In these times, when our First Amendment rights are constantly under threat and ideals of free speech don't mean what they used to, I believe that
such a database and project will offer valuable insight into our political climate. For this project, the main aim is to practice my dynamic scraping skills, 
collate a valuable database in an analyzable form and extract valuable insights from it. The context of the database, implication of censorship
and the added dimensions of "who protested what" adds a layer of complexity in data analysis. I want to focus on clear but depthy reader-facing visuals.


## Frameworks Used

**Code**
- Python (pandas)
- Scraping (BeautifulSoup, Playwright) 
- Google Sheets

**Data Visualization**
- [Datawrapper](https://www.datawrapper.de)
- Adobe Illustrator
- ai2html


## Quick Guide To The Files

1. `data` directory: Contains all the main files required for analysis 
    - `campus_deplatforming_analysis.csv` : raw data files
2. `campus_deplatforming_analysis.ipynb` : main ipynb for analysis 
3. `campus_deplatforming_scraping.ipynb` : main ipynb for scraping the database 
4. `pages` directory: contains the HTML from each clickable iteration of the embedded table     
5. `visuals` directory:
    - contains all the main visuals used in the project


## Methodology 

Here is the framework that I followed for my analysis. The code notebook contains more detailed commentary for the individual steps.

1. Scraping the embedded table on FIRE's website using Playwright.
    - I clicked through 69 pages of the table using playwright and saved the HTML of each one separately 
    - Used BeautifulSoup to scrape each page and add it to a dataframe
    - Used the url in "details" to scrape more detailed metadata about each campus deplatforming incident


2. Clean and Standardise Data. Few of the steps include:
    - The data required a lot of standardization. 
    
    - Manually added a "State" column to untangle geographical patterns in censorship (or maybe electoral ones?)
    - A lot of topics were encoding with wrong spellings. Those needed to be corrected

    - Most deplatforming incidents were encoded as multiple topics. For example, "Gender, Sexuality, Race". 
    Those needed to be split into lists and exploded so that I can count them accurately.

    - Some data was also missing. The political motives of around 100 rows were missing. "Not applicable" was used as a sort of catch-all term and I had to go through every case to understand why it was encoded that way. 

    - I created a "successful_censorship" column to encode whether the deplatforming attempt was successful in getting the event censored or not.

    
3. Grouping, Counting and Pivoting data for analysis and visualization

4. Visualization:
    
    - Datawrapper graphs were embedded directly into the HTML
    - ai2html was used to make the visuals responsive

6. Coded a narrative storytelling template using an HTML and CSS framework.


## Limitations - "Wants" vs "Needs"

I had a harder time with this project than I anticipated. Part of it was pressure to draw accurate conclusions without bias and truly try to talk to the data and listen to what it is saying. 
Part of it was because of the counterintuitive structural nature the database. For example, "political_motives_source" being "From the Left" meant that the Left was the side attempting the deplatforming, 
which means that it was the right that was being censored. It was also important to keep in mind that these incidents were about censorship and right to free speech, without letting my own political leanings dictate my analysis.

Furthermore, in this particular database, raw counts tell you very little without looking into the actual description of the event - who is the censorship against, what they stand for, what action was taken, how did the University respond etc.
Take the example of controversial topics. The left attempted to censor events related to race 312 times and the right did the same 59 times. Simply drawing that conclusion means nothing and seems misrepresentative because
both parties tried to censor very different approaches to race. That is the kind of analysis I have gone into more depth for my story - the nuances of who the two sides thought didn't deserve a platform to propagate their views. 

I was able to accomplish everything I "needed", which included collating the database and analysing trends in censorship.

Given the time, I would have really liked to use machine learning algorithms of text-analysis to model topics over the years and how they have changed. For example, how has censorship around the very broad topic of race or gender changed from 1998 to now? 
Are we still trying to censor the same views or has that changed? How has university response changed over the years? Are they more or less likely to cave to censorship against certain types of subtopics within broadly contentious issues?


### Limitation

The biggest limitation of this dataset is that it is a severe undercount of the number of campus deplatforming attempts. FIRE's methodology also notes that 
this is an extremely conservative estimate. Some events were missing data about who instigated the censorship attempt and what the response was. 


## Note on AI use

ChatGPT was used in this project, primarily to help quickly assign the State where each incident took place based on the University location. I went through the database after ChatGPT was done and conducted extensive sanity
 checks to make sure everything was assigned the right "State" and corrected minor errors made by the LLM. 


## Questions

I would love to chat more about my work, including this project! If you have any questions, please [email me!](mailto:as7500@columbia.edu)


    



