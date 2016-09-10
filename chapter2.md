---
title_meta  : Chapter 2
title       : The second datacamp chapter
description : In this chapter we’ll get you into the right frame of mind for developing meaningful visualizations with R. You’ll understand that as a communications tool, visualizations require you to think about your audience first. You’ll also be introduced to the basics of ggplot2 - the 7 different grammatical elements (layers) and aesthetic mappings.
attachments :
  slides_link : https://s3.amazonaws.com/assets.datacamp.com/course/ggplot2/course_1/ggplot2_course1_ch1_slides.pdf
free_preview : TRUE

--- type:NormalExercise lang:r xp:100 skills:1,4 key:90c276a7f0
## ggplot2 is awesome!

To get a first fill for `ggplot2`, let's try to run some basic `ggplot2` commands. Together, they build a plot of the `mtcars` dataset, that contains information for 32 cars from motor trends magazine from 1973. This dataset is small, intuitive, and contains a variety of continuous and categorical variables.

*** =instructions
- Instruction one
- Instruction two
- Instruction three

*** =hint
- Use `library(ggplot2)` to load the `ggplot2` package.
- `str(mtcars)` will show you the structure of the `mtcars` dataset.
- For the third instruction, just hit Submit Answer and try to understand the code.

*** =pre_exercise_code
```{r eval=FALSE}
# no pec
```

*** =sample_code
```{r eval=FALSE}
# Load the ggplot2 package


# Explore the mtcars data frame with str()


# Execute the following command

```

*** =solution
```{r eval=FALSE}
# Load the ggplot2 package
library(ggplot2)

# Explore the mtcars data frame with str()
str(mtcars)

# Execute the following command
ggplot(mtcars, aes(x = cyl, y = mpg)) +
  geom_point()
```

*** =sct
```{r eval=FALSE}
test_library_function("ggplot2")

msg <-  "Call [`str()`](http://www.rdocumentation.org/packages/utils/functions/str) with the `mtcars` dataset as an argument."
test_function("str", "object", not_called_msg = msg, incorrect_msg = msg)

msg <- "You don't have to change the [`ggplot()`](http://www.rdocumentation.org/packages/ggplot2/functions/ggplot) command, it was predefined for you."
test_ggplot(1, data_fail_msg = msg, aes_fail_msg = msg, geom_fail_msg = msg)

test_error()
success_msg("Good job! Notice that `ggplot2` treats `cyl` as a continuous variable. We get a plot, but it's not quite right, because it gives the impression that there is such a thing as a 5 or 7-cylinder car, which there is not.")
```

--- type:MultipleChoiceExercise lang:r xp:50 skills:1,4 key:98405bb120
## This is a multiple choice question

In this video we made the distinction between plots for exploring and plots for explaining data. Which of the following are exploratory plots typically _NOT_?

*** =instructions
- Meant for a specialist audience.
- Data-heavy.
- Pretty.
- Rough first drafts.
- Part of our data science toolkit as graphical data analysis. 

*** =hint
If you're not sure, you can watch the video again.

*** =pre_exercise_code
```{r, eval=FALSE}
# no pec
```

*** =sct
```{r, eval=FALSE}
msg1 = "Exploratory plots are perfect for specialist audiences, because they will be able to handle all the data and properly critique it." 
msg2 = "We often make lots of very data-heavy plots to explore our data."
msg3 = "Exactly. We're not concerned with beautiful at this point. Although, the plots should be meaningful and conform to best practices so that we are not misled!"
msg4 = "Exploratory plots are the first kind of plots you'll make, so they're going to be pretty rough - expect to do lots of revisions!"
msg5 = "Exploratory plots are an extension of your data science capabilities! "
test_mc(3, feedback_msgs = c(msg1, msg2, msg3, msg4, msg5))
```
