# ACM-Loss-function
this is my attempt to implement Active Contour Model as a Loss function

this code works with Baumgach repo:
https://github.com/baumgach/acdc_segmenter

this code is a modification from Chen repo:
https://github.com/xuuuuuuchen/Active-Contour-Loss

how to use this code:
1. this only tested in baumgach repo, so you should follow his instruction first about how to run his code
2. copy this code to add another loss function in baumgach tfwrapper/losses.py
3. add your loss function in model.py to be able to be selected
4. dont forget to change your experiment setting to use this loss function
