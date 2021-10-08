# Epiforecasts R-universe

![Current status of epiforecasts R-universe](https://epiforecasts.r-universe.dev/badges/:registry)
![Total of packages on epiforecasts R-universe](https://epiforecasts.r-universe.dev/badges/:total)

### Note to @epiforecasts team members

The file [`packages.json`](packages.json) contains a list of packages that will be automatically built and made available on https://epiforecasts.r-universe.dev/, including binaries for the relevant platforms.

You can add any 'package-like' repository in [`packages.json`](packages.json) (e.g., R packages but also R research compendia, bookdown projects, etc.). As long as it can be built with `R CMD build`, it can be added here. Please refer to [the official documentation](https://r-universe.dev/help/) to learn how you can build from a specific branch, specific subfolder or any other non-standard case.

Thanks to R-universe, you can now provide your users with an easy way to install the development version of your packages or projects that are not hosted on CRAN. Instead of recommending `draft` or:

```r
remotes::install_github("epiforecasts/yourproject")
```

you can now either instruct your users to run:

```r
install.packages("yourproject", repos = "https://epiforecasts.r-universe.dev")
```

or to add the `epiforecasts` universe to their `.Rprofile`:

```r
options(
  repos = c(
    epiforecasts = 'https://epiforecasts.r-universe.dev',
    CRAN = 'https://cloud.r-project.org'
  )
)
```

and after a restart, run the regular:

```r
install.packages("yourproject")
```

Please note that as opposed to `remotes` (or `devtools`), installs via R-universe will not automatically detect every new commit as a new version. To make a change available via `update.packages("yourproject")`, you need to increment the version number of your package.
