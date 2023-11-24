# CBioPortal-Beacon
Beacon v2 API on top of a cBioPortal.

## Container
The singularity container has been created from the beacon.def.

```
sudo singularity build Beacon.sif Beacon.def
```

# Usage

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







