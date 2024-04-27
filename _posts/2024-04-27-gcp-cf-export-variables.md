---
layout: post
title: "GCP - Cloud Function - Export variables"
categories: gcp
tags: cloudfunction
---

1. It´s a script to export Cloud Function variables.

```shell
#!/bin/bash

environment="{environment}"
project_id="{project_id}"

functions_name_list=("cf-a" "cd-b" "cf-c" "cf-d")
echo "==================================================================="
echo "                        AMBIENTE - "$environment"                             "
echo "==================================================================="
for function_name in ${functions_name_list[@]}
do
  echo "FUNCTION_NAME: "$function_name

  # Get Cloud Function variables
  VARIABLES=$(gcloud functions describe $function_name --project=$project_id --format='yaml(serviceConfig.environmentVariables)')
  
  # Export variables
  echo "$VARIABLES" > ../$environment/$function_name.txt
  
  echo "EXPORTED"
  echo "-------------------------------------------------------------------"
done
echo "==================================================================="

```
