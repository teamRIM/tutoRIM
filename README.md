# Tutorial for AlgoRIM Interface

Welcome to our Github page dedicated to Random Illumination Microscopy images reconstruction!   

**This page is linked to the following publication:**    
Mangeat et al., Super-resolved live-cell imaging using random illumination microscopy, Cell Reports Methods (2021),
https://doi.org/10.1016/j.crmeth.2021.100009

AlgoRIM is our image reconstruction interface allowing to achieve super-resolution based on the properties of the Random Illumination Microscopy (RIM).
**Download AlgoRIM and test it! You will find below a tutorial to guide you step by step.** 

### Data

If you want the images shown in our publication please send an email to thomas.mangeat@univ-tlse3.fr or simon.labouesse@univ-tlse3.fr

### Conditions of use

* You are free to use this software **for research purposes only**, but **you must not transmit and distribute it without our consent (See contacts list)**.  
* In addition, you undertake **to include a citation, Mangeat et al., Super-resolved live-cell imaging using random illumination microscopy, Cell Reports Methods (2021),
https://doi.org/10.1016/j.crmeth.2021.100009**, whenever you present or publish results that are based on it.   
* The CNRS makes no warranties of any kind on this software and shall in no event be liable for damages of any kind in connection with the use and exploitation of this technology. 

## Download AlgoRIM

Latest version (07/01/22) AlgoRIM V1.2 
https://drive.google.com/file/d/1UQFCzHoaEWrVrhQcyTcM3R10Zs_K19k7/view?usp=drive_link

Release notes :
* Better denoising and data normalization
* Less iterations: algorithm converges faster

<!--
Latest version AlgoRIM V1.1 (20/04/21)
https://github.com/teamRIM/tutoRIM/raw/main/bin/AlgoRIM_V1_1_2_installer.exe
-->

#### Prerequisite to install AlgoRIM interface

* Internet connection
* Administrator rights on the computer (In some instances the antivirus try to prevent the installation)
* Windows operating system (Tested on : Windows 10 and 11 pro)  

## Example of use with our dataset

1. Use this link and download all the content: https://drive.google.com/file/d/1UQFCzHoaEWrVrhQcyTcM3R10Zs_K19k7/view?usp=drive_link
2. Unzip the folder.
3. You will find a folder named "data" that contains the file we want to reconstruct for this example and the PSF we need.
4. Start the download of AlgoRIM by clicking on "AlgoRIM_V1_2_installer_web.exe". Follow the process. This operation may take several minutes. Don't forget to add a shorcut to your desktop.
5. Once your installation is complete, open AlgoRIM_V1_2 interface.
6. *Images from:* 'Other'
7. *Input data:* 'Only 1 file (Stream)'
8. *File reconstruction mode:* 'Full file'
9. *Select:* Go in the folder you previously unziped, then in he folder 'data' select 'ROI1_SUM_image_43_800.tif'
10. *PSF emission:* 'PSF256_520nm.tif'
11. *PSF excitation:* 'PSF256_405nm.tif'
12. *Image expansion factor:* 2
13. *PSF expansion factor:* 1
14. *Regularization parameter:* 0.15 <!-- V1_1   *Regularization parameter:* 0 -->
15. *Number of iterations:* 4  <!-- V1_1 *Number of iterations:* 16 -->
16. *Pre-filtering parameter:* 0.05. You can click on the 'Adjust' button to adjust it. <!-- V1_1 *Pre-filtering parameter:* 0.008. -->
17. Make sure that the cutoff frequency matches your system.
18. You can click on 'Launch preview' to start preview. Use the 'STOP' button if you don't want to wait until the end of the iterations.
19. Click on 'Launch' to reconstruct the file.
20. This will create a reconstruction folder in 'data' folder, with the reconstructed image in it.

## How to use AlgoRIM interface

