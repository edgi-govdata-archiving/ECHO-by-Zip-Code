# **IMPORTANT! We've moved development of this repo to the `main` branch. You will not be able to merge changes into `master`.**

## **UPDATING LOCAL CLONES**

(via [this link](https://www.hanselman.com/blog/EasilyRenameYourGitDefaultBranchFromMasterToMain.aspx), thanks!)

If you have a local clone, you can update and change your default branch with the steps below.

```sh
git checkout master
git branch -m master main
git fetch
git branch --unset-upstream
git branch -u origin/main
git symbolic-ref refs/remotes/origin/HEAD refs/remotes/origin/main
```

The above steps accomplish:

1. Go to the master branch
2. Rename master to main locally
3. Get the latest commits from the server
4. Remove the link to origin/master
5. Add a link to origin/main
6. Update the default branch to be origin/main


# ECHO by Zip Code
A Jupyter Notebook-based exploration of emissions permits, compliance, and enforcement designed for localization by zip code

[![Code of Conduct](https://img.shields.io/badge/%E2%9D%A4-code%20of%20conduct-blue.svg?style=flat)](https://github.com/edgi-govdata-archiving/overview/blob/master/CONDUCT.md)

---
## Try it out!

See a static sample report [here](https://htmlpreview.github.io/?https://github.com/edgi-govdata-archiving/ECHO-by-Zip-Code/blob/main/echo-by-zip-demo.html). This demo won't let you look at different locations, it's just a quick sample!

### Link to Jupyter Notebook
[Here](https://colab.research.google.com/github/edgi-govdata-archiving/ECHO-by-Zip-Code/blob/main/echo-by-zip.ipynb)'s the demo where you can modify the location & see new results. Follow the instructions for Google Colab below:

### Running the notebook in Google CoLab
* Go to [the CoLab page for the notebook](https://colab.research.google.com/github/edgi-govdata-archiving/ECHO-by-Zip-Code/blob/main/echo-by-zip.ipynb)
* Set `my_zip` in the code to the zip code you're interested in
* In the "Runtime" menu, click "Run all"

## Running the notebook locally
### Quickstart
You need:
* Python
* Jupyter Notebook
* [ECHO exporter data](https://echo.epa.gov/tools/data-downloads#exporter), unzipped and added to the `data` folder (should be a .csv and a .xlsx)
* Python libraries as shown in the notebook

Run `jupyter notebook` in the project repo to start the notebook.

### Setup for beginners
#### Getting set up with the programming tools
In this section, we will install the programming language Python, and use its package manager "pip" to install Jupyter Notebook.

* If you've never used the command line/terminal before, you might find it helpful to try this [one-page tutorial](https://tessel.github.io/t2-start/cmd.html)
* Install Python on your computer: [Python download page](https://www.python.org/downloads/)
* Python should come with its package manager `pip` pre-installed. Type `pip` into the command line and press enter just to check.
![Screen Shot 2020-02-06 at 3 38 15 PM](https://user-images.githubusercontent.com/454690/73988245-ec30d780-48f6-11ea-88a7-529d876f360a.png)
If it gives you an error message, you may need to debug. Here are some options:
  * Quit and re-open your terminal; try again
  * Restart your computer; try again
  * Run `sudo easy_install pip` in the command line; try again
  * Copy and paste your error message into a search engine and see what else you can try
* Use `pip` to install [Jupyter Notebook](https://jupyter.org/install): run `pip install notebook`

Hopefully, you should now be able to run `jupyter notebook` in the command line. If it's working, it will open your browser and show you all the files in your current directory.

![Screen Shot 2020-02-06 at 3 39 26 PM](https://user-images.githubusercontent.com/454690/73988242-eaffaa80-48f6-11ea-90ed-24f15b91b97f.png)

#### Getting this repo onto your computer
You will need to install `git`, which is a version control system that's designed for multiple people to be able to work with the same repo: [Git download page](https://git-scm.com/downloads). You can test whether it worked by running the command `git` in the command line.

![Screen Shot 2020-02-06 at 3 38 32 PM](https://user-images.githubusercontent.com/454690/73988244-eb984100-48f6-11ea-81f6-e91ae7cd31aa.png)

Choose where on your computer you want this project to go (`Documents`, for example). In your command line, use `cd` to navigate to the folder where you want to save the project.

Now "clone" the repo (copy all of the files from the online repository to your computer) by running:

`git clone https://github.com/edgi-govdata-archiving/ECHO-by-Zip-Code.git`

Once the process completes, navigate into the cloned repo folder:

`cd echo-by-zip-code`

If you run `jupyter notebook` from here, it should open your browser and there should be a file called `echo-by-zip.ipynb`. Click to open!

![Screen Shot 2020-02-06 at 3 33 53 PM](https://user-images.githubusercontent.com/454690/73987763-4bdab300-48f6-11ea-95dc-ce467a117735.png)

![Screen Shot 2020-02-06 at 3 34 07 PM](https://user-images.githubusercontent.com/454690/73987762-4b421c80-48f6-11ea-8cfe-4e27d4b9d1c4.png)

### Getting the data
The data we are using is not a part of the repo. (It could be, but isn't in order to keep the repo small.) You will need to download it separately.

Download the ZIP file from [ECHO Exporter](https://echo.epa.gov/tools/data-downloads#exporter) on the ECHO Data Downloads page.

![Screen Shot 2020-02-06 at 3 34 41 PM](https://user-images.githubusercontent.com/454690/73987758-4aa98600-48f6-11ea-869b-422db8507cea.png)

Unzip the file and move its contents into the `data` folder of your local copy of this repo. It should look like:

`echo-by-zip-code/data/ECHO_EXPORTER.csv`

(You can put the xlsx file there too, but the code doesn't depend on it. It's a useful file to keep around.)

### Installing libraries

When you open the Jupyter notebook, there will be a little code block near the top with the comment `# Import libraries`.

This code block names the different libraries (packages of many specialized functions for e.g. mapping things or manipulating data) that the notebook is using:

![Screen Shot 2020-02-06 at 3 34 19 PM](https://user-images.githubusercontent.com/454690/73987761-4b421c80-48f6-11ea-9b15-cc39e34f51f4.png)

For each line with an `import` in front of it, you will need to install a library using the command line.

Open a new window of your terminal, then for each library, install with:

`pip install <library>`.

For example, since there is a line that says `import pandas as pd` in the notebook, enter

`pip install pandas`

into the command line.

### Using the notebook
Now that the notebook is running and you have the data & libraries installed, you should be able to run it!

Back in the notebook, you can either click the button that says "Run" to run one cell at a time, or hit "Run All" in the "Cell" menu to run the whole notebook.

![Screen Shot 2020-02-06 at 3 49 56 PM](https://user-images.githubusercontent.com/454690/73988710-56964780-48f8-11ea-9828-bac90e047058.png)

It might take a minute to process all that data! When it's done, you should see some maps and graphs about the ECHO permits in the specified zip code area.

Change the zip code in the code as `my_zip` to your own zip code and run the notebook again to see a report for your area:

![Screen Shot 2020-02-06 at 3 52 03 PM](https://user-images.githubusercontent.com/454690/73988794-a37a1e00-48f8-11ea-8d13-9acb7321aed2.png)

## Default branch - 'main'
The 'master' branch is no longer the repo's primary branch in line with EDGI's policy decided here: https://github.com/edgi-govdata-archiving/overview/issues/241

> If someone has a local clone, they can update their locals like this:
```
$ git checkout master
$ git branch -m master main
$ git fetch
$ git branch --unset-upstream
$ git branch -u origin/main
$ git symbolic-ref refs/remotes/origin/HEAD refs/remotes/origin/main
```
> The above steps accomplish:
> - Go to the master branch
> - Rename master to main locally
> - Get the latest commits from the server
> - Remove the link to origin/master
> - Add a link to origin/main
> - Update the default branch to be origin/main

(From @jywarren at Public Lab: https://github.com/publiclab/plots2/issues/8077)

---


## License & Copyright

Copyright (C) <year> Environmental Data and Governance Initiative (EDGI)
This program is free software: you can redistribute it and/or modify it under the terms of the GNU General Public License as published by the Free Software Foundation, version 3.0.

This program is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.

See the [`LICENSE`](/LICENSE) file for details.
