# What journalism can learn from open and reproducible research

I am a PhD student in Statistics and I am not a journalist. I do write a
[blog](http://heidiseibold.github.io/), but I would not consider this
journalism.  I think, however, that journalists - especially data journalists
and researchers can learn a great deal from one another. And I think that open
and reproducible data journalism can use the same tools and workflows as open
and reproducible science, because both investigate complex topics, often
involve collaboration and have openness and reproducibility as goals.

![](https://upload.wikimedia.org/wikipedia/commons/f/f4/Campagnolo_Tool_Kit_Super_Record_Wooden_Box_Nr._16.jpg) 

## What should data journalists consider to learn
### R
R is great for everything from reading in diverse types of data, doing
statistical analyses, creating graphics (e.g.
[ggplot2](http://docs.ggplot2.org/current/)) and full documents
([RMarkdown](http://rmarkdown.rstudio.com/), [knitr](http://yihui.name/knitr/))
to even creating webapps
([shiny](http://rmarkdown.rstudio.com/authoring_shiny.html)) or
[websites](http://rmarkdown.rstudio.com/rmarkdown_websites.html).  Andrew
Flowers from FiveThirtyEight gave a great talk at the R User Conference in
Stanford in which he argued that R is the best tool for journalists. His five
big reasons are:

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

There are plenty of R courses you can take. If you want to try learning R by
yourself, you might want to try [swirl](http://swirlstats.com/), which is an
interactive R course within the R console.

All the following tools work great with R and since I think using R is the most
essential, I will mostly add tutorial suggestions that are easily
understandable for R users. 


### Version control (Git/Subversion)
Do consider learning a version control system like [git]() or
[subversion](). You might have noticed that it was already mentioned in Andrew
Flowers big reasons for R. It is essential to collaborating with other writers
smoothly and without losses. Also when you realise that someone did something
stupid, you can always go back to any older version of your text or code.

If you want to use Git or Subversion from within RStudio (a R IDE), you can try
the [tutorial by Hadley Wickham](http://r-pkgs.had.co.nz/git.html). For a
non-technical introduction you can also check out the [GitHub
tutorial](https://guides.github.com/activities/hello-world/) (For more info on
GitHub see below). I personally prefer using Git and Subversion from the
command line (check out this [tutorial on
git-scm.com](https://git-scm.com/docs/gittutorial)). 


### Publication of code and data (e.g. GitHub)
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

To get started on GitHub, check out the [GitHub
tutorial](https://guides.github.com/activities/hello-world/)



### make or some other way of automation
[make]() is a automation software that let`s you define rules of dependecy
between documents, data, programs, etc. It is very helpful if you do an
analysis and use more than two code documents. It is independent of the tool
and can be used with any program than is accessible via command line. I use
this for every project.  This way I do not have to keep track of which files I
have changed and which code I have to rerun. 

To get a first glimpse at how to use Makefiles, check out the
[tutorial by Karl Broman](http://kbroman.org/minimal_make/). 

### Docker
[Docker](http://www.docker.com/) images are essentially little computers on
your computer, which you can send to other computers easily and which can be
used to keep a stable environment to work with. Imagine you use software for a
project that is hard to install or that might change over time. You want to
collaborate on the project with someone or maybe you want to go back to the
project some time in the future. This can be really hard. If you have a little
pseudo-computer (docker image) where you have just the stuff for this given
project installed and maybe even have the data and code saved in there, you can
just send it to your collaborator or your future self. The person then only has
to start up the image and can work in this fixed environment.  The Washington
post just published a [video](https://youtu.be/_PDoxTThGnY) in which they
describe what they use Docker for. 

To get started with Docker, check out this
[tutorial](http://ropenscilabs.github.io/r-docker-tutorial/) or the
[courses on the Docker website)[https://training.docker.com/]. 
 




