Layout: post

Title: Lab Report #8: Computational Analysis I

tags: [lab report, fieldbook]

author: Galen Bunting

# Lab Proceedings 

For this lab, we proceeded to sign in to R Studio as a group, and navigated to the Computational Analysis file. There, we found a tutorial 
compiled by Professor Cordell for the purpose of our class. We loaded the tidy text directories and libraries, so that they would work with 
the base program of R Studio in order to process the directory of Project Gutenberg. We then proceeded to review what a pipeline was as 
expressed by %>% along with functions to break words apart by tokens, to count, and then ungroup them. For the purpose of this pipeline, we
loaded the Project Gutenberg file of Henry James' novella *In The Cage,* the story of a telegrapher who learns about the lives of others. 

```{r}
words <- cage %>%
  unnest_tokens(word, text) %>%
  count(word, sort = TRUE) %>%
  ungroup

View(words) 

{r}```

First, stop-words were sorted by count, so we ran an operation which would allow us to remove stop-words (such as "the," "and", "if", "but"). 

Therefore, we were more easily able to tell which words were the most prominent throughout *In The Cage.*
