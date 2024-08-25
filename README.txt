GENERAL INFORMATION
This README.txt file was updated on 25 August 2024

A. Paper associated with this archive
Citation:
This repository contains the matlab code and reused data for the following publication: Croll J. C. and Caswell H. (2024), Family matters: Linking population growth, kin interactions, and African elephant social groups. The American Naturalist

B. Originators
Jasper C. Croll, University of Amsterdam,
Hal Caswell, University of Amsterdam.

C. Contact information
Name: Jasper Croll
email: J.c.croll@uva.nl

F. Funding Sources
This research was supported by the European Research Council under the European Union's Horizon 2020 research and innovation program, ERC Advanced Grant 788195 (FORMKIN), to HC.

ACCESS INFORMATION
1. Licenses/restrictions placed on the data or code
CC BY (Attribution)

3. Recommended citation for this data/code archive
Cite with article citation:
Croll and Caswell (2024) Family matters: Linking population growth, kin interactions, and African elephant social groups. American Naturalist.

DATA & CODE FILE OVERVIEW
This data repository consist of 9 code scripts, 2 csv-files with reused data, and this README document, with the following data and code filenames:

Code scripts and workflow
[file names and brief descriptions. Also describe the workflow if there are several scripts that need to be run in order]
    	1. Main_elephant_kin_interactions.m; This is the main script that is used for analysis of computations and graphs. All other files contain MATLAB functions called from this file.
	2. kinship_function.m; This file contains the kinship_function(Umat, Fmat) function, which takes the survival matrix (Umat) and fecundity matrix (Fmat) and returns a array with the kinship structure calculated according to the equations in the main text of the paper.
	3. relatedness_high_function.m; This file contains the relatedness_high_function(kinstruc) function, which takes a kinship structure as produced by kinship_function.m and returns the higher estimate of the relatedness of Focal to the kin network calculated according to the equations in the main text of the paper.
	4. relatedness_low_function.m; This file contains the relatedness_low_function(kinstruc) function, which takes a kinship structure as produced by kinship_function.m and returns the lower estimate of the relatedness of Focal to the kin network calculated according to the equations in the main text of the paper.
	5. c1_calcX.m; This file contains the c1_calcX(kinstruc) function, which takes a kinship structure as produced by kinship_function.m and returns a vector with the age specific probability an individual has a living mother, to implement the feedback between mother presence and juvenile survival as discussed in the main text of the paper. 
	6. c2_calcX.m; This file contains the c2_calcX(kinstruc) function, which takes a kinship structure as produced by kinship_function.m and returns a vector with the age specific probability of having at least one sister, to implement the feedback between the presence of a sister and fecundity as discussed in the main text of the paper. 
	7. c3_calcX.m; This file contains the c3_calcX(kinstruc) function, which takes a kinship structure as produced by kinship_function.m and returns a vector with the expected oldest age in the kinship network, to implement the feedback between matriarch age and juvenile survival as discussed in the main text of the paper. 
	8. c4_calcX.m; This file contains the c4_calcX(kinstruc) function, is a wrapper combining the c1_calcX.m, c2_calcX.m and c3_calcX.m to implement the feedback effects from these functions simultaneously.
	9. solveXkin.m; This file contains the solveXkin(X,Fmat,Umat,@calcX), which is a wrapper of the c1_calcX.m, c2_calcX.m, c3_calcX.m and c4_calcX.m functions to feed these functions in the solve function and in this way solve the kinship network assuming these interactions. The function takes a guess of the values produced by the c1_calcX.m, c2_calcX.m, c3_calcX.m and c4_calcX.m functions (X), the fecundity matrix (Fmat), the survival matrix (Umat) and a handle of the c1_calcX.m, c2_calcX.m, c3_calcX.m and c4_calcX.m functions. The function returns the difference between the provided guess values (X) and the values calculated based on the provided matrices and function handle.
	10. wittemyer21.csv; data from Wittemyer, G., D. Daballen, and I. Douglas-Hamilton. 2021. Differential influence of human impacts on age-specific demography underpins trends in an african elephant population. Ecosphere 12:e03720. The first column contains age, the second column is the survival probability and the third column contains fertility of African elephants.
	11. wittemyer13.csv; data from Wittemyer, G., D. Daballen, and I. Douglas-Hamilton. 2013. Comparative demography of an at-risk african elephant population. PloS one 8:e53726. The first column contains age, the second column is the survivorship of African elephants.

SOFTWARE VERSIONS
MATLAB version 9.14.0.2254940 (R2023a) Update 2
Matworks Optimisation Toolbox version 9.5
