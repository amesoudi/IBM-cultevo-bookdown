I am reporting here various matters discussed in previous emails, and adding some others.

#### General project idea

The goal of the project is to generate a series of Rmarkdown tutorials that illustrate the development of individual based models of cultural evolution, and to put everything together in a book made with [bookdown](https://bookdown.org).

The idea would be to have IBM treatments of the most important topics in cultural evolution. The models would not be new, but the goal would be to be relatively exhaustive, to go from simple to more complex models/topics (so the book could be used as an intro to IBM in cultural evolution by students), and to have plenty of codes, examples, etc., for the various topics, again mainly reproducing results that are already there, but within a common framework. And, everything should be done in R, which is increasingly popular among the sciences and taught to students, but still underrepresented in a modelling context.

#### TOC

We have a couple of documents with the models that could be included. It would be good to start to work towards a tentative TOC in the next weeks. We can work on the [document](TOC.md) in this repository.

#### General coding

We agreed to use [the tidyverse package](https://www.tidyverse.org) and some of the main features, mainly `tibble()` instead of `data.frame()` and `ggplot()` instead of `plot()`. 

Since tibbles are in many cases less performant than matrices we decided that we can use in general tibbles, but for some model that will be particularly heavy/slow because of that, we can introduce an alternative code with matrices. This will also give the occasion to talk about benchmarking and show how to do it (at a basic level) in R. These models will follow the pure-tidy models in the book.  


#### Some convention

In general, I'd try to follow the [tidyverse style guide](https://style.tidyverse.org) for names of functions, variables, code, just to be consistent. There is also a [library](https://www.tidyverse.org/articles/2017/12/styler-1.0.0/) that formats automatically the code according to the style guide, and it can be accessed in R Studio from the "Addins" menu ("Style active file"). Of course, it formats things like spaces or tabs and not names or the Rmarkdown text.

For the text, I did so far as such:

* inline code: `geom_line()`, `unbiased_transmission()` (this is standard markdown)

* technical terms: 'geoms', 'chr'

* names of variables: $p$, $generation$ (latex style, works in Rmarkdown)

* names of data structures: **population**, **output** (in **bold**, since if in *italics* they look like names of variables)

Let's add here other options, or discuss if you prefer something else.

#### Others

* We may want to consider that some readers will use directly the Rmd files, others the html/pdf generated by bookdown, and others potentially a printed version. We need to discuss this in the Intro, and edit accordingly the parts where we mention directly RStudio? (e.g. "Run this code snippet using the green 'play' triangle in the top right of the snippet.")

* We need to introduce some information on the functioning of non-basic R (e.g. ggplot, tibbles, etc.). If we do it when describing the models it can be distracting, we can use "boxes", or appendixes or in the intro...

* If we agree on using the terminology "individual based" (versus "agent based"), we need to remember to explain in the intro
  1. why we do this (*individual* is opposed to *population* and it indicates the level of abstraction at which the model is specified, check Grimm & Railsback) and
  2. individual should not be intended necessary in biological sense, an individual can be a firm, an organisation, etc. 

* It may be useful to have at the end of each model (or chapter) a section that briefly describes the relevant literature.