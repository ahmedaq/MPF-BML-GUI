# MPF-BML-GUI

## Table of Contents
*  [Overview](#overview)
*  [Details](#details)
*  [Requirements](#requirements)
*  [Installation](#installation)
*  [Usage](#usage)
*  [Troubleshooting](#troubleshooting)
<!-- *  [Acknowledgement](#acknowledgement) -->

## Overview
MPF-BML-GUI is a standalone cross-platform package which features an easy-to-use GUI. The package only requires the input data (protein sequence data or data of multiple configura-tions of a complex system with large number of variables) and returns the maximum entropy model parameters inferred using the MPF-BML method. 

![alt text][MPFBMLGUI]

[MPFBMLGUI]: https://github.com/ahmedaq/MPF-BML-GUI/blob/master/E2_fig_3.png "MPF_BML_GUI"

## Details
#### Title of paper
MPF-BML: A standalone GUI-based package for maximum entropy model inference
<!-- #### Authors
Ahmed A. Quadeer, Matthew R. McKay, and Raymond H. Y. Louie -->

## Requirements
A PC with either macOS, Microsoft Windows, or Linux.

## Installation
<details>
  <summary>
    <b> macOS </b>
  </summary> 
  
1.	Download the installer "MPF_BML_mcr.zip" from http://bit.ly/MPF_BML_v1_macOS (size: ~1.5 GB) and install the application by following the guidelines in the setup window as follows:
    * Make sure to install MPF-BML-GUI in any folder other than the “Applications” folder (e.g., you can create a new folder on your Desktop or in Documents folder). In this tutorial, we assume that you made a folder “MPF-BML-GUI” in your “Documents folder”. 
    * Do not change the default installation folder ("Applications") of MATLAB runtime libraries.
    * This will install MPF-BML-GUI as well as MATLAB runtime libraries (required to run the app). This procedure may take 2 – 3 minutes on a standard computer.

2.	Open terminal and go to /Documents/MPF-BML-GUI/applications/ directory and type the following command:
    ```
    ./run_MPF_BML.sh /Applications/MATLAB/MATLAB_Runtime/v93/
    ```
      This will open the GUI of the MPF-BML-GUI software.

</details>

<details>
  <summary>
    <b> Windows </b>
  </summary>
  
1.	Download the installer "MPF_BML_mcr" from http://bit.ly/MPF_BML_v1_win (size: ~1 GB) and install the application by following the guidelines in the setup window as follows:
      * Make sure to install RocaNet in any folder other than the “Program Files” folder (e.g., you can create a new folder on your Desktop or in Documents folder). In this tutorial, we assume that you made a folder “MPF_BML_GUI” in your “Documents folder”.
      * Do not change the default installation folder (“Program Files”) of MATLAB runtime libraries. 
      * This will install MPF-BML-GUI as well as MATLAB runtime libraries (required to run the app). This procedure may take 2 – 3 minutes on a standard computer.

2.	Run the installed app by double clicking “MPF_BML_mcr.exe” located in your newly created folder (e.g.,\Documents\MPF_BML_GUI\application\). This will open the GUI of the MPF-BML-GUI software. 
    
    Note that antivirus programs, if installed, may block running the software. If this problem arises (noticed for example in the case of Avast and F-secure antivirus), add the program in trusted applications and then run it.
</details>

<details>
  <summary>
    <b> Linux </b>
  </summary>  

1.	Install the MPF-BML-GUI application as follows:
      * Download the installer "MPF_BML_mcr.install" from http://bit.ly/MPF_BML_v1_linux (size: ~1.8 GB) to a directory on your computer. Here onwards, we assume that you download it in the "Documents" folder.
      * Open terminal and go to the "Documents" folder and type the following command (admin password on user's computer required): 
      ```
      sudo chmod +x MPF_BML_mcr.install
      ```
      * Go to the "Documents" folder, double click on the installer file “MPF_BML_mcr.install”, and follow the guidelines in the setup window.
      * Please make sure to install MPF-BML-GUI in any folder other than the system folders (e.g., you can create a new folder on your Desktop or in Documents folder). In this tutorial, we assume that you made a folder “MPF-BML-GUI” in your “Documents folder”.
      * Install MATLAB Runtime in the directory /Documents/MATLAB_Runtime/.
      * This will install MPF-BML-GUI as well as MATLAB runtime libraries (required to run the app). This procedure may take 2 – 3 minutes on a standard computer.

2.	To run the application, open terminal and go to the directory /Documents/MPF-BML-GUI/application/ and type the following command (admin password on user's computer required): 
      ```
      sudo ./run_MPF_BML.sh /home/UserName/Documents/MATLAB_Runtime/v94/
      ```
      where “UserName” is the name of the directory in which the Documents folder is located. This will open the GUI of the MPF-BML-GUI software.
  
</details>

## Usage

1.	To infer maximum entropy model parameters using MPF-BML, you need to simply provide 
      * Input data in FASTA/Excel format comprising either multiple sequence alignment of the protein or a categorical data (with rows and columns representing samples and variables, respectively) [mandatory input]; 
      * Input file in Excel format for providing different weights to samples in order to reduce any sampling bias (each sample is given the same weight if no data is provided) [optional input];
      * Input file comprising maximum entropy model parameters for initializing the method (see Supplementary Text S1) [optional input].

2.	For testing purposes, you can use the data provided in the Datasets folder in this repository. 

    **IMPORTANT**: The data to be analyzed must be in the same directory where application is installed, e.g., /Documents/MPF-BML-GUI/applications/. 

3.	The inferred maximum entropy parameters using MPF and  MPF-BML are saved in Excel format (see Supplementary Table 2), and the MCMC samples generated based on the inferred MPF-BML model (used in model verification) are also saved in a separate Excel file.
    
4. Vector graphics (eps format) of all results are also saved in the same directory for generating publication-quality figures.

<!-- 
## Acknowledgement

I would like to thank Neelkanth Kundu, Laureano Moreno Pozas, Muhammad Saqib Sohail, Syed Muhammad Umer Abdullah, Syed Faraz Ahmed, and Syed Awais Wahab Shah for providing useful comments/feedback and assisting in testing of RocaNet.
-->

## Troubleshooting

1. Due to the known issue in writing xls/xlsx files in macOS and Linux versions of MATLAB, "xlwrite" function (https://www.mathworks.com/matlabcentral/fileexchange/38591-xlwrite-generate-xls-x-files-without-excel-on-mac-linux-win) was used to write the output files. The function "xlwrite" works for data with small dimensions; however, for large-dimensional datasets, the inferred maximum entropy model parameters are saved in a numeric csv file while the (row/column) labels of the matrix are saved separately in a xls file named "matrixlabels".

2. In macOS version only, the MCMC samples generated based on the inferred MPF-BML model (used in model verification) are not currently being saved. We are in the process of debugging this issue.


For any further questions or comments, please email at ahmedaq@gmail.com. 
