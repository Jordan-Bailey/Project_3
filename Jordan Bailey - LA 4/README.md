### Abstract

My intent with this project was to build a classification model that could distinguish between two subreddits which, I initially thought, would have somewhat similar topics.  For this project, I chose the umbrella terms "History" and "Mystery" to describe the two categories I wanted to discriminate between.  Such a model may have a practical application, as with this example, by a company wanting to keep its message boards clear of any erroneous information or ill content.

### Process

I first gathered posts from 4 different subreddits through querying Reddit's built-in API. These 4 subreddits were: History: /r/history and /r/AskHistorians, Mystery: /r/conspiracy and /r/UnresolvedMysteries. I gathered ~1000 unique posts from each of them, for a total of a shade less than 4000 posts.  Of these posts, all of them had titles, and the majority of them had selftext, or text in the body of the post.  I then passed the text from these posts into a vectorizer, followed by running a Logistic Regression model, a Decision Tree, and a Random Forest, GridSearching over the last two.

### Results

The best score for my model came from a Logistic Regression model performed on the fulltext, with the words gone through a TF-IDF vectorizer.  The Random Forest model also did well, about 89.7%, but I feel that, because of its inherent simplicity, I would choose to use the Logistic Regression model for real world data.

One point I wanted to address was that there was little difference between the words prioritized by my TF-IDF vectorizer and a regular CountVectorizer, and as such my results for my models fit on each type are very similar.  I want to look into the documentation for these vectorizers in the future to get a better look at how they operate.
