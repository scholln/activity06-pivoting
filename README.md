Activity 6 - Pivot!
================

It is assumed that you have read Chapters 9 and 10, and 12 from R4DS and
completed the Derive Information with dplyr Primer.

In this activity, you will:

-   Locate and read data or other files into R using the `here::here`
    function.
-   Restructure datasets into longer and wider formats using `{tidyr}`.
-   Separate and unite columns into a tidy format.
-   Dress up data tables to help with human readability.

## `gather` and `spread` vs `pivot_longer` and `pivot_wider`

In the Primer, you learned about the `tidyr::gather` and `tidyr::spread`
functions. These two functions still exist within the **tidyverse**;
however, they have been superseded ![superseded
badge](README-img/lifecycle-superseded.png) and will no longer receive
new features. You will often see these [“lifecycle”
badges](https://lifecycle.r-lib.org/articles/stages.html) on
`{tidyverse}` packages and are meant to provide additional information
to users.

Hadley’s introduction to the new pivoting functions can be found at the
[tidyverse blog](https://tidyr.tidyverse.org/dev/articles/pivot.html).

In the `tidyr::gather` help documentation (i.e., type `?gather` in the
**Console**), we can see how to do similar calls using
`tidyr::pivot_longer`.

> `df %>% gather("key", "value", x, y, z)` is equivalent to
> `df %>% pivot_longer(cols = c(x, y, z), names_to = "key", values_to = "value")`

Similarly, in the `tidyr::spread` help documentation, we can see the
similarities to `tidyr::pivot_longer`.

> `df %>% spread(key, value)` is equivalent to
> `df %>% pivot_wider(names_from = key, values_from = value)`

An important thing to recognize between the two `pivot_` functions is
when we use quotation marks `"..."`.

-   For `pivot_wider`, we are specifying columns that **already exist**
    to restructure that information across new columns. Therefore, we do
    not need to use quotation marks.
-   For `pivot_longer`, we are specifying **new columns** to restructure
    the information into. Therefore, we need to use quotation marks.

For this Activity (and in STA 418/518) we will use `pivot_longer` and
`pivot_wider`.

## ☑️ Task 1: The Workflow

**You may need your PAT that you created in Activity 1**. If you
misplaced this token, you will need to create a new one prior to
beginning the steps below. You can do this by going back to your
Activity 1 repo and look at Task 4 or go to my repo’s [Task
4](https://github.com/gvsu-sta518/activity01-rmarkdown#%EF%B8%8F-tasks-4-connect-rstudio-and-github).

Remember to take these steps slowly, help each other out, and get a hold
of your instructor when you have questions or issues.

1.  In this GitHub repo, click on the ![fork](README-img/fork-icon.png)
    **Fork** icon near the upper-right-hand corner. You should be taken
    a copy of this repo that is in your GitHub account - your page title
    should be `username/activity06-pivoting`, where `username` is
    replaced with your GitHub username.
2.  Click on the green **Code** button.

-   Verify that the drop-down identifies that you are using the
    **HTTPS** method (this is *probably* the default view; otherwise,
    select “HTTPS”).
-   Click on the ![clipboard](README-img/clipboard-icon.png) icon to
    copy the repo HTTPS information.

3.  Log in to the [RStudio Workbench](https://rstudio.gvsu.edu/).

-   Verify that you are in an RStudio session (it doesn’t matter if it
    is a previous Project session or a “vanilla” RStudio session).

4.  Create a new Project. You can do this by clicking on the
    <img src="README-img/new-project-icon.png" alt="new project" width = "20"/>
    icon or through the menus (File > New Project…).

-   In the *New Project Wizard* pop-up, select **Version Control** on
    the *Create Project* screen, then select **Git** on the *Create
    Project from Version Control* screen.
-   On the *Clone Git Repository* screen, paste the HTTPS information
    from (2) into the *Repository URL* dialog box. It should look like:
    `https://github.com/username/activity06-pivoting.git`
-   The *Project directory name* dialog box should automatically
    populate with your repository name, but sometimes Macs have an issue
    with this (if so, click into this box and press the ![command
    key](README-img/command-key-icon.png) command key on your keyboard).
    It should look something like: `activity06-pivoting`
-   In the *Create project as subdirectory of* dialog box, click on
    **Browse**.
-   In the *Choose Directory* pop-up, navigate to your class-level
    folder (i.e., you were encouraged to create a folder named either
    `STA418` or `STA518`) You were also encouraged to create
    an`activities` folder within your class-level folder to help
    organize our materials. Once you have navigated to the folder you
    wish this repo to be located, click **Choose**.
-   Verify that the *Create project as a directory of* dialog box
    contains the folder location that you previously specified, then
    click on **Create Project**.
-   You may be asked to login with your GitHub credentials on a *Clone
    Repository* pop-up window. Provide your GitHub username and PAT (not
    your GitHub password) if prompted.

6.  After a few seconds, your RStudio session will refresh and you
    should be in your newly created RStudio Project!

Note that beginning in Activity 7, I will be no longer provide these
full steps and will instead be saying:

> ![fork](README-img/fork-icon.png) **Fork** this repo and clone it to a
> new [RStudio Project](https://rstudio.gvsu.edu/).

Remember that more detailed directions are provided in this Activity - I
will note/link this in activities after this switch.

<img src="README-img/noun_pause.png" alt="pause" width = "20"/>
<b>Planned Pause Point</b>: If you have any questions, contact your
instructor or another group.

## ☑️ Task 2: Complete the RMarkdown File

The `activity06-pivoting.Rmd` file contains the directions for this
activity. For the rest of this class period, you will complete the
RMarkdown document with your neighbor(s). Your instructor will be
circling and be available to help when needed.

Note that each person is working in their own repo. We are not worrying
about collaborating for the time being and instead will be working on
being more comfortable with the workflow for working between RStudio and
GitHub.

However, do not continue in this README document until you and your
neighbor(s) have completed your `.Rmd` files.

![Ross from the TV show FRIENDS yelling “Pivot!” while trying to move a
couch up a set of
stairs](https://media.giphy.com/media/oCjCwnuLpiWbfMb1UA/giphy.gif)

## ☑️ Task 3: Reflection

Take 5 minutes to draw a concept map that connects what you have learned
about `pivot_longer` and `pivot_wider`. For example, here is a concept
map for `dplyr::select`:

![RStudio concept map for the select function from the dplyr package in
R](https://raw.githubusercontent.com/rstudio/concept-maps/master/en/select.svg)

**Next**: Activity 7 will focus on combining information from multiple
datasets as well and creating maps!
