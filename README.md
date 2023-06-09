# Optimization of Fire Stations Location 

## Introduction 
There are six cities (cities 1-6) in Kilroy County. The county must determine where to build fire stations. The county wants to build the minimum number of fire stations needed to ensure that at least one fire station is within 15 minutes (driving time) of each city. The times (in minutes) required to drive between the cities in Kilroy County are shown in Table 6 and Table 7. For each city, Kilroy must determine whether to build a fire station there

## Problem Formulation

For each city, Kilroy must determine whether to build a fire station there, We define the 0-1 variables X1, X2, X3, X4, X5 and X6 by :

**Xi = 1** --> If a fire station is built in city i
**Xi = 0** --> Otherwise

Then the total number of fire stations that are built is given by X1 + X2 + X3 + X4 + X5 + X6 and Kilroy's objective function is to minimize

**Z = X1 + X2 + X3 + X4 + X5 + X6**

must be ensure that there is a fire station within 15 minutes or less for each city, for that we add the constraints:

* X1 + X2      >= 1   (City 1 constraint)
* X1 + X2 + X6 >= 1   (City 2 constraint)
* X3 + X4      >= 1   (City 3 constraint)
* X3 + X4 + X5 >= 1   (City 4 constraint)
* X4 + X5 + X6 >=1    (City 5 constraint)
* X2 + X5 + X6 >=1    (City 6 constraint)

where **Xi = 0 or 1** ; (i=1,2,3, 4,5, 6)


## Technologies Used
* Pthon 
* Jupyter Notebook
* Cplex IBM

In this project, I utilized Python as my primary programming language to analyze and manipulate data. Also an CPLEX extension was used to solve the IP problem.

## Data Source

**Table 6: Time required to travel between cities in the county**
| FROM     | City 1   | City 2   | City 3   | City 4   | City 5   | City 6   |
|----------|----------|----------|----------|----------|----------|----------|
| City 1   | 0        | 10       |  20      |   30     | 30       | 20       |
| City 2   | 10       |  0       |  25      |   35     | 20       | 10       |
| City 3   | 20       | 25       |   0      |   15     | 30       | 20       |
| City 4   | 30       | 35       |  15      |    0     | 15       | 25       |
| City 5   | 30       | 20       |  30      |   15     |  0       | 14       |
| City 6   | 20       | 10       |  20      |   25     | 14       |  0       |

**Table 7 cities within 15 minutes of given city**
| City     | Within 15 minutes   | 
|----------|---------------------|
| City 1   | 1,2                 |
| City 2   | 1,2,6               |
| City 3   | 3,4                 |
| City 4   | 3,4,5               |
| City 5   | 4,5,6               |
| City 6   | 2,5,6               |

## Analysis and Results

* Resolution Kilroy Fire Stations
