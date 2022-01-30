# 3D_medical_imaging

I built a piece of AI software that could help clinicians perform this task faster and more consistently. In this project, I focused on the technical aspects of building a segmentation model and integrating it into the clinician's workflow, leaving the dataset curation and model validation questions largely outside the scope of this project.

<b> What I Had Built </b> </br>
In this project I built an end-to-end AI system which features a machine learning algorithm that integrates into a clinical-grade viewer and automatically measures hippocampal volumes of new patients, as their studies are committed to the clinical imaging archive.

Fortunately, I didn't have to deal with full heads of patients. A HippoCrop tool was run which cuts out a rectangular portion of a brain scan from every image series, making my job a bit easier, and the committed radiologists have collected and annotated a dataset of relevant volumes, and even converted them to NIFTI format!

I used the dataset that contains the segmentations of the right hippocampus and I used the U-Net architecture to build the segmentation model.

After that, I proceeded to integrate the model into a working clinical PACS such that it runs on every incoming study and produces a report with volume measurements.

<b>The Dataset</b> </br>
I used the "Hippocampus" dataset from the Medical Decathlon competition. This dataset is stored as a collection of NIFTI files, with one file per volume, and one file per corresponding segmentation mask. The original images here are T2 MRI scans of the full brain. As noted, in this dataset I used cropped volumes where only the region around the hippocampus has been cut out. This makes the size of the dataset quite a bit smaller, the machine learning problem a bit simpler and allows me to have reasonable training times. Algorithms that crop rectangular regions of interest are quite common in medical imaging. Segmentation is still hard.
