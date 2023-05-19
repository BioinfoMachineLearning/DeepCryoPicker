# DeepCryoPicker
This is the python implementation of the original DeepCryoPicker for picking single protein particles in cryo-EM images. 

# Abstract
Cryogenic electron microscopy (cryo-EM) has revolutionized the determination of protein structures. However, the computational reconstruction of these protein structures remains a challenging task, hindered by the diversity of particle shapes and the extremely low signal-to-noise ratio of micrographs.. Human intervention is often required to create a high-quality set of particles, a process which is time-consuming, error-prone, and requires extensive manual annotation.

We propose DeepCryoPicker, a fully automated, unsupervised approach for single particle picking in cryo-EM micrographs. Our solution involves three stages: image preprocessing, particle clustering, and particle picking. Image preprocessing techniques, including image averaging, normalization, contrast enhancement correction, histogram equalization, restoration, adaptive histogram equalization, guided image filtering, and morphological operations. These steps have shown to significantly improve the cryo-EM image quality, allowing for more accurate clustering and picking. The particle clustering stage leverages an intensity distribution model, which has outperformed traditional methods like K-means and Fuzzy C-Means in speed and accuracy for our task. Particle picking employs image cleaning and a region-based method that identifies connected regions in the processed image and encapsulates the particles within bounding boxes. This

approach, aided by earlier preprocessing steps, effectively distinguishes between protein particles and background noise, providing a more precise selection of particles.
DeepCryoPicker will autonomously identify protein particles in cryo-EM micrographs, eliminating the need for human intervention or labeled training data. This breakthrough has the potential to greatly expedite and improve the accuracy of cryo-EM protein structure determination.

# Workflow Chart
![image of flow](https://github.com/BioinfoMachineLearning/DeepCryoPicker/assets/58675459/029a5a9c-cabe-4df0-81d8-0fd376ab6837)

# Preprocessing results
![fig12](https://github.com/BioinfoMachineLearning/DeepCryoPicker/assets/58675459/b9731b49-5c20-439b-806d-f9a003a0202a)


# Data Sets
Contains the Data Sets that were used in the building and testing of this project. These include the Raw Data apoferritin, Beta-galactosidase, KLH, and 80S Ribosome. These are just a selct few samples from the much larger data set that can be found here:

    "EMPIAR-10146"- Apoferritin - https://www.ebi.ac.uk/pdbe/emdb/empiar/entry/10146/#&gid=1&pid=1
  
    EMPIAR-10017-Beta-galactosidase - https://www.ebi.ac.uk/pdbe/emdb/empiar/entry/10017/
  
    KLH Dataset - http://nramm.nysbc.org/
  
    EMPIAR-10028-80S ribosome - https://www.ebi.ac.uk/pdbe/emdb/empiar/entry/10028/
  
 Processed, clustered and output folders will be output into 'Data Sets' locally when running the notebooks. They were not included in this repository to save space
 
 # Notebooks
 Contains all the notebooks used in this project. Each will need to be started manually
 
     Archive - contains old versions of several notebooks

     Clustering - Custom - our custom IBC approach, clusters pixels based on their intensity

     Clustering - FCM - clusters using the common FCM algorithm

     Clustering - K Means - clusters using the common k-means algorthim

     Particle Picking - binary mask cleaning and region detection for identifying particles in clustered images

     PreprocessingV2 - preprocessing of .mrc or .png images (Note: this not book takes up to 90 min to run)

 To completly run this program, run all cells in the following order:
 
    PreprocessV2 -> Clustering - Custom -> Particle Picking
 
# Report and Presentations
contains the written report for this project in pdf and docx format, also contains the poster presentation that was presented at the undegraduate reseach fair fall 2022 and spring 2023 at mizzou

# Utility Programs
contains various notebooks and scripts that were used when developing these notebooks, they are not necessary but may be usefull in the future

# Previous models and version
This project was based on previous matlab versions of this architecture. These previous models can be found here:

    DeepCryoEM - https://github.com/jianlin-cheng/DeepCryoEM

    DeepCryoPicker: Fully Automated Deep Neural Network for Single Protein Particle Picking in cryo-EM. https://link.springer.com/article/10.1186/s12859-020-03809-7

    AutoCryoPicker: an unsupervised learning approach for fully automated single particle picking in cryo-EM images.https://bmcbioinformatics.biomedcentral.com/articles/10.1186/s12859-019-2926-y
 

# Future work
Current implmentation of region detection has much room for improvment, currently there are many false positives and misclassification of regions. These improvments can be made to the binary mask cleaning as well as region detection and filtering. Improvments can also be made in clustering and preprocessing.
