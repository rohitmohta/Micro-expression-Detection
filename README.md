# Micro-expression-Detection
This project aims to study and detect the possible micro-expressions shown by one person using the Mean Direction Maximal
Difference(MDMD) technique using machine learning with the help of the CASME-II and SMIC dataset.

The original MDMD (Main Directional Maximal Difference Analysis)  method proposed is slightly modified for MEGC 2020 as follows.

(1) For preprocess, face regions are cropped according to the landmarks detected by the "Dlib" toolkit. More details can be gotten by reading the codes in the file "preprocess.py" in the folder "MEdatabase_processed".  

(2) For parameter settings: for the CAS(ME)^2 dataset, the "k" is set to 12 for micro-expressions, and 39 for macro-expressions; for the SAMM Long Videos dataset, the "k" is set to 80 for micro-expressions, and 260 for macro-expressions; the number of blocks is set to 6 x 6, and the number of directions is set to 4, and the "p" is set to 0.01. 

(3) The original MDMD only predicts whether a frame belongs to facial movements. To output target intervals,  the adjacent frames consistently predicted to be macro- or micro-expressions form an interval, and the intervals that are too long or too short are removed. The number of micro-expression frames is limited between 7 and 16 for the CAS(ME)^2 dataset, and between 47 and 105 for the SAMM Long Videos dataset. The number of macro-expression frames is defined as larger than 16 for the CAS(ME)^2 dataset, and larger than 105 for the SAMM Long Videos dataset.

