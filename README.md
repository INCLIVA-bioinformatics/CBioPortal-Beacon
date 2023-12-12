# CBioPortal-Beacon
Beacon v2 API on top of a cBioPortal.

## Container
The singularity container has been created from the beacon.def.

```
sudo singularity build Beacon.sif Beacon.def
```

## Usage

Run Beacon. In this case, the default parameters will be used (URL https://www.cbioportal.org/api & study of cBioPortal "acc_tcga"):

```
singularity run Beacon.sif 
```

You can modify this information using the -s and -b parameters, and obtain more information with the -h parameter.

```
singularity run Beacon.sif -h
#Usage: /.singularity.d/runscript [-b cbioportal_url] [-s study_name]
#by default:
#cBioPortal_URL: https://www.cbioportal.org/api
#study_name: acc_tcga
```

For example, to access the study "pcpg_tcga" from the incliva cbioportal (http://193.146.187.14:8080) we can use:

```
singularity run Beacon.sif -b "http://193.146.187.14:8080/api" -s "pcpg_tcga"
```

## Retrieve information
Retrieve your queries by changing the request parameters of the URL:

```
# Base path for genomic variants
http://localhost:5050/api/g_variants

# Base path for individual data
http://localhost:5050/api/individuals

# Base path for biosample data
http://localhost:5050/api/biosamples

# Metadata
http://localhost:5050/api/info
http://localhost:5050/api/map
http://localhost:5050/api/configuration
```

More information about implementation and usage: https://gitlab.bsc.es/impact-data/impd-beacon_cbioportal





