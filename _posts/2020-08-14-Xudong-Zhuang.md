---
layout: post
title: "code clean and test"
author: Xudong Zhuang
---

Today, we learn about:
1. how to clean the developed Monte Carlo code 
2. how to test the code.

## Clean the code

The first part is about how to make the code in a more canonical way.

The first step of this part is to rearrange the .ipynb file in a more canonical way. To do this, one should put all the imports at the beginning of the .ipynb file and all the functions closely attached to the imports.

After that, one should paste all the imports and functions to a new .py file follow the sequence of the rearranged .ipynb file. In the class, we accomplished this by the Visual Studio code and then save the .py file. 

Finally, we changed our Monte Carlo simulation loop into a function and named it as run_simulation so that it can be called conveniently. It is worth to note that in the run_simulation function, parameters initialization should be set as the input parameters and the origin initialization should be deleted.



## Test the code

The second part is about testing the code.

Two methods are presented in the lecture. 

The first method is done in a jupyter notebook. The first step is to import the ,py file and the second step is to set the initial parameters. Then we can run the function in the .py and see if it works.

The second method is pytest, which is frequently used for python code testing. The pytest will read the file named as test_xxx.py. One can test all the .py files start with 'test_' or assign one specific file to be tested. One can also assign some specific functions to be tested in a specific .py file. Several command lines are important to be noticed:
1. To install pytest:  pip install -U pytest-cov / pip install -U pytest
2. To run the pytest:  pytest
3. To run the pytest and print detailed information: pytest -v
4. To test a specific funtion in a specific .py file:  pytest test_xxx.py::test_function
5. To test a specific .py file:  pytest --cov=xxx.py 

Some special techniques like decoration are also covered in the lecture. 

<center>

<img src = 'https://raw.githubusercontent.com/msse-2020-bootcamp/template-blog/master/images/msse-logo-bg.svg'>  

</center>

   






