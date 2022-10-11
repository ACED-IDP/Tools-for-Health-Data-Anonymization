## To run the command in the docker file

./FHIR/src/Microsoft.Health.Fhir.Anonymizer.R4.CommandLineTool/bin/Release/netcoreapp3.1/publish/Microsoft.Health.Fhir.Anonymizer.R4.CommandLineTool -i ./FHIR/samples/fhir-r4-files -o ./FHIR/samples/fhir-r4-files-output


## Examine the results

```
root@378b3ab98367:/source# jq '.entry[] | select(.resource.resourceType == "Patient") | .resource.identifier[] | .value ' ./FHIR/samples/fhir-r4-files/Antonia30_Ruelas156_fe07e69a-4d6d-4e11-a675-de69f62de5f3.json
"fe07e69a-4d6d-4e11-a675-de69f62de5f3"
"fe07e69a-4d6d-4e11-a675-de69f62de5f3"
"999-40-8244"
"S99970618"
"X74625645X"
root@378b3ab98367:/source# jq '.entry[] | select(.resource.resourceType == "Patient") | .resource.identifier ' ./FHIR/samples/fhir-r4-files-output/Antonia30_Ruelas156_fe07e69a-4d6d-4e11-a675-de69f62de5f3.json
nul

```



