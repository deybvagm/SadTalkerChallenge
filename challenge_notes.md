# Relevant notes

Base repo: https://github.com/OpenTalker/SadTalker

Main challenges introduced in this repo as opposed to the original:
- Create a `POST /predict` API using Flask to make predictions
- The API now handles images/audio when running predictions instead of loading those from the filesystem
- Refactor the code the separate the model initialization from model prediction and also to separate the config

Things not included in this repo so far that are needed:
- Dockerize the repo (Docker, Kubernetes): The idea behind this, is to be able to run the prediction as an independent service, that way if scalability is an issue we can create more replicas of the service. This service is not intended to run alognisde a web service that serve other purpose (preprocessing, saving to DB, running validations, etc), is that is needed then a different service should be created since this have specific hardware requirements to run the model
- Further refactor is needed to get rid of things like `ArgumentParser` still needed by some modules

