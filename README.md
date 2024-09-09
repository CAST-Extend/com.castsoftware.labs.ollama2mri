# com.castsoftware.labs.ollama2mri

This extension allow to leverage LLM during analyis in order to get functionnal/business/technical summaries of code.


# Problem statement

Application often contains a lot of objects, which make them hard to navigate through. You have to understand the purpose of every single objects in order to able to navigate easily. Even with some coding skills it can be very time-consuming.

# Research Labs Proposal


We leverage LLM during the analysis in order to obtain functionnal process/ business rules and technical step by step summaries of every object of code. It allows to understand quickly and easily the purpose of every object, and so to navigate more easily in the graph of the application. 

# Release Notes
## 1.0.0

Initial release of the extension. This version creates 3 differents summaries for every object.

* LLM_Metrics.LLM_Steps_Extraction : functionnal processes summary
* LLM_Metrics.LLM_Process_Mapping : business rules summary
* LLM_Metrics.LLM_Rules_Extraction : technical summary step by step

# CAST AIP compatibility

This extension is compatible with:

* 8.3.x
* 8.4.x


# Supported DBMS servers

This extension is currently supported on Cast Storage service - which is the default option for CAST AIP -. 

# Prerequisites

* An installation of any compatible release of CAST AIP (see table above)
* Ollama running locally or on a server, with the LLM model, that you want to use, installed

# Bug Fix List

N\/A


# Download and configuration intructions

* Download the extension on Cast Extend
* Go to folder of the extension and open the .env file to configure the extension
- OLLAMA_URL : keep 'localhost' if you're using a local ollama otherwise put the ollama server url
- OLLAMA_MODEL : Put the name of the LLM model that you want to use for summary ( The model has to be installed on ollama)
- DRY_RUN : "True" if you want to only generate summaries in a tmp folder or "False" if you want to generate summaries in a tmp folder AND modify your knowledge_base



# What results can you expect?

## Objects

All the objects with the tag "withcode" will be given 3 properties, each property will have as a value the corresponding code summary of the object. 

## Links

N\/A

## Quality rules

N\/A

## Property

* LLM_Metrics.LLM_Steps_Extraction : functionnal processes summary
* LLM_Metrics.LLM_Process_Mapping : business rules summary
* LLM_Metrics.LLM_Rules_Extraction : technical summary step by step



## Summaries

All the the summaries are stored in the 3 differents files (one for each property) in following folder:
cast-node\/common-data\/upload\/"application_name"\/main_sources\/tmp

If the dry_run is configured in "False", the summaries are also stored, in the knowledge_base.


