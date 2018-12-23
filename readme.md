# Instagram - What makes a post successful

## The Project

Collecting data from National Geographic's instagram page (images - caption - likes - comments), I ran multiple logistic regression models creating a machine that predicted the posts that would be successful and used Latent Dirichlet allocation to determine the aspects and context behind their success.

National Geographic was selected due to its homogenuity of posts, overall user activity and steady flow of posts. All the steps and data analysis process is thoroughly presented in the project's report.

## Tools used

- Python 3
- Jupyter Notebook
- Google Vision API 
- Sklean


## Important Notes

1. The engagement score of each post was calculated based on the below formula:
$$EngagementValue = 0.4\frac{likes}{max Likes} + 0.6\frac{comments}{max Comments}$$ 

Using this formula and the overall median engagement value of all the posts, I set the "Engagement" parameter as 1 (there was engagement related to a post) for all posts that had EngagementValue above or equal to the median and 0 for the rest of the posts, classifying all our posts into two discrete categories. It was important to take into account the relevant engagement of each post, identifying the posts that were popular in relation to the rest of the National Geographic posts.

2. Three different logistic regression models were used in the analysis:

- One using the google vision API labels as input
- One using the image captions as input
- One using both google vision API labels and image captions as input

3. The use of LDA (Latent Dirichlet allocation) for the clustering of the images and theme selection was used multiple times until through the review of the words with the highest scores per category was decided that there were 4 underlying themes in the images:

- plants
- human factor
- animal
- scenery

## Interesting Insights

- Using using both google vision API labels and image captions as input improved the model's accuracy only slightly. The added complexity of the model was not justified. It seemed that the information of the image labels and description were correlated, essentially describing the same thing and carrying the same amount of information. The image caption was describing what the google vision API is summarising in its labels.

- The first theme (related to nature and plants) was prominent in all the images irrespective of their engagement, which was expected given that the images were collected from national geographic's page and thus it did not appear to be the differentiating factor.

- On the other hand, the rest of the themes (human factor, animal and scenery) played a crusial role in separating images from mediocre to great. More unsuccessful images had twice the amount of "human factor", more than 5 times "animal" related themes, and twice the "scenery" aspect.

## Advice for National Geographic

Based on my analysis, I would advice the people responsible to keep focusing on natural themes, but rather adding more context to their images enhancing the human factor and somewhat avoiding the plain classic beautiful animal related scenery themes.
