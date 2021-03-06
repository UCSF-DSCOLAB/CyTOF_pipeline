# CyTOF CLustering Optimization aNd Evaluation (Cyclone)

Instructions by Dan are for anyone who wants to help develop this package

# To help develop this package with RStudio:

1. Clone the repo.
2. Try to open the Cyclone/Cyclone.Rproj file.  It should open up RStudio into the Cyclone project which will have build tools set up!  You can also open RStudio and tell it to open the project by navigating to that file.
3. Create a branch, `git checkout -b <name-of-branch>`.
5. Make edits in your branch.
6. Push your branch back to the repo with `git push origin HEAD -u`.
7. Create a Pull Request into the `main` branch, describe your changes in the description.

## Writing Documentation:
I've always used roxygen for documentation management.
It allows for code-based documentation creation which I've found pretty easy to use.
Roxygen documentation gets written right into a packages `.R` files in the `R/` directory, with any lines starting with `#'` being the roxygen lines.
For a normal package, that let's you document functions in the same spot that you define them.
Of course, we won't be doing that exactly here... most of our documentation chunks will be followed by a `NULL`.
**I got a few started already [here](R/checkpoints.R)!**

You can check out [the dittoSeq repo](https://github.com/dtm2451/dittoSeq/tree/master/R) for some of my other examples, or the roxygen2 vignettes [here](https://cran.r-project.org/web/packages/roxygen2/vignettes/roxygen2.html).

### Building the documentation:
How the project is set up, documentation is re-built any time that the `'Build ...'` or `'Check'` actions are made (More on those below). That's what I end up relying on mostly in dittoSeq dev, but you can also use `roxygen2::roxygenise()`, `devtools::build()`, or `Ctrl + Shift + D`!

## Writing the Vignette:
It's an `.Rmd` file in the `vignettes` folder.  Rmd files give a rendered text md format surrounding code chunks that can be controlled with arguments provided to the \`\`\`{r} that they start with.

### Building the vignette:
With the `.Rmd` open, click the `Knit` button in the menu bar of the editor panel. 

## Building / Checking / Installation
Build tools are in the top right panel of RStudio, in the `Build` tab.

The 3 actions I use most often:
- Build a source version of the package with `More > Build Source Package`
- Install from the source version ^^ will build with the `Install and Restart`
- Run Checks: The `Check` button performs lots of tests and is probably what I've relied on most of anything.

To view the documentation yourself, Build, then install, then `?<target_docs>`

To run automated checks which include checks of the documentation, use the Check feature.

I learned by doing and since this is a git repo, we can always undo if something breaks!
