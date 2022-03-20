
# My Meme
![my_meme](https://user-images.githubusercontent.com/101084953/158925824-6e70c322-30cb-4284-a3bf-1f9033c85a2a.png)

## About The Meme
I made a meme using ```R``` script in R studio about the struggles of online learning, it struggles and how daunting it may seem. 

* This meme was made with a similar format to other memes with a some variations
* The idea and message behind the meme was some what original and something that I havent seen before 




### The Codes 
``` 
library(magick)

#image one
 
in_person_learning <- image_read("https://www.teaching.unsw.edu.au/sites/default/files/styles/quicklink/public/quicklink/shutterstock_218235067.jpg.jpeg?itok=gSQvT9KF") %>%
  image_scale(600)

#text in front of image one

ipl_text <- image_blank(width = 500, 
                        height = 500, 
                        color = "#737373") %>%
  image_annotate(text = "In\nCampus",
                 color = "#FFFFFF",
                 size = 60,
                 font = "Impact",
                 gravity = "center")

#image two
online_learning <- image_read("https://www.babystore.ae/pub/media/amasty/webp/wysiwyg/ni/blog/56_How_Visual_Stress_During_Online_Learning_Impacts_Kids.webp") %>%
  image_scale(600)

#text in front of image two

ol_text <- image_blank(width = 500, 
                       height = 500, 
                       color = "#737373") %>%
  image_annotate(text = "Online\nLearning",
                 color = "#FFFFFF",
                 size = 60,
                 font = "Impact",
                 gravity = "center")

#using vectors

first_row <- image_append(c(in_person_learning, ipl_text)) 

second_row <- image_append(c(online_learning, ol_text))


meme <- c(first_row, second_row) %>%
  image_append(stack = TRUE) %>%
  image_scale
(800)
image_write(meme, "my_meme.png")
``` 
