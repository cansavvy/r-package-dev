# r-package-dev

This is Candace's guide to making R packages that hopefully won't break easily. 

## Set up infrastructure
1. Create an R package `devtools::create("myfirstpackage")`
2. Push this to a new github repo. 
3. Copy over GHA tests, PR template, issues templates. Can legit copy this whole folder to your repo: https://github.com/fhdsl/metricminer/tree/main/.github and make a PR for that. 
4. Create a pkgdown set up for docs `usethis::use_pkgdown()`
4. Create a README that will act as your vignette.
5. Write out in the README what this should look like from the user perspective.
   a. what does this R package do?how to install
   b. how to install it
   c. How to run the most basic workflow with it. 
7. Break up the most basic workflow described in the README into discrete units. 
8. Create a file in `R` folder for each unit and include a "utils.R" that holds things that might be used by multiple files. Develop these in the order that they will be used in the vignette
9. Create a test file for each of these respective units with the same file name for each using `usethis::use_test("discrete_unit_name")`
10. File a PR with all this

## Develop a unit 
11. In each R file create documentation first. What is the main goal of the function -- aka if this doesn't work the whole thing is trash. What arguments are absolutely necessary (ignore fringe features right now)? What are the goals of the functions? Write all this down before even creating code that does it. 
12. Okay now actually write code that works. The development cycle is this: 
  a. Write an example code of what should work when you're done.
  b. `devtools::load_all()`
  c. Hard code arguments 
  d. Run it line by line
  d. Once you think its moderately working `devtools::load_all()` and run your example code and see if it worked.
  e. Rinse and repeat steps a - e until you have a working function.
13. File a PR

## Develop a test 
13. Go to your respective unit test file. Write a test for each essential aspect of the function.
14. Then `devtools::check()`
15. Start with the most basic needs of the function before writing fringe features. (it can feel tempting to follow side quests DON'T). 
16. After creating a semi-functional function, create a test for it. Think about what are the essentials we need to keep track of to make sure this package is doing what it needs to do? 
17. Once you have the first step working also add it to a new vignette. `usethis::use_vignette("getting_started")`.
18. File a PR
