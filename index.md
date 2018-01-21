
```Automatic Generation of OCL Constraints from Use Case Specifications in Natural Language```

## Overview of the approach

System testing plays a crucial role in safety-critical domains, e.g., automotive, where system test cases are used to demonstrate the compliance of software with its functional and safety requirements. Unfortunately, since requirements are typically written in natural language, significant engineering effort is required to derive test cases from requirements.

In such a context, automated support for generating system test cases from requirements specifications written in natural language would be highly beneficial. Unfortunately, existing approaches have limited applicability. For example, some of them require that software engineers provide formal specifications that capture some of the software behavior described using natural language. The effort needed to define such specifications is usually a significant deterrent for software developers.

OCLgen is an approach which largely automates the generation of the additional formal specifications required by an existing test generation approach named UMTG. More specifically, OCLgen relies on semantic analysis techniques to automatically derive the pre- and post-conditions of the activi- ties described in use case specifications. The generated conditions are used by UMTG to identify the test inputs that cover all the use case scenarios described in use case specifications. In practice, the proposed approach enables the automated generation of test cases from use case specifications while avoiding most of the additional modeling effort required by UMTG.

Results from an industrial case study show that the approach can automatically and correctly generate more than 75% of the pre- and post-conditions characterizing the activities described in use case specifications.


## Data

The list of VerbNet classes that are likely/unlikely to appear in use case specifications and the list of VerbNet classes whose members can be processed by means of the meta-verb-transformation rule described in the paper are enclosed in a Excel document that can be downloaded from the following URL https://github.com/OCLGen/OCLGen.github.io/blob/master/data/OCLGen_AnalysisOfVerbClasses.xlsx.

## Software

You can download the tool from the following URL https://drive.google.com/open?id=13cw3EBIzOjNpRqciQihxEHq2NMHPVNhA

The tool can be run from OsX/Linux. To use the tool simply uncompress the tar.gz archive and cd in the folder OCLGenDistVx.

OCLGen receives as input a class diagram saved in UML format and a sentence to translate to an OCL constraint. Alternatively, you can provide a file with a list of sentences (one per new line) and a directory where to save the generated OCLs; in this case the tool will save the generated OCLs one per file in the indicated folder (files are named with a number, corresponding with the line of the provided sentence). 

Currently we support UML files generated with Rational Rhapsody, we will extend the format supported soon.

To see the brief usage instructions simply type 'bash runOCLGen.sh'.

We provide two usage examples in the following lines:
bash runOCLGen.sh OCLGen/files/IEE/UMTG-DEMO/DomainModel.uml "The system sets TemperatureError to detected"
(the OCL will be printed on screen)

bash runOCLGen.sh OCLGen/files/IEE/UMTG-DEMO/DomainModel.uml OCLGen/files/DEMO/text.txt dirWithGeneratedOCLs/
(the generated OCLs will be saved in the folder dirWithGeneratedOCLs)

We will provide the list of OCLs used to evaluate the tool in the ICST'18 paper soon, after properly renaming concepts and verbs to avoid breaking NDA.

