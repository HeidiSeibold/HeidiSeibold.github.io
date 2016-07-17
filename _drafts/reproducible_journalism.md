# What journalism can learn from open and reproducible research

I am a PhD student in Statistics and I am not a journalist. I do write a
[blog](http://heidiseibold.github.io/), but I would not consider this
journalism.  I think, however, that journalists - especially data journalists
and researchers can learn a great deal from one another. And I think that open
and reproducible data journalism can use the same tools and workflows as open
and reproducible science. Because both investigate complex topics, often
involve collaboration and have openness and reproducibility as goals.

## What should data journalists consider to learn

### R
R is great for everything from reading in diverse types of data, doing
statistical analyses, creating graphics (e.g. [ggplot2]()) and full documents
([RMarkdown](), [knitr]()) to even creating webapps ([shiny]()) or
[websites]().  Andrew Flowers from FiveThirtyEight gave a great talk at the R
User Conference in Stanford in which he argued that R is the best tool for
journalists. His five big reasons are:

- Open Source (transparency, GitHub)
- ggplot2 (custom theme, weird charts)
- Data wrangling (speed, messy data)
- Collaboration(RStudio/Git/GitHub integration)
- Interactives (Shiny prototypes, data processing) 

Please watch the
[talk](https://channel9.msdn.com/Events/useR-international-R-User-conference/useR2016/FiveThirtyEights-data-journalism-workflow-with-R)
for details. Also Check out Timo Grossenbacher`s blog post on [why data
journalists should start using
R](https://timogrossenbacher.ch/2015/12/why-data-journalists-should-start-using-r-in-2016/).


### Version control (Git/Subversion)
Please do consider learning a version control system like [git]() or
[subversion](). You might have noticed that it was already mentioned in Andrew
Flowers big reasons for R. It is essential to collaborating with other writers
smoothly and without losses. Also when you realise that someone did something
stupid, you can always go back to any older version of your text or code.


### Publication of code and data (GitHub)
One service that makes it very easy to publish code and data is
[GitHub](). It goes wonderfully along with the version control 
system git and is free. Many data journalists use this already 
including teams from [The Guardian](), [The New York Times](),
[FiveThirtyEight](), [SRF]() and [ProPublica](). These are great
role models. If you want to own the system where you put up your
stuff, go ahead and publish the stuff on your website. Seems good 
to me, too. Just try to make it easy for people to access it.
You will be surprised to see, what people make from thing that 
you started. This might sometimes be a little uncomfortable, 
since everyone makes mistakes every once in a while, but mostly
it will boost your image.


### make

### Docker
