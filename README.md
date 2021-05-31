# VBA Challenge: Refactoring

## Overview of Project

The purpose of this analysis is to compare and contrast the original code of the macro created for analyzing the prices and volume of stocks in a given industry (green energy) with a refactored version which serves the same purpose. We want to determine if it is possible to refactor and optimize the code, and also how fast is the new code running in comparison.

## Results

We refactored the code mainly by creating arrays to hold the calculations of our data instead of using individual variables to hold each calculation. In this manner, our variables ```totalVolume```, ```startingPrice``` and ```endingPrice``` hold the single data for each ```ticker```. In contrast, the corresponding arrays ```tickerVolumes```, ```tickerStartingPrices``` and ```tickerEndingPrices``` hold all the data for every corresponding ticker and we traverse the data by using the variable ```tickerIndex```.

This simple change allowed us to avoid using a nested ```for``` loop, which was the main difference between the two codes. As the dataset becomes larger and larger, this allows us to reduce the time the program has to fetch and process data. We found that our *original* code ran in [**0.7969** seconds for the 2017 data](resources/VBA_Challenge_2017(Original).PNG) and in [**1.0156** seconds for the 2018 data](resources/VBA_Challenge_2018(Original).PNG) while the *refactored* code ran in [**0.1484** seconds for the 2017 data](resources/VBA_Challenge_2017.PNG) and in [**0.1796** seconds for the 2018 data](resources/VBA_Challenge_2018.PNG). Which is a reduction of around 80% of the time in comparison to the original code.

## Summary

Refactoring code has many advatages, the first and most important one is that it allows code to run more efficiently and faster; which becomes very relevant as the datasets that we end up working with are scaled up and more data is added. Another advantage is that it simplifies the process of debugging, as we have less clutter of code to begin with and it makes finding and fixing errors much easier. Finally, refactoring code allows us to detect and fix bad patterns and forms present in code for better readability.

However, there exists some diadvantages to refactoring code as well, the main one is that it's not really that intuitive and without a clear and set outline, it may also be time consuming and one may get lost in the code. This can create new bugs and errors to deal with, which itself may increase a project's schedule which might already be tight in the first place.

Our own code was subject to these diadvantages as it wasn't exacly second nature to figure out how to optimize the code in hand and many new bugs popped out developing the optimized code. However, code refactoring's advatages outweigh its cons, since we managed to cut the time required to run the code by more than 3/4 of its original runtime. Besides, our refactored code looks cleaner and uncluttered and can handle much larger datasets. If a company is interested in making their tools fast, accessible and long lasting, they must put their resources in refactoring and optimizing their code. 
