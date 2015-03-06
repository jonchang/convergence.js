# Building a better MCMC convergence diagnostic tool

Inspired by <http://danshipper.com/building-a-better-train-to-brooklyn>

## A big list of needs

* I don't want to have to install an app like Tracer or Mesquite
* I want to click on points in the trace plot and see the tree corresponds to that point
* I want to be able to discover "islands" in tree space
* I want to see if my chain is moving between islands in tree space
* I want to be able to see the sliding window of posterior values like AWTY
* I want to see a sliding window of RF distances between trees in my treeset
* The app should detect issues of parameter nonidentifiability (negative correlations)
* I should be able to easily compare prior to posterior distributions
* The app should know when I am trying to detect prior sensitivity and run statistics for that
* The app should help me to generate a prior-only BEAST XML / MrBayes file
* I want to see which parameters / topologies changed between two points on a trace plot
* I want to know how often a particular clade is appearing in my tree set
* I want the option to run this app locally instead of in my browser
* I don't want to be forced to upload my data to someone else's server
* If my computer is slow I want to be able to set up the app on a cluster and let it process files
* I want to be able to generate pretty PDF reports (like Bonsai)
* I want to easily see correlations between my different parameters
* I want to see which tree topologies correlate to posterior values
* The app should help teach what ASDSF, PSRF, ESS, etc. are, whey they're important, and how to use them
* I want to have inline help that tells me what each plot does
* I want a checklist of things to do to assess convergence
* I want a list of papers to read if I want to know more about MCMC diagnostics and statistics
* I should be able to upload only log files, only tree files, or both and get meaningful results
* The app should guide me to the proper procedure for convergence assessment
* I want to click things and tweak slides and see my plots change
* I should be able to compare multiple runs of the same file
* I should be able to compare multiple runs of the same data but with different models
* If I'm often examining a specific set of taxa the tool should remember that list for future analyses
* I should be able to download the raw data for downstream analysis in R and Python
* The plots should be in SVG format so I can import them into Illustrator
* When I load files I want to see progress bars instead of a spinning beachball for minutes
* I want to be reassured that my data aren't being secretly uploaded to the NSA
* The tool should point out potential instances of  porcupine roadkill, fuzzy caterpillars, and city skylines
* I should be alerted to model over- or under-parameterization in the lnL plots
* If I want to hack on the app it should be clear on how to set up a developer instance
* I want to be able to contribute bug fixes and documentation changes
* If I'm a new user I want to know why I should use this app vs Tracer/AWTY/CODA/etc.
* I should be able to export my data in several different formats (CSV, LaTeX, markdown, etc)
* The app should make appropriate use of colors

## My important points

* I have no idea if my trees are converged until I build the consensus tree
* A big blob of trees is hard to interpret
* I don't want to have to install anything
* TreeSetViz requires Mesquite and is slow
* I've never been able to get TreeSetViz to work on anything other than the smallest datasets
* AWTY wants me to uploads my huge trees to their server
* AWTY doesn't like BEAST trees

## Features to build

* Drag and drop tree files
* Big visual of tree distances like TreeSetViz
* Plots of comparesplits like AWTY
* Natively support multiple runs of trees
* "Where do my two runs differ?"
* SVG, PNG, etc. export
* Convergence diagnosis guide
* Click a point and see the tree
* Click a node and see its split in AWTY-clone
