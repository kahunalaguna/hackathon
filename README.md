PROJECT-HACKATHON

### Overview

For this project I was tasked with performing some data analysis and fitting at least two models on a topic of my choice. I decided to make NFT's the focus of my work. I initially wanted to scrape data from opensea (NFT platform) on a specific collection called mfers. I didn't have an API key approved in advance and began trying to scrape by working around not having private access. I was able to scrape data regarding the overall collection but was eventually stimied by the API key hurdle when trying to scrape the data on specific assets which is what I needed to model. With 2 hours burned and nothing to show for it I threw my work in the "botched" folder and found a a dataset on [Kaggle](https://www.kaggle.com/tunguz/cryptopunks) on a different collection of nfts. 

I moved forward with the cryptopunks dataset containing tens of thousands of transactions performed or initiated for all 10,000 CryptoPunks. Like many nft collections, these animated avitars are prized for their rare features. They come in many different types (human man, human woman, zombie, alien, ape) and with tons of unique characteristic combinations (hair style, hair color, countless accessories, etc.). Knowing that implementing these measures of rarity into my model would be paramount to performance I proceeded to spend the next couple hours scraping rarity scores on each unique characteristic/style(green wild hair, welding goggles, etc.) for each attribute (hair, eyes, etc.) from [rarity.tools](https://rarity.tools/cryptopunks). 

After successfully scraping the raw data I ran into some coding conundrums preventing me from adding the rarity scores as new features into my data set which only included lists of features included. Forced to decide between fitting models and resolving isssues in code, I moved on with the resolve to return to my work and improve it at a later date.

### Problem Statement

I want to know if by using historical transaction data and nft characteristics I could accurately predict the price of nfts belonging to a certain collection.

### Data Science Process

Data Collection: Proved to be a daunting task initially with the mfers collection that I hoped would be resolved by switching to an exiisting dataset, however, scraping rarrity scores proved to be quite a challenge in itself. 

Data Cleaning: The most difficult task was sweeping through the transaction records to clear out unrealistic bid offers that could deviate model performance from optimal behavior but luckily I was able to implement existing code from a kaggle user that I credited in the notebook. Cleaning the scraped rarity data is a whole different story as the format was nothing I had delt with before and learning how to manipulate it took precious time away from prroject progress. To add insult to injury I was unable to actually implement the data do to a minor mishap in my processing of the javascript that went unnoticed until I was all but ready to add the scores into the dataframe, mapped against the pre-existing list of accessories. 

Preprocesssing: Although I was unable to fit attrribute rarity scores into the model, I was able to preprocess the accessory list using sci-kit learn's MultiLabelBinarizer to include the features in some degree at the very least. Before modeling I made final decisions about feature including and chose to also subset the data by transaction type to only train and test the model on transactions resulting in an actual sale. 

Exploratory Data Analysis: My scraping and web research proved to be the greatest source of exploratory data anlysis since I was able to learn just how significant individual accessories/styles of each nft attribute is to an nft's "intrinsic" value.

Modeling: I fit a wide variety of regressor models including linear regression, decision trees/random forests, bagging, boosting, ensemble methods, and support vector regressors. Results were uniformly poor. Trees, bagging, and random forests yielded the highest scores on train data but were the most overfit and scored the worst on test data. 

### Conclusions and Next Steps:

To frame the model process in the lens of the problemm statement, I was certainly unable to accurately predict anything. However, as proof of concept for further work on this topic of predicting nft price, I am confident that massive improvements can be made by including all the data I had hoped for, greater efforts in feature engineering, and lots of manual labor in fine tuning a wide variety of models.

Included in my data is also the images of the CyberPunk collection. Image data offers a whole new medium to manipulate and model these nfts. In the future I hope to process these images and build a convolutional neural network to incorporate the image data into the project either as a predictive model type for comparison against or as some step in the process of creating the best performing predictive model overall. 
