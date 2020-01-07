# Deployment

## Getting Started

To begin the demo you'll need to do a few things which are described in the TTT video:

1. Execute a cloud shell
2. Download the [create-db.sh](https://github.com/microsoft/ignite-learning-paths-training-mod/blob/master/mod10/create-db.sh) script.
3. You'll need the presentation deck, get the latest from the [presentations.md](presentations.md)

We'll use these to prep before we go into the session.  Fully build the application at least before the session. Always keep a preview copy ready to go and build what you can as a demonstration live.  You will demonstrate building the databases live, but well remind the audience we're using "cooking show rules."  You will show the process of creating these databases.

Once you've prepped the app - you're going to build the same app live using the pre-created database information, an incremented name of the app from the one you've created for the demo.

You'll be creating the application twice... once completely before the session (just run the create databases script, create the VM and then exectue bash deploy.sh

IE: My pre-show demo 

```
az group create --subscription "Ignite The Tour" --name ignitemod10 --location eastus
```

What I will create live: resource group creation notes in [hints-for-presentation.md](hints-for-presentation.md)

```
az group create --subscription "Ignite The Tour" --name 001ignitemod10 --location eastus
```

The incremented name is just to keep it easy to follow.

---

## Creating Resource Group and Databases.

Within [create-db.sh](https://github.com/microsoft/ignite-learning-paths-training-mod/blob/master/mod10/create-db.sh) there are a few bash variables to change.

```
#!/bin/bash
set -e

# Credentials
azureResourceGroup=ignitemod10
adminUser=twtadmin
adminPassword=twtmod10pD
subname=cd400f31-6f94-40ab-863a-673192a3c0d0
location=eastus

# DB Name

cosmosdbname=apps30twtnosql
sqldbname=apps30twtsql
```

I do the same incrementing of the name for the "live" version.  I create these before hand but then demonstrate how to create from portal.  The versions I do from portal I do not "deploy" - before I "create and deploy" I explain for time we've already created our DB's with Azure SQL and Cosmos DB.

Example:

Live Version - 

```
#!/bin/bash
set -e

# Credentials
azureResourceGroup=ignitemod10
adminUser=example
adminPassword=examplesjefkjdkj
subname=2348283-example-398349839
location=eastus

# DB Name

cosmosdbname=001apps30twtnosql
sqldbname=001apps30twtsql
```

Once you've edited the script lets run it in bash Cloud Shell and begin process of building demo.

```
bash create-db.sh
```

This should take about 15 minutes for both DBs to create.

Collect both connection strings to put in the VARs for the container to connect to the database.

## Next Steps

Go through the opening of the talk with the application fully built in the background.  Keep two portals up, one with the "complete" version of the app, one of the resource group you're going to build live.  You'll want to show them the difference and how you're creating the resources live as you're explaining each part.
