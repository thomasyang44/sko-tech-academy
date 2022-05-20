# 2022 SKO Tech Academy - Business Automation 

## 1. Goal
The general aim of this advanced training is to make the technical sellers PoT/PoC ready for the portfolio. At the end of this training, the technical sellers should be able to take a customer problem, use their knowledge of the portfolio, then plan, define and execute the PoC/PoT using the components in the portfolio.

## 2. Statement of Approach
Attendees are expected to grow deep skills across the CP4BA portfolio including RPA and Process Mining.  Each attendee will be placed in teams with a mix of capability specific skills and are expected to select labs that will build their capability skills where they need the most depth. 

## 3. Learning Objectives
After this event, tech sellers should be able to do a POC targeting a customer use case.   

* Individually, install CP4BA starter pattern (advanced attendees to use production pattern)
* As a team:
    * Deploy seven prebuilt artifacts (ADS, Workflow, etc...) on a cluster
    * Integrate and test deployed artifacts
    * Rebuild selected artifacts (ADS, Workflow, etc...), likely one capability per team member
    * Learn how to effectively demonstrate the client onboarding demo that spans across the Cloud Pak for Business Automation (CP4BA)

All the content is visible [as a BOOK format here](https://thomasyang44.github.io/sko-tech-academy/).  

### Building this booklet locally

The content of this repository is written with markdown files, packaged with [MkDocs](https://www.mkdocs.org/) and can be built into a book-readable format by MkDocs build processes.

1. Install MkDocs locally following the [official documentation instructions](https://www.mkdocs.org/#installation).
1. Install Material plugin for mkdocs:  `pip install mkdocs-material`
2. `git clone https://github.com/thomasyang44/sko-tech-academy` _(or your forked repository if you plan to edit)_
3. `cd sko-tech-academy`
4. `mkdocs serve`
5. Go to `http://127.0.0.1:8000/sko-tech-academy` in your browser.

### Building this booklet locally but with docker

In some cases you might not want to alter your Python setup and rather go with a docker image instead. This requires docker is running locally on your computer though.

* docker run --rm -it -p 8000:8000 -v ${PWD}:/docs squidfunk/mkdocs-material
* Go to http://127.0.0.1:8000/ in your browser.


### Automatic deployment on github

This project includes a `.github` folder to define a git action workflow to build the pages when content is pushed to github.

## Contributors
* Lead content developer [Gerry Baird](https://www.linkedin.com/in/gerry-baird-a644524/)
* Lead content developer [Thomas Yang](https://www.linkedin.com/in/thomasyang44/)
