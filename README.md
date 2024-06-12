# r-package-dev

This is Candace's guide to making R packages that hopefully won't break easily. 

1. Create an R package `devtools::create("myfirstpackage")`
2. Push this to a new github repo. 
3. Copy over GHA tests, PR template, issues templates. Can legit copy this whole folder to your repo: https://github.com/fhdsl/metricminer/tree/main/.github and make a PR for that. 
4. Create a pkgdown set up for docs `usethis::use_pkgdown()`
4. Create a README that will act as your vignette
5. Write out in the vignette what this should look like from the user perspective. 
6. Break up this vignette's workflow into discrete units. 
7. Create a file in `R` folder for each unit and include a "utils.R" that holds things that might be used by multiple files. Develop these in the order that they will be used in the vignette
8. Create a test file for each of these respective units with the same file name for each using `usethis::use_test("filename")`
9. In each R file create documentation first. What is the main goal of the function -- aka if this doesn't work the whole thing is trash. What arguments are there? What are the goals of the functions? Write all this down before even creating code that does it. 
10. Okay now actually write code that works. Start with the most basic needs of the function before writing fringe features. (it can feel tempting to follow side quests DON'T). 
11. After creating a semi-functional function, create a test for it. Think about what are the essentials we need to keep track of to make sure this package is doing what it needs to do? 
12. Once you have the first step working also add it to a new vignette. `usethis::use_vignette("getting_started")`.
