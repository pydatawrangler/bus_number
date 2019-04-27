Let's get you set up to do **Reproducible Data Science**.

## The Bare Minimum
* `cookiecutter` 
* `conda` (and then python >= 3.6)
* `make`

## Getting Started
1. Install [cookiecutter](https://cookiecutter.readthedocs.io/en/latest/installation.html):
```
conda install -c conda-forge cookiecutter
```
2. Install the `pydata_nyc` branch of `cookiecutter-easydata`:
```
cookiecutter https://github.com/hackalog/cookiecutter-easydata.git \
             --checkout pydata_nyc
```


3. Configure a new project. Call it **bus_number**:
<pre>
project_name [project_name]: <b>bus_number</b>
repo_name [bus_number]: <b>↵</b>
module_name [src]: <b>↵</b>
author_name [Your name (or your organization/company/team)]: <b>Kjell Wooding</b>
description [A short description of this project.]: <b>Reproducible Data Science</b>
Select open_source_license:
1 - MIT
2 - BSD-2-Clause
3 - Proprietary
Choose from 1, 2, 3 [1]: <b>↵</b>
s3_bucket [[OPTIONAL] your-bucket-for-syncing-data (do not include 's3://')]: <b>↵</b>
aws_profile [default]: <b>↵</b>
Select virtualenv:
1 - conda
2 - virtualenv
Choose from 1, 2 [1]: <b>↵</b>
Select python_interpreter:
1 - python3
2 - python
Choose from 1, 2 [1]: <b>↵</b>
</pre>
4. Create your Development Environment
```
cd bus_number
make create_environment
conda activate bus_number         # or `source activate bus_number`
make requirements
git init
git add .
git commit -m "initial import from cookiecutter-easydata"
```
If you encounter an error installing `nbdime` or `nbval`, when you `make create_environment`, edit your `bus_number/environment.yml` file by removing the two lines:
```
  - nbdime
  - nbval
```
Re-save and pick up from `make create_environment`.


That's it! You're ready to go