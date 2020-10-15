
# Valtech - Connecting the dots SQL
Welcome to Valtech connecting the dots SQL Project

All datatransformation (from raw to analysis & report-ready data) happening inside BigQuery is defined inside this project.


## Prerequisites:

- **Python 3.7.5 (other version above 3.6 most probably works)**
- Understanding of the terminal
- Understanding of virtual environments in Python
- Basic understanding of DBT.

If you're new to DBT, walk through this guide to get a basic understanding before jumping into this project:
https://docs.getdbt.com/tutorial/setting-up/

For an introduction to virtual environments and some opinions on how your local environment should be set up. Please see this post:
https://medium.com/@maxkrog/my-local-environment-setup-for-data-engineering-on-gcp-5611e78aa28

## Local setup:

There's two parts to setting up this project locally
1. Setting up your dbt profile in ~/.dbt/profiles.yml
2. DBT Project setup
More on these two setups below.

#### DBT Profile
The first part of setting up this project locally is to provide your own dbt-profile to be used by the project. Your DBT profile should be put in ~/.dbt/profiles.yml
An example setup of this file looks like below.
An example file named 'example_profiles.yml' exists in the root of this project.
To initialize it:
1. Copy the example profile to ~/.dbt/profiles.yml
2. Update the keyfile variable to point to a service account json key

####  DBT Project
This assumes some knowledge about virtual environments (venv).
More info about venv can be found here: https://docs.python.org/3/tutorial/venv.html

If you're used a DBT-folder before and just need to a quickstart, these are the steps to follow from your terminal. Make sure your terminal is in the root folder of this project before executing the commands.

    python -m venv venv                 # Creates a folder 'venv'
    source venv/bin/activate            # Jumps inside the virtual environment

    pip install -r requirements.txt     # Installs relevant packages (dbt) to the virtualenvironment
    dbt deps 							#Fetches dbt dependencies defined in packages.yml

    ...do work...

    deactivate                          # Deactivates (takes you out of) the virtual environment

Note that when you've left (deactivated) the venv and want to enter it again, you do not need to install pip packages again. They are saved in the venv-folder.


## Working inside the project

### Some useful DBT commands:
    dbt deps 	# Fetches dbt dependencies from dbt-hub to the folder dbt_modules
    dbt clean 	# Cleans folder defined in
    dbt run 	# Runs all models defined in /models
    dbt run --models=linkedin_source.stg_linkedin__account_history #Runs one specific model




### DBT Resources:
- Learn more about dbt [in the docs](https://docs.getdbt.com/docs/introduction)
- Check out [Discourse](https://discourse.getdbt.com/) for commonly asked questions and answers
- Join the [chat](http://slack.getdbt.com/) on Slack for live discussions and support
- Find [dbt events](https://events.getdbt.com) near you
- Check out [the blog](https://blog.getdbt.com/) for the latest news on dbt's development and best practices
