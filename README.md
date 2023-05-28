# Data Science Basic

Basic Data Science Lessons for All!!!

This lesson will based on the following free only courses:

- [Microsoft: Data Science for Beginners](https://github.com/microsoft/Data-Science-For-Beginners)
  10 weeks 20 lessons package...
- [IBM: Python for Data Science](https://cognitiveclass.ai/courses/python-for-data-science)
  20 hours course for beginners, Python and Data Science: Python basic related to data science.
- [IBM: Data Analysis with Python](https://cognitiveclass.ai/courses/data-analysis-python)
  3 hours course for beginners
- [IBM: Data Visualization with Pyton](https://cognitiveclass.ai/courses/data-visualization-python)
  4 hours course for beginners
- [Google: Data Sciense with Python](https://learndigital.withgoogle.com/digitalgarage/course/data-science-with-python)
  8 hours course for advanced users, 13 modules.

## Using Docker Compose for Local Development ##

The repo [Jupyter Docker Stacks](https://github.com/jupyter/docker-stacks) has
a various list of docker images for running Jupyter Notebooks.
It is a very good choice for local development.

Check the page [Select an Image](https://jupyter-docker-stacks.readthedocs.io/en/latest/using/selecting.html)
to select the image you need.
For this course we will use [jupyter/scipy-notebook](https://github.com/jupyter/docker-stacks/tree/main/scipy-notebook).

Set up the docker compose folder.
```bash
mkdir -v ~/rd/myworkshopca/DataScienceBasic/docker

touch ~/rd/myworkshopca/DataScienceBasic/docker/README.md
touch ~/rd/myworkshopca/DataScienceBasic/docker/Dockerfile
touch ~/rd/myworkshopca/DataScienceBasic/docker/docker-compose.yml
```

## lessons

Create the lessons folder
```bash
mkdir -v ~/rd/myworkshopca/DataScienceBasic/lessons
```

01 Defining Data Science
```bash
mkdir -v ~/rd/myworkshopca/DataScienceBasic/lessons/01-defining-data-science
```
