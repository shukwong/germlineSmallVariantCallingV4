.. _`Input_and_Output`:

Pipeline inputs and outputs
============

Input
-----

In the config folder, please edit the samples.txt to list the aligned BAM files, one on each line. 
We also assume that the BAM file index are in the same directory and are with the name ``<bam_filename>.bai``

samples.txt
-----------
In the config folder, please edit the samples.txt to list the aligned BAM files, one on each line. 
For example:
``bam1.bam
bam2.bam``
Note that if the input files are on google storage please also use ``gs://`` as the prefix. The pipeline uses the prefix to determine whether they are remote files.
Also note that while on-prem/local runs can take advantage of remote files, currently it may cause unexpected errors when multiple tasks try to download the same file into the same location. This will be solved in the next release.

Config file
-----------

Edit config.yaml file accordingly, please note that you need to:
- provide full path to strelka2_glnexus.yml for glnexusConfig if strelka2 is used


Expected Outputs
----------------

Depends on run mode selected in the config, but can include:
Multi-sample VCF called with DeepVariant
Multi-sample VCF called with HaplotypeCaller
Multi-sample VCF called with Strelka2
Multi-sample VCF containing the union of the DeepVariant, HaplotypeCaller and Strelka2 calls