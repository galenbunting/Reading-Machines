Layout: post

Title: Lab Report #7: Building a Bot

tags: [lab report, fieldbook]

author: Galen Bunting

# Variables and Volumes

In this lab, we began working with bots and R Studio for the first time. Our lab took place in NULab this week, which meant we had access 
to an overhead screen along with more access to electrical sockets for our computers, which was a complete necessity for this particular lab, as
at least two computers died during the process of the lab. Today, we were programming literary bots, an activity I looked forward to with some 
relish. I am familiar with various bots in the course of my internet wanderings, including How 2 Sext @wikisext and Lil Miquela, an electric literature 
project who, as a fictional character and digital art project, regularly posts to Instagram as a model. Such projects create pastiches, 
parodies, or other remixed media. To say the least, I was excited to begin working with bots. 

We began by signing into R Studio, on Northeastern's DSG server. We worked within an R Markdown file format, meaning that we could weave words 
and coding if we so chose. The file we worked within was itself a remixed format: as Jim Ridolfo and Dànielle Nicole DeVoss argue in 
"Composing for Recomposition: Rhetorical Velocity and Delivery,"  "remixing—or the process of taking old pieces of text, images, sounds, video 
and stitching them together to form a new product—is how individual writers and communities build common values...remix is perhaps the premier c
ontemporary composing practice." We were about to embark on a new journey of remixing and reinventing texts, and this quote assists in framing 
this composing practice which we used in this lab. Throughout this document, as I recount the events of the lab, I will meditate and explore 
this quote. Through the RMD file format, we worked with more than a text file: we worked with a program which we began to learn how to run in 
RStudio. We ran some strings of math equations in order to learn how to execute commands. Thankfully, we didn't dwell long on math, and moved
on to a new order of operations: loading packages written by other members of the R community to allow us to manipulate data into remixing and
reinventing from Project Gutenberg, Wordnik, and Twitter. 

We then explored what a variable is through the following expression: 

```{r}

raven <- "raven"
raven

```
The arrow allows "raven" to be stored as a variable inside raven- the arrow or the equals sign allow a communication between R Studio and the 
working memory of the computer. In this way, the use of the variable itself stores data inside other data: it is a remix of the data as an 
expression. Since a variable's purpose is to hold data, we might read a variable as a form of composing data which takes old pieces (letters and 
numbers) to create a new product altogether. In this way, we were remixing, simply by learning how the variable form works.

However, we did not stop at variables. 
We contained the rest of the verse from The Raven in the variable, and then we contained it as a list: 

```{r}

raven <- list("Be","that","word","our","sign","of","parting",",","bird","or","fiend")

```
This simple list showed how easy it was to re-select and re-shuffle data in a way which we later built on within the lab in order to 
remix the data in this simple verse. 


# Bottish Literature 

We leaped into Mad-Libs-style poetry first by experimenting with substitution lists, which allowed us to create a set list of words to combine 
into variables, which then expressed in nonsensical remixed works. 
The list form came into practice as a preset library of terms which we could customize: I opted to replace my words with words from Bioshock (2007), 
with terms such as "splicer" and "plasmid."
This produced ridiculous results such as: "attacked the splicer, bloody hell!"

We then used our previously collected Wordnik API cords to draw from the Wordnik online dictionary. Despite some difficulty in finding our API 
codes within spam, we all ultimately found and placed these API codes within our consoles. This format allowed us to pull from words which 
appeared within Wordnik's dictionary at least 100 times, allowed us to specify the part of speech we wanted to remix into a poem, and allowed us 
to run code which would express as poems by replacing variables as words from the Wordnik dictionary. Using the`poem_word()` function to arrange 
words in and concatenate (combine) words within our poem, we were able to create poems. We then ran operations which allowed us 
to place a selected amount of 100 words for each part of speech desired to be stored on our server, to avoid overloading Wordnik's API. 

My poem read, "snuffing thy zones from touching my wapentake, and restocked thy ballerinas from again my values!
Quoth the Ravbot, "goddamnit"" 

A nonsensical result to be sure, but a result which remixed and reshuffled terms into a bot-created form of poetry. 

Finally, by using Twitter's API to establish Twitter credentials and then identify trending topics based on Boston's geographic location, 
we were able to use the "get_trends" function to filter by trending hashtags in order to tweet via that hashtag, inserting a hashtag at 
the end of our bot-created concatenates: 

```{r}

token <- create_token(
  app = "madlib_poetrybot",
  consumer_key = "tNh5iiXV6QNtvG3JskFNi6imL",
  consumer_secret = "Ez6uQirax9EOo55uvjCOfqw3p1cgQuc81IwEdh7Wo1qzEbCa5t",
  access_token = "1100069980681498626-m7pxkLwg1yyYwXSdyU4UYYmWfx4CQA",
  access_secret = "ffS4HrRH5AwXoeziOyZWIuOka8ROCWPXKl2RATybGphdh")

trends <- get_trends("boston") %>%
  filter(grepl("^#", trend))
 
```
We then used another code to count characters to make sure we stayed within Twitter's 280 character limit. My post was immediately tweeted. 

# Reflections and Recountings 

In particular, our use of Twitter to post to trending hashtags made me wonder what a stray wanderer into those trending hashtags would think, 
if they strayed across our bot-created literature. We, of course, know the context, but would an outsider? Probably not. 
