---
layout: post
title: "Introduction to C++ Programming Language"
author: Muhan Zhang
---

In this new week, we will be learning the brand-new section -- C++ programming language! As I learned C programming before in my undergraduate education, I know there exist many differences between C++ and Python, where C++ is more complicated with strict grammar on data type and accessing. Today I am going to talk about the group project where some discussions are heated around C++.

Basically, it uses a new integration method of Riemann sum. Different from Monte Carlo integration which focuses on random numbers and propability theory, Riemann sum method is more around the definition of integration:
$$ \int_a^b f(x) dx = \lim_{\lambda \to 0} \sum_{i=1}^n f(\xi_i) \Delta x_i $$
As is the origin of Riemann sum integration.

In our program, two functions are created apart from main function, calculate_y function to directly calculate y value according to the integrand and variable x, calculate_integral function as integration function using Riemann sum method with arguments a and b to limit the integral interval. In calculate_y function, double type is applied to both argument x and return value. We devised a scheme to fixate number of points of 1000, and the width of rectangle dx will be flexibly confirmed by calculating:
$$ dx = \frac{b - a}{n_{points}} $$
where dx, a and b are double data type, and n_points is assigned integer.

The value of height of rectangle (i.e. Y value) is key to success of integration. We use for loop with each step of X value increasing dx, while X value starts at a + dx/2. This can determine the midpoint of each rectangle.

Actually, the number of points in Riemann sum method just need to be at 50 or so, we use 1000 to make it more accurate, and the result is amazing! Different from Monte Carlo method, this method can be greatly accurate as the final estimation of $\pi$ equals to 3.1415926, which is nearly the same! However, Monte Carlo method still has its own advantages: regardless of whether the function is consecutive and differential, it can always calculate the area of integration. Just using random numbers and simple countings, Monte Carlo method can make integration much easier and less costly.