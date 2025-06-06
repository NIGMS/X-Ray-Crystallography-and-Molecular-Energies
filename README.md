<p align="center">
<img src="images/MS-course-card.png" width="400" />
</p>
     
# <center> **X-Ray Crystallography & Molecular Energies** </center>
### <center> **Authors: Dr. Christopher Jurgenson and Dr. Joseph Bentley** </center>

---

## Contents

+ [Overview](#Overview)
+ [Background](#Background)
+ [Before Starting](#Before-Starting)
+ [Getting Started](#Getting-Started)
+ [Software Requirements](#Software-Requirements)
+ [Architecture Design](#Architecture-design)
+ [Data](#Data)
+ [Funding](#Funding)
+ [License for Data](#License-for-Data)


## Overview

This cloud-based learning module teaches x-ray crystallography and molecular energy basics. The x-ray crystallography tutorial will be carried out threw the Phenix software. After going through this the user should be comfortable with the process of determining the protein structure. Additionally, the user should be comfortable with basic quantum chemistry concepts used to perform biochemistry modeling.


<p align="center">
        <a href="https://www.youtube.com/watch?v=FapVSYz_cms&list=PLXaEJPtnQ4w7Vu7vqWbttBjUGrPp4Qa7b&index=25">
            <img src="images/overview_video.png" alt="Overview", width="550"/>
        </a>
    <br>
    <span> Click above image to watch overview video </span>
</p>

The course is structured in four submodules, allowing us to:
1. Gain a basic understanding of proteins and x-ray diffraction/crystallography
2. Solve protein structure using SAD/MAD phasing in Phenix
3. Solve protein structure using molecular replacement in Phenix
4. Carry out protein modeling using COOT


The course content is organized in Jupyter Notebooks. The first three notebooks cover x-ray crystallography while the fourth discusses the quantum nature of molecular interactions.

The overall structure of the modules is explained below:

+ [**Submodule 0**](submodule_0_Phenix.ipynb): Used to launch the Phenix GUI
+ [**Submodule 1**](submodule_1_protein_crystallography_background.ipynb): Provides fundamentals of protein structure and x-ray crystallography. 
+ [**Submodule 2**](submodule_2_solving_protein_structure.ipynb):  Solving protein structure using SAD/MAD phasing and Molecular replacement methods.
+ [**Submodule 3**](submodule_3_protein_modeling_COOT.ipynb): Perform protein modeling using coot. 
+ [**Submodule 4**](submodule_4_molecular_interactions.ipynb): Aims to introduce basics of molecular energies providing basics of schrodingers equation and quantum chemistry.

## Background

X-ray crystallography and molecular dynamics are two essential tools in the field of structural biology that provide valuable insights into the three-dimensional structure and dynamic behavior of proteins. X-ray crystallography is an experimental technique that involves growing protein crystals, exposing them to X-ray beams, and analyzing the resulting diffraction patterns to determine the precise atomic positions within the protein. This technique has been instrumental in elucidating the structures of countless proteins, including enzymes, receptors, and other drug targets. On the other hand, molecular dynamics is a computational method that simulates the motion and interactions of atoms within a protein over time, based on the principles of classical mechanics and empirical force fields. By capturing the dynamic nature of proteins, molecular dynamics simulations can reveal important information about protein flexibility, conformational changes, and ligand binding, which are crucial for understanding protein function and designing effective drugs.

## Before Starting 
These tutorials are designed to run on AWS with the notebooks running within SageMaker AI notebooks. Before starting please gain access to an AWS account which you will be able to run SageMaker. 

## Getting Started 

<details>
    <summary> Setting Up AWS Sagemaker AI </summary>
    
**1. Setting Up an AWS SageMaker Notebook Instance**

You can also reference [this guide](https://github.com/NIGMS/NIGMS-Sandbox/blob/main/docs/SageMakerNotebook%26StudioSetup.md).

- Log in to AWS Management Console:
    - Navigate to the AWS SageMaker Console (Find **Amazon SageMaker AI** in the Services, or search it in the search bar)
- Create a SageMaker Notebook Instance:
    - Click **Notebooks**" in the left navigation pane (under Applications and IDEs, in Amazon SageMaker AI).
    - Click "**Create notebook instance**" at the top of the Notebook instances.
    - Fill out the following details:
        - Notebook instance name: Provide a unique name (e.g., notebook-yourname-date).
        - Instance type: Choose **ml.t3.medium** (or a larger instance type if your dataset is large, [more examples](https://docs.aws.amazon.com/sagemaker/latest/dg/notebooks-available-instance-types.html).
        - Click "**Addtional configurations**"
            - Lifecycle Configuration (Optional): Add a script to install any additional dependencies automatically.
            - **Volumne size in GB**: change it to **25**
        - IAM Role: If you don’t have an existing role, create a new one with S3 full access and AmazonSageMakerFullAccess permissions.
- Start the Notebook Instance:
    - Click "**Create notebook instance**" and wait for the status to change to "InService".

**2. Cloning the Tutorials Repository**
- Open the Notebook Instance:
    - Once the instance is active, click "Open JupyterLab" to access the notebook.
- Clone the Repository:
    - Open a terminal from the Jupyter interface.
    - Run the following command:
        - <code>**cd SageMaker**</code>
        - <code>**git clone https://github.com/NIGMS/X-Ray-Crystallography-and-Molecular-Energies.git**</code>
    - This will create a folder containing all tutorial files.

</details> <br>

You can also watch the AWS notebook setup video below for step-by-step instructions:
<p align="center">
        <a href="https://www.youtube.com/watch?v=djLo0L3147s&list=PLXaEJPtnQ4w7Vu7vqWbttBjUGrPp4Qa7b">
            <img src="images/aws_notebook_setup_thumbnail.jpeg" alt="Creating an AWS SageMaker Notebook Instance", width="550"/>
        </a>
    <br>
    <span> Click above image to watch notebook setup video </span>
</p><br>



<details>
<summary> Registering For Phenix Account</summary>
    Submodule 2/3 uses Phenix and in order to access Phenix you must register for an account.<br>
    <li>
    Submit 
    <a href="https://docs.aws.amazon.com/sagemaker/latest/dg/notebooks-available-instance-types.html">Phenix Registration</a> form. 
    </li>
    <li>Once you have submitted the download request form wait for an email response notifying you that you can download Phenix.  </li>

</details>
  
## Software Requirements

For submodule 1, you can install all necessary requirements using the instructions in submodule 4, and the detailed software versions used in this tutorial are listed here:
 - `python 3.10.16`
 - `pandas 1.5.3`
 - `IPython 8.34.0`
 - `ipywidgets 8.1.5`

For submodule 2/3 Phenix is used 

 - `Phenix version 1.1.4`
 - `COOT 1.1.14`


For submodule 4, you can install all necessary requirements using the instructions in submodule 4, and the detailed software versions used in this tutorial are listed here:
 - `python 3.10.16`
 - `pandas 1.5.3`
 - `numpy 1.26.4`
 - `matplotlib 3.10.1`
 - `scipy 1.15.2`
 - `IPython 8.34.0`
 - `ipywidgets 8.1.5`
 - `ase 3.24.0`

## Architecture Design
<center><img src='images/architecture_diagram.png', width='800'/></center>

## Data
Data for the crystallography exercises are from the following PDBIDs and their assocaited publications:
* 2A3N: Crystal structure of Putative glucosamine-fructose-6-phosphate aminotransferase (16423107) from SALMONELLA TYPHIMURIUM LT2 at 1.35 A resolution (To be published)
* 5TSO: Novel Enhancer Binding Site Found In Bacteria And Eukaryota But Not In Archea (To be published)
* 7DER: Acta Crystallogr D Struct Biol. 2021 Mar 1;77(Pt 3):288-292. Recent structural insights into the mechanism of lysozyme hydrolysis
* 8AB3: Mol Biol Evol 2023 40. Deciphering Evolutionary Trajectories of Lactate Dehydrogenases Provides New Insights into Allostery
* 3MJU: Crystal structure determination of pigeon (columba livia) haemoglobin at 3.5 angstrom resolution (To be published)
* 7EBC: J Struct Biol 213 2021: 107748-107748. Structural insights into the targeting specificity of ubiquitin ligase for S. cerevisiae isocitrate lyase but not C. albicans isocitrate lyase
* 7Q36: Commun Biol 5: 360-360 2022. High-pressure crystallography shows noble gas intervention into protein-lipid interaction and suggests a model for anaesthetic action.
* 7O83: J Med Chem 65: 6940-6952 2022. Discovery of AZD4625, a Covalent Allosteric Inhibitor of the Mutant GTPase KRAS G12C


## Funding

We would like to acknowledge the sources of funding:<br>
This work was supported by the Mississippi INBRE, funded by an Institutional Development Award (IDeA) from the National Institute of General Medical Sciences of the National Institutes of Health under grant number P20GM103476. Any opinions, findings, conclusions, or recommendations expressed in this material are those of the authors and do not necessarily reflect the views of the funding agencies.


## **License for Data**
Text and materials are licensed under a Creative Commons CC-BY-NC-SA license. The license allows you to copy, remix, and redistribute any of our publicly available materials, under the condition that you attribute the work (details in the license) and do not make profits from it.

This work is licensed under a [Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License](https://creativecommons.org/licenses/by-nc-sa/4.0/)

