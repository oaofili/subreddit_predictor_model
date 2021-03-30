![](https://ofilispeaks.com/wp-content/uploads/Screen-Shot-2021-03-05-at-11.37.21-AM.png)

### Background

In 2019, at the height of Covid-19, I purchased an ipad PRO because of it's newly improved pencil which had been taken the creative world by storm.

With my ipad in hand and the world on lock-down, I started playing around with different drawing apps to pass away time. In the past I had used PhotoShop Elements and Adobe PhotoShop, so it was no surprise that I started off with Adobe Illustrator. But the one app, that I kept hearing about online, was ProCreate.

Curious, I downloaded the app, and wow!

It was the smoothest and most intuitive drawing app I had come across in my 10 years of drawing. The app was so intuitive, that it made me understand how complex Adobe Photoshop features like **masking** and **layering** worked.

With this in mind, I was curious to know as consultant, what Adobe Illustrator could learn from ProCreate (who per image below are growing quite fast in popularity) by analyzing the correspondence between both users.


### Problem Statement

![](https://ofilispeaks.com/wp-content/uploads/Screen-Shot-2021-03-05-at-11.37.53-AM.png)

> “If you torture the data long enough, it will confess.” - Ronald Coase

ProCreate is perceived to be a more intuitive and less frustrating app to use than Adobe Illustrator.

This project thus aims to verify the degree to which the above statement is true by analyzing scraped subreddit text. 

The text will be processed by standard Machine Learning algorithms, but enhanced with sentiment/emotional analysis leveraging on the IBM Watson Natural Learning Understanding program.

If we are able to attain a prediction score of aboe 80%, we will then have confidence to give recommendations based on what we can infer from our analysis on ways Adobe Illustrator bite into the ProCreate market.


### Hypothesis

1. Procreate is more intuitive to use and would have lesser negative emotions (e.g. Disgust) and more positive emotions (e.g. Joy)

> “If you love the data just enough, it will confess.” - Okey Ofili

2. Utilizing sentiment and emotion embedded in text will improve our Machine Learning predictive ability.


### Scrapping The Data

To scrape the data from Reddit, 3 methods were tested and their results and performances are listed below:

1. **Beautiful Soup:** Inspecting the html of several OldReddit webpages, a function utilizing Beautiful Soups's API was written to extract the text and comments of each post on a page. However, this could not be expanded to other pages automatically as Reddit uses a sort of encryption (dynamic links), which ensures each page link cannot be determined with a simple logic. Thus the maximum number of data that could be scraped with Beautiful Soup was 25.

2. **Reddit API:** 1000 is the Maximum Number of Posts the Reddit API could scrape automatically due to Reddit's limit on its API. It was by far the simplest of the 3 scraping mechanisms to use but it did not give me enough data ... my target was at least 5,000.

3. **PushShift API:** The pushshift.io Reddit API was designed and created by the */r/datasets mod* team to help provide enhanced functionality and search capabilities for searching Reddit comments and submissions. It took the longest to execute, over 30 minutes for each subreddit, but it gave me the most information and flexibility of all the methods. At the end of the day, I was able to get 28,000 posts!


### Cleaning The Data

The Data was cleaned several times, for different reasons as the project progressed.

1. **Active Posts** The total number of posts scrapped from both subreddits was about 37,000. This for our computer would be too much information to process and could eat into our IBM API call limits. So I decided to focus on extracting the most active posts, this was done by eliminating posts with less than 4 comments, bringing rows down to 10,001. My assumption was that these posts have more impact on the community than others.

2. **IBM Watson** The IBM Watson NLU analyzer was used on our 10,000+ posts but for texts with 4 words or less, the IBM analyzer was not able to use the information. So we ran a filter that removed all text that did not meet IBM's requirement, dropping our rows to approximately 7,000 rows.

> - AdobeIllustrator    3,595 rows
> - ProCreate           3,443 rows

### Exploratory Data Analysis

![](https://ofilispeaks.com/wp-content/uploads/Screen-Shot-2021-03-05-at-11.38.40-AM.png)

### Inferences/Recommendations

1. **Ipad Niche** It is recommended that Adobe create an App Specific for the IPAD to attract first time users as ProCreate is currently doing. Although Adobe Fresco exists, it’s currently not exciting the art community ... with only 700 subscribers on the Adobe Fresco SubReddit.

2. **ProCreate Expansion** ProCreate can currently only do Rasterized images, there are workarounds to get Vector images in ProCreate, however if ProCreate figures out vector on their Ipad app, they could eat into the Adobe Illustrator user base and ultimately PhotoShop!

3. **Identify Problematic Features** It is recommended that the project is expanded and more data is analyzed so we can find out the specific features that frustrate Adobe Illustration users. For example this text here says "The color picker is maddening. Want to bite my hair off right now." It would be helpful to understand if there are other people struggling with the Color Picker feature currently.

![](https://ofilispeaks.com/wp-content/uploads/Screen-Shot-2021-03-05-at-11.39.30-AM.png)
