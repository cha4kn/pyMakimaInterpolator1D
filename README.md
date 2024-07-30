# pyMakimaInterpolator1D

Python Modified Akima Interpolation Implementation in 1D

Overview
===================================================
This repo contains a Python implementation of the *Modified Akima Interpolation* method described here: https://blogs.mathworks.com/cleve/2019/04/29/makima-piecewise-cubic-interpolation/

To my knowledge this is the first Python implementation openly available (as of 2024).

Please see the LICENSE file before usage.

Performance
---------------------------------------------------
The code has been extensively evaluated against the native Matlab implementation for filling out missing values inside large amounts of data (~10 GB). 
Sadly, this version is slower than the Matlab version. This is mainly due to Matlab invoking C code while Python is inherently slow. I have tried to maximize the speed by invoking Numba just-in-time compilation.
The correctness of the interpolation is however 100% compared with Matlab.

How To Use
===================================================
The script requires Python modules 'numba' and 'numpy'.  
Run ". setup_venv.sh" to build and activate a virtual Python environment with these libraries available.

Example
---------------------------------------------------
1. Import the script by adding "import makimaInterpolator1D" to your own Python script.
2. Given an array x_vals of x-values and an array y_vals of corresponding y-values, the interpolated values at new points xq are given my the call "makimaInterpolator1D.makima(x_vals, y_vals, xq)".

All given input variables should preferably be numpy arrays.
