# Twitter-Data-Analysis
Twitter Data Analysis using r language. Twitter sentiment analysis

Require - TwitteR package      - Available on (CRAN)
 WordCloud package
  R 3.3.3
  
  Commands (after installing above packages) 
 
require("twitteR")

require("wordcloud")

api_key <- "YOUR API KEY FROM TWITTER AUTHENTICATION"

api_secret <-  " "

access_token <- " "

access_token_secret <- " "

setup_twitter_oauth(api_key,api_secret,access_token,access_token_secret)

tweets <- searchTwitter('#whateveryouwant',n=100)

l <- length(tweets)

tweeter <- vector(mode = "character", length = l)

for (i in 1:l) tweeter[i] <- tweets[[i]]$getScreenName()

tweeter.freq <- table(tweeter)

wordcloud(names(tweeter.freq), tweeter.freq, colors = c("tomato",  "wheat", "lightblue"), scale = c(6, 0.5), random.color = TRUE, rot.per = 0.5,  min.freq = 1, font = 2, family = "serif")
