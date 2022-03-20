
# Welcome to my first GitHub website. 

## Quick Introducution 
I am a New Zealand born Korean that is in his second year studying Data Science in Auckland. In this repo, I will be sharing my meme aswell as giving a little explanation and showing how it was made. 

## Meme Introduction
With the ongoing Ukrainian invasion, the world has seen a immense increase in petrol prices.
With the petrol prices being all over the media, I decided to make a lighthearted *meme* using **(magick)**.

## The Meme

![my_meme](https://user-images.githubusercontent.com/100745215/158946733-4872d0ca-7117-4a43-8925-c6329ef4dafd.png)

## Meme Explanation
I used a basic *meme*  template, which depicts two photos in the first column with corresponding comments to the right. 
The first photo shows the scandalous increase in petrol prices in New Zealand.
The first comment on the right is a sarcastic view that petrol prices aren't as precipitous as the media makes it out to be. 
The second photo used in this *meme*, is a photo of [Elon Musk](https://en.wikipedia.org/wiki/Elon_Musk), who is smoking cannabis.
The photo of Mr. Musk was used in irony, as he is the founder and CEO of Tesla, the most dominant electric motor company in the world.
The parallel comment made is to show that in fact that petrol prices are indeed "high" in New Zealand. 




## R Code Used To Make The Meme
~~~r

gases_price <- image_read("https://tvnz-1-news-prod.cdn.arcpublishing.com/resizer/BX14RYU6a9TiMnSL1OUMYkCXAFc=/800x450/filters:format(jpg):quality(70):focal(-5x-5:5x5)/cloudfront-ap-southeast-2.images.arcpublishing.com/tvnz/DPOGT5JWD5BWBHDQDFG5D322AQ.jpg") %>%
  image_scale(500)

high <- image_read("https://cdn.geekwire.com/wp-content/uploads/2018/09/180907-musk-630x455.jpg") %>%
  image_scale(500)

low_price <- image_blank(width = 500,
                         height = 281,
                         color = "#000000") %>%
  image_annotate(text = "gAS\nPrICeS\naReN't\neVen\ntHAt\nhIGh",
                 color = "#FFFFFF",
                 size = 40,
                 font = "Impact",
                 gravity = "center")
high_elon <- image_blank(width = 500,
                         height = 361,
                         color = "#000000") %>%
  image_annotate(text = "Gas\nprices\nin\nNZ",
                 color = "#FFFFFF",
                 size = 80,
                 font = "Impact",
                 gravity = "center")

first_row <- c(gases_price, low_price) %>%
  image_append()
second_row <- c(high, high_elon) %>%
  image_append()
meme <- c(first_row, second_row) %>%
  image_append(stack = TRUE)

image_write(meme, "my_meme.png")
~~~




