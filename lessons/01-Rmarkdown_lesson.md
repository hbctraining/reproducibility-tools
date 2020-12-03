---
title: Making your research reproducible
subtitle: knitr and RMarkdown
author: Michael J. Steinbaugh, Meeta Mistry, Radhika Khetani, Jihe Liu
---

## Learning Objectives

* Understanding the need for reproducible research 
* Exploring the benefits of RMarkdown reports in the context of reproducibility

## Making your research reproducible
 
For any scientific experiment, it is critical to have it be reproducible. That is, if one were to use the same materials and methods of the original researcher, they would reach the same end results. Having your work be reproducible validates the correctness and the quality of your findings.

For laboratory work, lab notebooks allow us to organize our methods, results, and conclusions for future retrieval and reproduction. These notebooks are then converted into a more concise experimental description outlined in the Methods sections of journals. Computational analysis requires the same diligence. In theory, the equivalent of a lab notebook for computational work would be a detailed log of every action taken by the computer, with a note of the versions of the software being used.

In a [*Science Perspective* article from 2011](https://doi.org/10.1126/science.1213847), Roger Peng describes a reproducibility spectrum. He states that "a study may be more or less reproducible than another depending on what data and code are made available." On the one end of the spectrum you have the publication describing your work; on its own it is not deemed reproducible. Making code and data available enhances the reproducibility. But the big leap towards full reproduction is achieved with complete documentation of the analysis in a transparent fashion, and by providing code that is executable.

<p align="center">
<img src="../img/reproducibility.jpg" width="800">
 </p>

*Image source: Peng 2011 https://doi.org/10.1126/science.1213847*


## RMarkdown

Creating the "gold standard" code is not always easy depending on what programming language you are using. For analyses within R, RStudio helps facilitate reproducible research with the use of R scripts, which document all code used to perform a particular analysis. However, we often don't save the version of the tools we use in a script, nor do we include or interpret the results of the analyses within the script.

RMarkdown is a file format that allows you to save/share your R code with collaborators along with tables, figures, and text describing results and interpretation all in a single document!

RMarkdown documents provide quick, reproducible reporting from R. You write your document using the **Markdown language** and within it **embed executable R code chunks**. The code chunks are paired with **knitr syntax**, so that once your document is complete, you can easily convert it into one of several common formats (i.e. HTML, PDF, PPT).

<p align="center">
<img src="../img/rmarkdown_workflow.png" width="500">
 </p>

*Image source: [Applied R code](http://applied-r.com/project-reporting-template/)*

Wait, what? 

Did most of that last paragraph seem like a foreign language to you? Don't worry, **the goal of this lesson is to cover each of those concepts in much more detail**! By the end of the lesson, you can come back to that paragraph and the workflow image above and will know exactly what it means.

Ready to get started?

---

#### Exercise #1

Before we delve into the details, we will start with an activity to show you what an RMarkdown file (.Rmd extension) looks like, and how to generate the resulting HTML report using the `knit()` function (which is part of the R [knitr package](https://yihui.name/knitr/)).

1. Open up RStudio and **create a new project** in a new directory called `rmd_workshop`. Remember the location in computer where you create this project.
2. **Right click [this RMarkdown file](https://raw.githubusercontent.com/hbctraining/Training-modules/master/Rmarkdown/data/workshop-example.Rmd)**. Download it (using **Save Link As**) and place it within the `rmd_workshop` project directory.
3. **Download and uncompress [this data folder](../data/data.zip?raw=true)** within the `rmd_workshop` project directory.
4. **Open the .rmd file** in RStudio.
5. **knit the markdown** by clicking on the `Knit` button located at the top of your script editor pane.

In the console, you will see a flurry of text scrolling by. The text indicates progress while each code chunk is being executed. Once the document is finished 'knitting', a new window will be automatically opening up with the HTML report that was just generated. Scroll through it and take note of what you see.

> **NOTE**: If you run into an error when knitting the markdown, make sure your data structure is set properly as shown below:
> - The `data` folder should be in the same directory as `workshop-example.rmd` file
> - Two files (`counts.rpkm.csv` and `mouse_exp_design.csv`) are located inside the `data` folder
> <p align="center">
> <img src="../img/workingDir_screenshot.png" width="300">
> </p>

---

## RMarkdown basics

[Markdown](https://en.wikipedia.org/wiki/Markdown) is a lightweight markup language with plain-text-formatting syntax. It is often used for formatting readme files, writing messages in online discussion forums, and creating rich text using a plain text editor. The Markdown language has been adopted by many different coding groups, and some have added their own "flavours". RStudio implements something called **"R-flavoured markdown"**, or **"RMarkdown"**, which has really nice features for text and code formatting as described below.

### Text

The syntax for formatting the text portion of the report is relatively easy. You can easily get text that is **bolded**, *italicized*, ***bolded & italicized***. You can create "headers" and "sub-headers" by placing an "#" or "##" and so on in front of a line of text, generate numbered and bulleted lists, add hyperlinks to words or phrases, and so on.

Let's take a look at the syntax of how to do this in RMarkdown before we move on to formatting and adding code chunks:

<p align="center">
<img src="../img/rmd-syntax.png" width="650">
</p>

You can also get more information about text formatting [here](http://rmarkdown.rstudio.com/lesson-1.html) and [here](http://rmarkdown.rstudio.com/authoring_basics.html).

### Code chunks

The basic idea behind RMarkdown is that you can describe your analysis workflow and provide interpretation of results in plain text, and intersperse chunks of R code within that document to tell a complete story using a single document. Code chunks in RMarkdown are delimited with a special marker (\`\`\`). Backticks (\`) commonly indicate a chunk of code. This syntax is also used for formatting text on [GitHub](https://github.com). 

Each individual code chunk should be given a **unique** name. The name should be something meaningful, and we recommend using [snake_case](https://en.wikipedia.org/wiki/Snake_case) for the names whenever possible. 

<img src="../img/code_chunk_example.png" width = "200">

There is a handy `Insert` button within RStudio that allows you to insert an empty R chunk in your document without having to type it yourself. 

<p align="center">
<img src="../img/rmd_chunk_insert_button.png" width = "400">
</p>

Alternatively, a keyboard shortcut is:

* <kbd>Ctrl</kbd> + <kbd>Alt</kbd> + <kbd>i</kbd> **for PC users**
* <kbd>Command</kbd> + <kbd>option</kbd> + <kbd>i</kbd> **for Mac users**

Additionally, you can write inline R code enclosed by single backticks (\`) containing a lowercase `r`. This allows for variable returns outside of code chunks, and is extremely useful for making report text more dynamic. For example, you can print the current date inline within the report with this syntax: `` `r Sys.Date()` ``. See how we implement this at the 4th line of code in `workshop-example.rmd` file.

For the **final chunk in your analysis, it is recommended to run the `sessionInfo()`** function. This function will output the R version and the versions of all libraries loaded in the R environment. Documenting the versions of the tools you used is important for reproduction of your analysis in the future.

___

#### Exercise #2 

1. Scroll down to the end of the `.rmd` document. **Add a new code chunk.** Within the code chunk place the code `sessionInfo()`.
2. **Add a new section header** above the newly created code chunk. Use a title that best describes the output. Have this header be the same size as the "Project details" header.
3. **Modify the `author` and `title`** parameters at the top of the script.
4. **knit the markdown**. 

[Answer Key](https://raw.githubusercontent.com/hbctraining/Training-modules/master/Rmarkdown/data/workshop-answer-activity3.Rmd)

___

### Options for code chunks

By this point we have mentioned knitr quite a few times, but have not yet fully defined what it is. [knitr](https://yihui.name/knitr/) is an R package, developed by [Yihui Xie](https://yihui.name), designed to generate reports within RStudio. As you have seen, it takes an [RMarkdown](http://rmarkdown.rstudio.com/) file as input and dynamically generates a report as output in the user selected file format (i.e HTML,PDF). 

The knitr package provides a lot of customization options for code chunks, which determine what information is written to the output file. These options are written in the form of `tag=value`.

<img src="../img/r-chunkoptions.png">

There is a [comprehensive list](https://yihui.org/knitr/options/) of all the options available, however when starting out this can be overwhelming. Here, we provide a short list of some options commonly used in code chunks:

* `echo = TRUE`: whether to include R source code in the final knitted document. If echo = FALSE, R source code will not be written. But the code is still evaluated and its output will be included in the final document.
* `eval = TRUE`: whether to evaluate/execute the code .
* `include = TRUE`: whether to include R source code and its output in the final document. If include = FALSE, nothing (R source code and its output) will be written into the final document. But the code is still evaluated and plot files are generated if there are any plots in the chunk
* `warning = TRUE`: whether to preserve warnings in the output like we run R code in a terminal (if FALSE, all warnings will be printed in the console instead of the output document)
* `message = TRUE`: whether to preserve messages emitted by message() in the final output document (similar to warning)
* `results = "asis"`: output as-is, i.e., write raw results from R into the output document instead of LaTeX-formatted output. Another useful option for this option is "hide", which will hide the results, or all normal R output.


### Global options

knitr allows for global options, which means choosing **options that apply to all code chunks in an RMarkdown file**. These will be the default options used for all the code chunks in the document, however they can also be modified for each individual code chunk if required.

Global options should be placed inside your `setup` code chunk. The **`setup` chunk is a special knitr chunk that should be placed at the start of the document**. We recommend storing all `library()` loads required for the script and other `load()` requests for external files here. 

<img src="../img/setup_chunk2.png" width="500">

> **NOTE:** An additional cool trick is that you can save `opts_chunk$set` settings in a hidden file called `.Rprofile`. This file is located in your home directory and accessed by RStudio everytime your open up a new session. By setting this up, these knitr options will apply to all of your RMarkdown documents that you create.

___

#### Exercise #3

1. Only some of the code chunks in the `.rmd` file have names; go through and **add names to the unnamed code chunks**.
2. For the code chunk named `data-ordering` do the following:
    - First, **add a new line of code** that displays a small part of the newly created `data_ordered` data frame using `head()`
    - Next, **modify the options for (`{r data-ordering}`)** such that the output from the new line of code shows up in the report, but not the code
3. Without removing the last code chunk (for boxplot) from the Rmd file, **modify its options** such that neither the code nor its output appear in the report
4. **knit the markdown** 

[Answer Key](https://raw.githubusercontent.com/hbctraining/Training-modules/master/Rmarkdown/data/workshop-answer-activity2.Rmd)

___

### Figures

A neat feature of knitr is how much simpler it is to generate figures. For the most part, you don’t need to do anything. If a code chunk produces a figure, it will automatically be produced and inserted into the final document. A single chunk can support multiple plots, and they will be arranged in squares below the chunk in RStudio. There are a few code chunk options commonly used for plots. For example, to easily resize the figures in the final report you can specify the `fig.height` and `fig.width` of the figure when setting up the code chunk.

<img src="../img/r-figure.png">

You can simply return a plot in a chunk, and also have knitr automatically write the files to disk, in an organized subfolder. Using the `dev` option you are able to specify the desired filetype for your image file, including PNG, PDF, and SVG. 

### Tables

knitr includes a simple but powerful function for generating stylish tables in a knit report named `kable()`. Here's an example using R's built-in `mtcars` dataset:

```r
help("kable", "knitr")
mtcars %>%
    head %>%
    kable
```

|                   |   mpg|  cyl|  disp|   hp|  drat|     wt|   qsec|   vs|   am|  gear|  carb|
|-------------------|-----:|----:|-----:|----:|-----:|------:|------:|----:|----:|-----:|-----:|
| Mazda RX4         |  21.0|    6|   160|  110|  3.90|  2.620|  16.46|    0|    1|     4|     4|
| Mazda RX4 Wag     |  21.0|    6|   160|  110|  3.90|  2.875|  17.02|    0|    1|     4|     4|
| Datsun 710        |  22.8|    4|   108|   93|  3.85|  2.320|  18.61|    1|    1|     4|     1|
| Hornet 4 Drive    |  21.4|    6|   258|  110|  3.08|  3.215|  19.44|    1|    0|     3|     1|
| Hornet Sportabout |  18.7|    8|   360|  175|  3.15|  3.440|  17.02|    0|    0|     3|     2|
| Valiant           |  18.1|    6|   225|  105|  2.76|  3.460|  20.22|    1|    0|     3|     1|

There are some other functions that allow for more powerful customization of tables, including `pander::pander()` and `xtable::xtable()`, but the simplicity and cross-platform reliability of `knitr::kable()` makes it an easy pick.


### Generating the report

Once we have finished creating an RMarkdown file, we finally need to knit the report. You can knit it by using the `knit()` function, or by just clicking on "knit" in the panel above the script as we had done in our first activity in this lesson. 

> Note that when creating your own reports you might find yourself knitting the report periodically as you work through it, rather than just once at the end. 

When executing `knit()` on a document, by default this will generate an HTML report. If you would prefer a different document format, this can be specified in the YAML header with the `output:` parameter. You can also click on the button in the panel above the script and click on "Knit" to get the various options as shown below:

<img src="../img/r-knit-button.png">

> **Note**: *PDF rendering is sometimes problematic, especially when running R remotely, like on the cluster (Cannon or O2). If you run into problems, it's likely an issue related to [pandoc](http://pandoc.org).*

The [RStudio cheatsheet for Rmarkdown](https://github.com/rstudio/cheatsheets/blob/master/rmarkdown-2.0.pdf) is quite daunting, but includes more advanced Rmarkdown options that may be helpful as you become familiar with report generation, including options for adding interactive plots RShiny.

___

#### Activity 4

1. **Download the linked [R script](https://github.com/hbctraining/Training-modules/raw/master/Rmarkdown/Rscript.R)**
2. **Download the linked [RData object](https://github.com/hbctraining/Training-modules/raw/master/Rmarkdown/data/Rmarkdown_data.Rdata)** by right-clicking and save to `data` folder.
3. **Transform the R script into a new RMarkdown file** with the following specifications:
    - Create an R chunk for all code underneath each `#` comment in the original R script
    - Comment on the plots (you may have to run the code from the R script to see the plots first)
    - Add a floating table of contents
4. **knit the markdown** 

[Answer Key](https://raw.githubusercontent.com/hbctraining/Training-modules/master/Rmarkdown/data/workshop-answer-activity4.Rmd)

***

> **Note1: output formats**
> 
> RStudio supports a [number of formats](http://rmarkdown.rstudio.com/formats.html), each with their own customization options. Consult their website for more details.
> 
> The `knit()` command works great if you only need to generate a single document format. RMarkdown also supports a more advanced function named `rmarkdown::render()`, allows for output of multiple document formats. To accomplish this, we recommend saving a special file named `_output.yaml` in your project root. Here's an example from our [bcbioRnaseq](https://github.com/hbc/bcbioRnaseq) package:
>
> ```r
> rmarkdown::html_document:
>         code_folding: hide
>         df_print: kable
>         highlight: pygments
>         number_sections: false
>         toc: true
> rmarkdown::pdf_document:
>         number_sections: false
>         toc: true
>         toc_depth: 1
> ```

***

> **Note2: working directory behavior**
> 
> knitr redefines the working directory of an RMarkdown file in a manner that can be confusing. If you're working in RStudio with an RMarkdown file that is not at the same location as the current R working directory (`getwd()`), you can run into problems with broken file paths. Make sure that any paths to files specified in the RMarkdown document is relative to its location, and not your current working directory.
> 
> A simple way to make sure that the paths are not an issue is by creating an R project for the analysis, and saving all RMarkdown files at the top level and referring to the data and output files within the project directory. This will prevent unexpected problems related to this behavior.

***

**Additional resources**
================

-   [knitr in a knutshell](http://kbroman.org/knitr_knutshell/)
-   [knitr book](https://www.amazon.com/gp/product/1498716962)
-   [knitr examples](https://yihui.name/knitr/demos)
-   [knitr vignettes](https://github.com/yihui/knitr/tree/master/vignettes)

***

*This lesson has been developed by members of the teaching team and Michael J. Steinbaugh at the [Harvard Chan Bioinformatics Core (HBC)](http://bioinformatics.sph.harvard.edu/). These are open access materials distributed under the terms of the [Creative Commons Attribution license](https://creativecommons.org/licenses/by/4.0/) (CC BY 4.0), which permits unrestricted use, distribution, and reproduction in any medium, provided the original author and source are credited.*
