---
layout: post
title: "Introduction of NumPy"
author: Xudong Zhuang
---

# Introduction of NumPy

Today, we learned something about NumPy.

NumPy is a frequently used module for scientific computing. It can be used to store and manipulate large-scale matrix and shows higher efficiency compared to the nested list structure of the Python Standard Library. To import numpy: 

        import numpy as np

After talking about how to import this useful module, a frequently-used data structure--numpy array was introduced. If one import the numpy module by the aforementioned method, this data structure can be called in this way:

        a1 = np.array([[1, 2, 3], 
                       [2, 3, 4]])

One of the properties of numpy array is that it allows us to do pair-wise calculation without writing a for loop or nested for loop, which can greatly simplify the code. That is to say, if one write the following code:

        print(a1 * a1)

The result will be:

        np.array([[1, 4, 9],
                  [4, 9, 16]])

The feature of broadcasting was also introduced. Here, broadcasting means that numpy will automatically enlarge the smaller numpy array to fit the larger one when two numpy arrays are manipulated.

Additionally, array axis is something important to be noted. For example, when considering the following numpy array:

        c1 = np.array([[1, 4, 9],
                       [4, 9, 16]])

To calculate the mean or sum of each column:

        c1_m_col = c1.mean(axis = 0) / c1_m_row = c1.sum(axis = 0)

To calculate the mean or sum of each row:

        c1_m_col = c1.mean(axis = 1) / c1_m_row = c1.sum(axis = 1)

NumPy is a module that has a lot of similar function as the module of math. Some additional codes are also important to be noted:

1. To investigate the shape of a numpy array:

        c1.shape()

2. To calculate the mean value of all the values in a numpy array:

        c1.mean()

3. To calculate the mean value of all the values in a numpy array:

        c1.sum()

Hint: c1 is assumed to be a numpy array.


<center>

<img src = 'https://raw.githubusercontent.com/msse-2020-bootcamp/template-blog/master/images/msse-logo-bg.svg'>  

</center>