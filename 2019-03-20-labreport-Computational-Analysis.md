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


words <- cage %>%
  unnest_tokens(word, text) %>%
  count(word, sort = TRUE) %>%
  ungroup

View(words) 


First, stop-words were sorted by count, so we ran an operation which would allow us to remove stop-words (such as "the," "and", "if", "but"). 

Therefore, we were more easily able to tell which words were the most prominent throughout *In The Cage.* However, some of these high-count words 
included the names of characters. Laura and Avery mentioned the fact that it is in fact possible to remove these terms from the general count and place them within stop words. We then had the opportunity to run a similar operation via a work of our choice: I selected Virginia Woolf's 
*Jacob's Room,* in order to see what leading words were used multiple times. Using the work's identifier via Project Gutenberg, it is possible to 
load Project Gutenberg works in one's global environment, and sort them in various ways by counting words across the corpus. 

We then repeated this experiment with the works of Jane Austen, dividing her works by total words and sorted words, so that one could see the total words in, for example, *Northanger Abbey*, and sort by the most used words. Similarly, we removed stop words. 

Using some of the graphing abilities present in the tidy_texts universe, we were able to display the total amount of words in all the novels, 
however, given the fact that this operation pulls from the total length of all texts including stop words, the graphs produced were difficult to parse, and illustrated a principle which explains that the most used words in any language tend to be stop words. We then removed stop words to produce various different graphs from the library of Jane Austen's works. 

Then, we used n-grams to show which words held locational probability across Jane Austen's works. N-grams attempt to predict the next item 
in a particular sequence. They show a continguous sequence of any number of objects in a text, based on the words which precede it. We were able to show "I do not know..." as one of the top n-grams across our corpora. 

Professor Cordell concluded the lab by acknowledging that when conducting such computational analysis, it is important to talk about the data as data, not just as a graph which is self-evident or self-explanatory. 

# Computational Reflections 

While the lab was edifying, I could not help thinking of Denis Tenen's argument in *Plain Text* that codes govern other codes. Even digital books, which can be very easily duplicated online, are protected via the Digital Millennium Copyright Act of 1996. The technological control of digital books requires us, as scholars, to "perceive the mechanisms of its codification" (3). We may wish to use computational analytics when approaching our own scholarship of various texts. However, it is important for us to perceive our adaption of such books as a reading, and how this reading changes our approach to our chosen texts. I also pondered how digital books complicate study: surely someone hoping to study e-books would need to obtain certain licensing, among other institutional barriers. Would it be possible to, say, load the seven Harry Potter books into a corpora directly from their Kindle format, or would one need to be careful of copyright law? I am not sure of the answer without further study, but I suspect one would need to navigate a perhaps complicated gauntlet of red tape.

In Rita Raley's "TXTual Practice," the question of empherality looms large. If one attempted to pull corpera from a publically available website, what guarantee would scholars have of that website's eternal presence? Websites spring up almost as quickly as they are deleted: this fact is why a project such as the Internet Archive exists, an attempt to capture a rapidly expanding and collapsing growing thing. I pondered how the shape of the Internet itself complicates the task of computational analysis: while it seems quite easy to count and quantify numberic information, it is less easy to capture rogue words when the Internet itself often exists as an emphemeral medium. 

