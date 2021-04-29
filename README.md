<!-- ## Quick introduction of RIM microscopy

<!--(Le software ci-dessous est en lien avec le papier... DOI -->

# Tutorial for AlgoRIM Interface (Under construction 🛠️)

## Mailing list

Join the project mailing list by sending an email to claire.estibal@univ-tlse3.fr with the subject line "Join RIM project mailing list" to be informed of the release of new versions and key stages of the project. You can unsubscribe at any time by sending an email with the subject line "Leave RIM project mailing list".

## Conditions of use

You are free to use this software **for research purposes only**, but **you must not transmit and distribute it without our consent (See contacts list)**.  

In addition, you undertake **to include a citation (<!-- Mangeat et al., Super-resolved live-cell imaging using random illumination microscopy, Cell Reports Methods (2021),
https://doi.org/10.1016/j.crmeth.2021.100009 --> )** whenever you present or publish results that are based on it.   

The CNRS makes no warranties of any kind on this software and shall in no event be liable for damages of any kind in connection with the use and exploitation of this technology. 

## Download AlgoRIM

Latest version AlgoRIM V1.1 (20/04/21)  
https://github.com/teamRIM/tutoRIM/raw/main/bin/AlgoRIM_V1_1_2_installer.exe

> ### Prerequisite to install AlgoRIM interface
>
> * Internet connection
> * Administrator rights on the computer (In some instances the antivirus try to prevent the installation)
> * Windows operating system (Tested on : Windows 10)  

## Example of use with our datasets

1. First of all, start the download of AlgoRIM. If this is your first time installation this operation may take several minutes. Don't forget to add a shorcut to your desktop.   
2. On your computer, create a folder named "AlgoRIM_Dataset" and a subfolder named "RAW_DATA" in it,  in order to be able to fill them with our dataset given as an example. 
3. Our dataset is on the "data" folder at the top of the Github page.
4. Download PSF files in "AlgoRIM_Dataset" folder and ROI1_SUM_image_43_800.tif in "RAW_DATA" folder.
5. Once your installation is complete, open AlgoRIM interface.
6. *Images from:* Click on "Other".
7. *Input data:* Raw data folder is selected.
8. *Select:* Select "RAW_DATA" folder.
9. *PSF emission:* Select PSF256_520nm.tif.
10. *PSF excitation:* Select PSF256_405nm.tif.
11. *Image expansion factor:* 2
12. *PSF expansion factor:* 1
13. *Regularization parameter:* 0
14. *Number of iterations:* 16
15. *Pre-filtering parameter:* 0.008. You can click on the "Adjust" button to adjust it.
16. You can click on "Launch preview" button. The first launch is always a little longer because AlgoRIM detects the calculation parallelization possibilities of your computer.
17. Use the "STOP" button if you don't want to wait until the end of the iterations.
18. Click on "Launch" button.
19. This will create a reconstruction folder next to your "RAW_DATA" folder, with the reconstructed image in it.

## How to use the interface

> ### 1. Specify where your data comes from
> 
> * Micromanager or compatible format (image matrix containing n raw speckle) : No prerequisite on the name of the channels but they will not be differentiated. (see example of micromanager files used in the paper)
> * Inscoper: channel 0 is identify with 'c0' in the image name and channel 1 with 'c1'
> * Abbelight: the image name begins with 'ROI2' or 'ROI1', depending on the channel
> 

> ### 2. Managing Input data
> * **'Global folder' mode:** With this mode you can launch several reconstructions by selecting a folder containing several projects. It is based on Inscoper's raw image backup mode: global_folder/sub_folder/images/RAW_DATA/. If you want you launch preview, you need to select precisely the raw data folder you want to launch preview on.
> * **'Raw data folder' mode:** With this mode you can launch reconstruction on one folder containning several .tif files.  
<!---
> * **'Only 1 file (Stream)' mode:**  With this mode you can launch reconstruction on one .tif file. You can set the number of raw images per reconstructed image ('Speckles per sequence'). These sequences can be overlaped to improve time resolution and denoising.--->   

> ### 3. Select folder<!--/file-->

> ### 4. Adjust <!--optical--> parameters <!--from your microscope-->
> * **PSF emission:** You can determine this PSF experimentally at the emission wavelength.  
> <!--How to inject the good emission experimental PSF ? link psf extractor.-->
> 
> * **PSF excitation:** You can use the free software *'PSF generator'* to generate this PSF at the excitation wavelength. As an alternative you can use the emission PSF.
> <!--How to inject the good PSF from simulation ? link psf generator -->
> 
> * **Image expansion factor:** pixel physical size of the output reconstruction image.  
> * **PSF expansion factor:** pixel physical size must be the same as for the final image after reconstruction.  
> * **Number of iterations:** You can adjust this setting using preview mode.  
> * **Pre-filtering parameter(Wiener):**  You can adjust this parameter with the adjust button and preview mode.
> * **Regularization parameter:**  

> ### 5. Launch preview
> This mode allows you to preview the reconstruction result on the first raw image. If you want to interrupt it, please use the stop button.  

> ### 6. Launch reconstruction
> This mode starts the reconstruction and saves your results in a folder named according to your settings.  


## Contacts list

Distribution request:
* simon.labouesse@gmail.com
* thomas.mangeat@univ-tlse3.fr

Technical support:
* claire.estibal@univ-tlse3.fr

## Contributors

* Simon Labouesse (AlgoRIM development and implementation)
* Claire Estibal  (AlgoRIM interface development)
* Thomas Mangeat  (Methodological part for biological reconstruction and imaging workflow)
* Anne Sentenac   
* Jérôme Idier    
* Marc Allain

