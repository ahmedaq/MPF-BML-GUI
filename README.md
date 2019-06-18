# MPF-BML-GUI

&nbsp;
## Table of Contents
*  [Overview](#overview)
*  [Details](#details)
*  [Requirements](#requirements)
*  [Installation](#installation)
*  [Usage](#usage)
*  [Acknowledgement](#acknowledgement)
*  [Troubleshooting](#troubleshooting)

&nbsp;
## Overview
MPF-BML-GUI is a standalone cross-platform package which features an easy-to-use GUI. The package only requires the input data (protein sequence data or data of multiple configura-tions of a complex system with large number of variables) and returns the maximum entropy model parameters inferred using the MPF-BML method. 

![alt text][MPFBMLGUI]

[MPFBMLGUI]: https://github.com/ahmedaq/MPF-BML-GUI/blob/master/E2_fig_3.png "MPF_BML_GUI"

&nbsp;
## Details
#### Title of paper
MPF-BML: A standalone GUI-based package for maximum entropy model inference
<!-- #### Authors
Ahmed A. Quadeer, Matthew R. McKay, and Raymond H. Y. Louie -->

&nbsp;
## Requirements
A PC with either macOS, Microsoft Windows, or Linux.

&nbsp;
## Installation
<details>
  <summary>
    <b> macOS </b>
  </summary>  
&nbsp;

RocaNet can be installed using one of the following methods on macOS:

#### Method 1: Downloading MATLAB Runtime separately and running directly the RoCA app without any installation

1. Download and install the Macintosh version of the MATLAB Runtime for R2017b from the following link on the MathWorks website http://ssd.mathworks.com/supportfiles/downloads/R2017b/deployment_files/R2017b/installers/maci64/MCR_R2017b_maci64_installer.dmg. This will install MATLAB Runtime at /Applications/MATLAB/MATLAB_Runtime. Note that the RoCA application will not work with any older or newer version of the MATLAB Runtime.

2. Download this "RocaNet" repository. A folder named "RocaNet-master" will be made on your computer.

3. Go to /RocaNet-master/macos/ directory and run the RoCA app by double clicking “RocaNet” in this folder. This will open the GUI of the RoCA software.


#### Method 2: Using the MATLAB Runtime installer

1.	Download the installer "RocaNet_mcr" from http://bit.ly/rocanet_v1_mac (size: ~1 GB) and install the application by following the guidelines in the setup window as follows:
      * Make sure to install RocaNet in any folder other than the “Applications” folder (e.g., you can create a new folder on your Desktop or in Documents folder). In this tutorial, we assume that you made a folder “RoCA_dir” in your “Documents folder”.
      * Do not change the default installation folder ("Applications") of MATLAB runtime libraries. 
      * This will install RoCA_gui as well as MATLAB runtime libraries (required to run the app). This procedure may take 2 – 3 minutes on a standard computer.

2.	Run the installed app by double clicking “RocaNet” located in your newly created folder (/Documents/RoCA_dir/application/). This will open the GUI of the RocaNet software.
</details>

<details>
  <summary>
    <b> Windows </b>
  </summary>  
&nbsp;

RocaNet application can be installed using one of the following methods on Microsoft Windows OS:

#### Method 1: Downloading MATLAB Runtime separately and running directly the RoCA app without any installation

1.	Download and install the Windows version of the MATLAB Runtime for R2018a from the following link on the MathWorks website http://ssd.mathworks.com/supportfiles/downloads/R2018a/deployment_files/R2018a/installers/win64/MCR_R2018a_win64_installer.exe. This will install MATLAB Runtime in the Program Files directory. Note that the RoCA application will not work with any older or newer version of the MATLAB Runtime.

2. Download this "RocaNet" repository. A folder named "RocaNet-master" will be made on your computer.

3. Go to \RocaNet-master\windows\ directory and run the RoCA app by double clicking “RocaNet.exe” in this folder. This will open the GUI of the RoCA software. 
    
    Note that antivirus programs, if installed, may block running the software. If this problem arises (noticed for example in the case of Avast and F-secure antivirus), add the program in trusted applications and then run it.

#### Method 2: Using the MATLAB Runtime installer

1.	Download the installer "RocaNet_mcr" from http://bit.ly/rocanet_v1_win (size: ~1 GB) and install the application by following the guidelines in the setup window as follows:
      * Make sure to install RocaNet in any folder other than the “Program Files” folder (e.g., you can create a new folder on your Desktop or in Documents folder). In this tutorial, we assume that you made a folder “RoCA_dir” in your “Documents folder”.
      * Do not change the default installation folder (“Program Files”) of MATLAB runtime libraries. 
      * This will install RocaNet as well as MATLAB runtime libraries (required to run the app). This procedure may take 2 – 3 minutes on a standard computer.

2.	Run the installed app by double clicking “RocaNet.exe” located in your newly created folder (e.g.,\Documents\RoCA_dir\application\). This will open the GUI of the RocaNet software. 
    
    Note that antivirus programs, if installed, may block running the software. If this problem arises (noticed for example in the case of Avast and F-secure antivirus), add the program in trusted applications and then run it.

</details>

<details>
  <summary>
    <b> Linux </b>
  </summary>  
&nbsp;

RocaNet application can be installed using one of the following methods on Linux OS (tests have been done on CentOS Linux 7, Ubuntu 16.04 LTS and 18.04 LTS):

#### Method 1: Downloading MATLAB Runtime separately and running directly the RoCA app without any installation

1.	Download the Linux version of the MATLAB Runtime for R2018a from the following link on the MathWorks website: http://ssd.mathworks.com/supportfiles/downloads/R2018a/deployment_files/R2018a/installers/glnxa64/MCR_R2018a_glnxa64_installer.zip. 

      Unzip the downloaded zip file in a folder (e.g., MCR_downloaded). Open terminal, go to the directory of the downloaded zip file and type the following commands (admin password on user's computer required): 
      ```
      sudo chmod +x install
      ./install
      ```
      This will open the MATLAB Runtime setup window. Follow the guidelines in the setup window and install MATLAB Runtime in the directory /Documents/MATLAB_Runtime. Note that the RoCA application will not work with any older or newer version of the MATLAB Runtime.

2. Download this "RocaNet" repository. A folder named "RocaNet-master" will be made on your computer.
3. Open terminal and go to /RocaNet-master/Linux/ directory and type the following command (admin password on user's computer required): 
      ```
      sudo ./run_RocaNet.sh /home/UserName/Documents/MATLAB_Runtime/v94/
      ```
      where “UserName” is the name of the directory in which the Documents folder is located. This will open the GUI of the RocaNet software.

#### Method 2: Using the MATLAB Runtime installer

1.	Install the RocaNet application as follows:
      * Download the installer "RocaNet_mcr.install" from http://bit.ly/rocanet_v1_linux (size: ~1 GB) to a directory on your computer. Here onwards, we assume that you download it in the "Documents" folder.
      * Open terminal and go to the "Documents" folder and type the following command (admin password on user's computer required): 
      ```
      sudo chmod +x RocaNet_mcr.install
      ```
      * Go to the "Documents" folder, double click on the installer file “RocaNet_mcr.install”, and follow the guidelines in the setup window.
      * Please make sure to install RocaNet in any folder other than the system folders (e.g., you can create a new folder on your Desktop or in Documents folder). In this tutorial, we assume that you made a folder “RoCA_dir” in your “Documents folder”.
      * Install MATLAB Runtime in the directory /Documents/MATLAB_Runtime/.
      * This will install RocaNet as well as MATLAB runtime libraries (required to run the app). This procedure may take 2 – 3 minutes on a standard computer.

2.	To run the application, open terminal and go to the directory /Documents/RoCA_dir/application/ and type the following command (admin password on user's computer required): 
      ```
      sudo ./run_RocaNet.sh /home/UserName/Documents/MATLAB_Runtime/v94/
      ```
      where “UserName” is the name of the directory in which the Documents folder is located. This will open the GUI of the RocaNet software.
</details>


&nbsp;
## Usage

1.	To infer sectors of co-evolving sites using RoCA, you need to simply provide 
      * Multiple sequence alignment (MSA) of the protein in fasta format [mandatory input]; 
      * A list of known protein biochemical domains in csv/xls format [optional]. If provided, the software computes and displays the association of inferred sectors with the specified biochemical domains. The numbering of the residues in each biochemical domain should match the numbering used in the MSA. For formatting this data properly, see the example files provided in the Data_RoCA folder in this repository.
      * The number of leading principal components (PCs) to use in the infer-ence of co-evolutionary networks [default: 2];


2.	For testing purposes, you can use the data provided in the Data_RoCA folder in this repository.

3.	RoCA saves the following output files in either csv or xls format (as specified by the user; [default: csv]):
      * Sample PCs used in the inference procedure (xyz_SamplePCs.format, where “xyz” is the name of the fasta file provided as an input and “format” is either csv or xls depending on the option selected in the GUI.)
      * All eigenvalues of the sample correlation matrix (xyz_Eigenvalues.format)
      * RoCA estimated PCs (xyz_RocaPCs.format)
      * RoCA sectors (xyz_RoCASecs.format)

    Note that the above-mentioned output files are saved by default in the same directory in which the input fasta file is located.
    
4. Vector graphics (eps format) of all results are also saved in the same directory for generating publication-quality figures.

&nbsp;
## Acknowledgement

<!-- I would like to thank Neelkanth Kundu, Laureano Moreno Pozas, Muhammad Saqib Sohail, Syed Muhammad Umer Abdullah, Syed Faraz Ahmed, and Syed Awais Wahab Shah for providing useful comments/feedback and assisting in testing of RocaNet. -->

&nbsp;
## Troubleshooting
For any questions or comments, please email at ahmedaq@gmail.com. 
