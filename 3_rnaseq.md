# Intro to Nextflow processes and workflows using nf-core  RNAseq pipeline




Make usre you are in a persistenet session for this one

```bash 
persistent-sessions start -p ad30 bioedu
ssh bioedu.$USER.ad30.ps.gadi.nci.org.au
```


Check which project you have selected:
```bash 
echo $PROJECT
```

If the project is not ad30 switch project as below:

```bash 
switchproj ad30 
echo $PROJECT
```


now it is time to start the pipeline.  check out the content of the following files

/g/data/ad30/nci_jc.conf


```bash
 nextflow run nf-core/rnaseq -r 3.23.0 -profile test,nci_gadi -c /g/data/ad30/nci_jc.conf --outdir . 

```

while the above is running  check out the content of the following files

/g/data/ad30/nci_jc.conf
https://nf-co.re/configs/nci_gadi/
https://nf-co.re/rnaseq/3.23.0/



Hint: add -resume if the pipeline fails and you want to continue from where you left off