# ACM-Loss-function
This is my attempt to implement Active Contour Model as a Loss function

This code works with Baumgach repo:
https://github.com/baumgach/acdc_segmenter

This code is a modification from Chen repo:
https://github.com/xuuuuuuchen/Active-Contour-Loss

how to use this code:
1. This only tested in baumgach repo, so you should follow his instruction first about how to run his code
2. Copy this code to add another loss function in baumgach tfwrapper/losses.py
3. Add your loss function in model.py to be able to be selected
4. Dont forget to change your experiment setting to use this loss function



ps: Any Jupyter Notebook file in the 'visualization' folder is my attempt to analyze my model deeply
