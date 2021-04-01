# Tutorial for AlgoRIM Interface (Under construction 🛠️)

## Conditions of use

You are free to use this software **for research purposes only**, but **you must not transmit and distribute it without our consent (See contacts list)**.  

In addition, you undertake **to include a citation (Mangeat et al., Super-resolved live-cell imaging using Random Illumination Microscopy, Cell Reports Methods, first issue 2021.)** whenever you present or publish results that are based on it.   

The CNRS makes no warranties of any kind on this software and shall in no event be liable for damages of any kind in connection with the use and exploitation of this technology. 

## Download
Latest version AlgoRIM V1.1 (30/03/21)  
https://github.com/teamRIM/tutoRIM/raw/main/bin/AlgoRIM_V1p1.exe


> ### Prerequisite to install AlgoRIM interface
>
> * Internet connection
> * Administrator rights on the computer
> * Windows operating system (Tested on : Windows 10)
> 

> ### 1. Specify where your data comes from
> 
> * Inscoper: channel 0 is identify with 'c0' in the image name and channel 1 with 'c1'
> * Abbelight: the image name begins with 'ROI2' or 'ROI1', depending on the channel
> * Other (ex: Micromanager...): No prerequisite on the name of the channels but they will not be differentiated.

> ### 2. Input data
> * **'Global folder' mode:** With this mode you can launch several reconstructions by selecting a folder containing several projects. It is based on Inscoper's raw image backup mode: global_folder/sub_folder/images/RAW_DATA/. If you want you launch preview, you need to select precisely the raw data folder you want to launch preview on.
> * **'Raw data folder' mode:** With this mode you can launch reconstruction on one folder containning several .tif files.  
> * **'Only 1 file (Stream)' mode:**  With this mode you can launch reconstruction on one .tif file. You can set the number of raw images per reconstructed image ('Speckles per sequence'). These sequences can be overlaped to improve time resolution and denoising.   

## Contacts list

Distribution request:
* simon.labouesse@gmail.com
* thomas.mangeat@univ-tlse3.fr

Technical support:
* claire.estibal@univ-tlse3.fr

## Contributors

* Simon Labouesse (AlgoRIM development and implementation)
* Claire Estibal  (AlgoRIM interface development)
* Thomas Mangeat
* Anne Sentenac
* Jérôme Idier
* Marc Allain

