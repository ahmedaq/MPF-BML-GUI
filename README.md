# MPF-BML: A standalone GUI-based cross-platform package for maximum entropy model inference

## Table of Contents
*  [Overview](#overview)
*  [Details](#details)
*  [Requirements](#requirements)
*  [Installation](#installation)
*  [Running the application](#running-the-application)
   - [Input data](#input-data)
   - [Setting the parameters](#setting-the-parameters)
   - [Running the MPF-BML method](#running-the-mpf-bml-method)
   - [Model verification](#model-verification)
   - [Saved output data](#saved-output-data)
*  [Troubleshooting](#troubleshooting)
*  [References](#references) 
<!-- *  [Acknowledgement](#acknowledgement) -->

## Overview
MPF-BML-GUI is a standalone cross-platform package which features an easy-to-use GUI. The package only requires the input data (protein sequence data or data of multiple configura-tions of a complex system with large number of variables) and returns the maximum entropy model parameters inferred using the MPF-BML method. 

![alt text][MPFBMLGUI]

[MPFBMLGUI]: https://github.com/ahmedaq/MPF-BML-GUI/blob/master/E2_fig_4.png "MPF_BML_GUI"

## Details
#### Title of paper
MPF-BML: A standalone GUI-based package for maximum entropy model inference
#### Authors
Ahmed A. Quadeer, Matthew R. McKay, John P. Barton, and Raymond H. Y. Louie.

## Requirements
A PC with either macOS, Microsoft Windows, or Linux.

## Installation
<details>
  <summary>
    <b> macOS </b>
  </summary> 
  
1.	Download the installer from the "macOS" directory in this repository, unzip the files, and install the application by following the guidelines in the setup window.

2. This will install MPF-BML-GUI as well as MATLAB runtime libraries (required to run the app). This procedure may take 10 – 15 minutes on a standard computer.

3.	Open /Applications/MPF-BML-GUI/application/ directory and double click the installed application "MPF_BML". This will open the GUI of the MPF-BML-GUI software.

</details>

<details>
  <summary>
    <b> Windows </b>
  </summary>
  
1.	Download the installer from the "Windows" directory in this repository, unzip the files, and install the application by following the guidelines in the setup window.

2. This will install MPF-BML-GUI as well as MATLAB runtime libraries (required to run the app). This procedure may take 10 – 15 minutes on a standard computer.

3.	Open \Program Files\MPF-BML-GUI\application\ directory and double click the installed application "MPF_BML". Or the the can double click the shortcut to the application, in case the user opted for it during the installation. This will open the GUI of the MPF-BML-GUI software.
    
    Note that antivirus programs, if installed, may block running the software. If this problem arises (noticed for example in the case of Avast and F-secure antivirus), add the program in trusted applications and then run it.
</details>

<details>
  <summary>
    <b> Linux </b>
  </summary>  

1.	Install the MPF-BML-GUI application as follows:
      * Download the installer from the "Linux OS" directory in this repository, unzip the files, and install the application by following the guidelines in the setup window. 
      
      Note: In case the installer doesn't start, open terminal and go to the "Documents" folder and type the following command: 
      ```
      chmod +x MPF_BML.install
      ```
      * The installer will try to install the software in the /usr/ directory. If this directory in inaccessible, the user can choose any other directory to install the software. In this tutorial, we assume that you made a folder “MPF-BML-GUI” in your “Documents" folder. Install MATLAB Runtime in the same parent directory.
      * This will install MPF-BML-GUI as well as MATLAB runtime libraries (required to run the app). This procedure may take 10 – 15 minutes on a standard computer.

2.	To run the application, open terminal and go to the directory /Documents/MPF-BML-GUI/application/ and type the following command: 
      ```
      ./run_MPF_BML.sh /home/UserName/Documents/MPF-BML-GUI/v96/
      ```
      where “UserName” is the name of the directory in which the Documents folder is located. This will open the GUI of the MPF-BML-GUI software.
  
</details>

## Running the application

### Input data
To infer maximum entropy model parameters using MPF-BML, you need to simply provide 
* Input data in FASTA/Excel format comprising either multiple sequence alignment of the protein or a categorical data (with rows and columns representing samples and variables, respectively) [mandatory input]; 
* Input file in Excel format for providing different weights to samples in order to reduce any sampling bias (each sample is given the same weight if no data is provided) [optional input];
* Input file comprising maximum entropy model parameters for initializing the method (see Supplementary Text S1) [optional input].

Different datasets are provided in the "Datasets" folder in this repository for testing the MPF-BML GUI framework. For demonstration purposes, we will focus here on the data of HIV p7 nucleocapsid protein "p7-alignment.fasta" present in this folder. Click the "Load data" button and select this dataset and leave the remaining optional inputs blank as shown below.

**IMPORTANT**: The data to be analyzed (e.g. the file "p7-alignment.fasta" in this example) must be in the same directory where application is installed, e.g., /Documents/MPF-BML-GUI/application/. 

<img src="https://github.com/ahmedaq/MPF-BML-GUI/blob/master/Input_panel_2.png" width="300">

### Setting the parameters
In the "Parameters" panel of MPF-BML GUI, the user can set values of the different parameters involved in the three steps of the MPF-BML method (see (Louie et al., 2018) and Supplementary Text S2 for details of these parameters). A brief description of all parameters is also provided as tooltip to assist the user. The default values of these parameters, which were found to return a reasonable model for the majority of the test data, are already set. 

For the example dataset of HIV p7, we will only change the value of the BML parameter "Max eps" from 1.0 (default) to 1.5. This change enables the user to obtain a reasonable maximum entropy model in 10-20 minutes (on a standard computer with 1 processing core).

<img src="https://github.com/ahmedaq/MPF-BML-GUI/blob/master/Parameters_panel_2.png" width="300">

### Running the MPF-BML method
After providing input data and setting the parameters, the user can run the method by clicking on the “Run MPF-BML” button in the MPF-BML GUI as shown below. A “Stop” button is also provided to the user to stop execution in case the algorithm is not converging.

<img src="https://github.com/ahmedaq/MPF-BML-GUI/blob/master/Run_panel.png" width="300">

Progress of the execution process is displayed in the “Processing information” panel of MPF-BML GUI as shown below. 

<img src="https://github.com/ahmedaq/MPF-BML-GUI/blob/master/Processing_panel_2.png" width="400">

For the example dataset of HIV p7, the MPF-BML model would take around 10-20 minutes (on a standard computer with 1 processing core).

### Model verification
In the "Model verification" panel of MPF-BML GUI, the inferred models (MPF-only and MPF-BML) are validated by comparing the following statistical quantities of configurations in the data with those obtained from the inferred model:
* the individual frequencies (*p*<sub>i</sub>), 
* the pair-wise frequencies (*p*<sub>ij</sub>), 
* the connected correlations (*p*<sub>ij</sub> - *p*<sub>i</sub>*p*<sub>j</sub>), and
* the probability *P*(k) of observing a configuration with k differences with the consensus configuration.

<img src="https://github.com/ahmedaq/MPF-BML-GUI/blob/master/Model_ver_panel_2.png" width="600">

### Saved output data

* The inferred maximum entropy parameters using MPF and  MPF-BML are saved in a matrix form in tab-delimited text format (shown below). The first row and column show the change of configuration at a position with A/1/B denoting a change from configuration A to configuration B at position 1. The diagonal entries of the matrix represent the inferred fields while the non-diagonal entries represent the inferred couplings. 

<img src="https://github.com/ahmedaq/MPF-BML-GUI/blob/master/Output_parameters.png">

* A tab-delimited text file is also provided as an output with pairs of positions arranged in descending order according to their computed Frobenius norm, a metric representative of the pairs in contact. This metric is calculated using the inferred couplings (Cocco et al., 2018) and the higher the value of this metric, the higher is the chance of this pair to be in contact, and vice versa.

* Vector graphics (eps format) of all model-verification results are also saved in the same directory for generating publication-quality figures.

<!-- 
## Acknowledgement

I would like to thank Neelkanth Kundu, Laureano Moreno Pozas, Muhammad Saqib Sohail, Syed Muhammad Umer Abdullah, Syed Faraz Ahmed, and Syed Awais Wahab Shah for providing useful comments/feedback and assisting in testing of RocaNet.
-->

## Troubleshooting

1. Due to the known issue in writing xls/xlsx files in macOS and Linux versions of MATLAB, "xlwrite" function (https://www.mathworks.com/matlabcentral/fileexchange/38591-xlwrite-generate-xls-x-files-without-excel-on-mac-linux-win) was used to write the output files. The function "xlwrite" works for data with small dimensions; however, for large-dimensional datasets, the inferred maximum entropy model parameters are saved in a numeric csv file while the (row/column) labels of the matrix are saved separately in a xls file named "matrixlabels".

2. In macOS version only, the MCMC samples generated based on the inferred MPF-BML model (used in model verification) are not currently being saved. We are in the process of debugging this issue.


For any further questions or comments, please email at ahmedaq@gmail.com. 

## References

1. [Louie, R. H. Y. et al. (2018) Fitness landscape of the human immunodeficiency virus envelope protein that is targeted by antibodies. <i>Proceedings of the National Academy of Sciences</i>, <b>115</b>(4): E564–E573. doi: 10.1073/pnas.1717765115](https://dx.doi.org/10.1073/pnas.1717765115).

2. [Cocco,S. et al. (2018) Inverse statistical physics of protein sequences: a key issues review. <i>Reports Prog. Phys.<\i>, <b>81<\b>, 032601. doi: 10.1088/1361-6633/aa9965] (http://dx.doi.org/10.1088/1361-6633/aa9965).
<!-- 2. [Barton, J. P., De Leonardis, E., Coucke, A. and Cocco, S. (2016). ACE: adaptive cluster expansion for maximum entropy graphical model inference. <i>Bioinformatics</i>, <b>32</b>(20): 3089-3097. DOI: 10.1093/bioinformatics/btw328](https://dx.doi.org/10.1093/bioinformatics/btw328). -->