> ### 1. Specify where your data comes from
> *Allow the interface to be able to identify and differentiate your channels.*
> * If you select **Other**: No prerequisite on the name of the channels but they will not be differentiated during reconstruction. You can create a subfolder for each channel and reconstructed them separately.<!-- (see example of micromanager files used in the paper)-->
> * **Inscoper**: channel 0 is identify with 'c0' in the image name and channel 1 with 'c1'
> * **Abbelight**: the image name begins with 'ROI2' or 'ROI1', depending on the channel
> 

> ### 2. Input data
> *Select the type of the input data*
> * **Global folder:** Launch several reconstructions in a row by selecting a folder containing several projects.   
It is based on Inscoper's raw image backup mode: global_folder/sub_folder/images/RAW_DATA/. If you want you launch preview, you need to select precisely the raw data folder you want to launch preview on.
> * **Raw data folder:** Launch reconstruction on one folder containning .tif files.  
> * **Only 1 file (Stream):**  With this mode you can launch reconstruction on one .tif file.

> *Select how to reconstruct the input data*
>  * **Full file:** 1 raw data file => 1 reconstructed file
>  * **Sequential:** Set the number of raw images per reconstructed image.
>  * **Interleaved:** Like the Sequential mode, it divides file in sequences but they are interleaved. The 1st speckle of the n+1 sequence is x speckles after the 1st speckle of the n sequence. x is the gap value. It improves time resolution and denoising.

> ### 3. Select folder ou file
> * Folder must contain raw data files of one or more raw data image.
> * Files must be in .tif format. <!-- and square. -->

> ### 4. Adjust parameters
> **Over-sampling factor:**   
> Raw images are usually recorded with a pixel-size about lambda/(4xNA), with lambda the wavelength of the
   emitted light and NA the numerical aperture of the objective. The super-resolved reconstruction should be
   discretized with a smaller pixel size. The over-sampling factor is the ratio between the pixel size of
   the raw images and the pixel size of the reconstructed (super-resolved) image, e.g., 2 will produce an
   output/reconstructed image with a pixel size that is half the native pixel size of the raw data.   
>   
> Remark: the reconstruction code is based on Fast Fourier Transforms, which are faster if the number of pixels
    along any direction is a power of 2 (128, 256, 512, etc.). Of course this is not mandatory. Images must be square.   
>    
>  **Collection PSF:**   
> PSF of the objective with respect to the  collected light (emitted by the fluorophores). This PSF can be estimated
    experimentally or generated theoretically with a free software like 'PSF generator'.   
>
> The PSF file should be provided in .tif format and the maximum of the PSF should be at the center of the
    image. Beware that this image should be provided with a pixel size corresponding to that of the super-resolved/reconstructed
    image.    
>    
> **Excitation PSF:**   
> PSF of the objective with respect to the illlumination light. This PSF corresponds to the autocorrelation of the
    speckle; it can be generated with a free software like 'PSF generator'. Note that this PSF is not affected
    by any aberration.   
>
> The PSF file should be provided in .tif format and the maximum of the PSF should be at the center of the image.
    This image should be provided with a pixel size corresponding to that of the super-resolved/reconstructed image.
>
> **Number of iterations:**   
> Number of iterative updates in the variance matching algorithm. The early stopping of the iterative scheme is
    producing a Tikhonov-like regularization of the reconstruction. You can adjust this setting with the preview
    mode showing the progression of the reconstructed image over the course of the algorithm.   
>
> **Pre-filtering parameter:**   
> Each raw image is deconvolved using a Wiener filtering. You can adjust this parameter with the adjust button
    in the preview mode.   
>
> ### 5. Launch preview
> This mode allows you to preview the reconstruction result on the first raw image. If you want to interrupt it, please use the stop button.  

> ### 6. Launch reconstruction
> This mode starts the reconstruction and saves your results in a folder named according to your settings.  


## Contacts list

Distribution request:
* simon.labouesse@gmail.com
* thomas.mangeat@univ-tlse3.fr

## Contributors

* Simon Labouesse (AlgoRIM development and implementation)
* Claire Estibal  (AlgoRIM interface development)
* Thomas Mangeat  (Methodological part for biological reconstruction and imaging workflow)
* Anne Sentenac   
* Jérôme Idier    
* Marc Allain

