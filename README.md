## Welcome to Hyunjoon kim's homepage

### Benchmark Problems for H. Kim, B.-I. Kim, and D. Thiel “Optimal Incremental Deployment Method of Hydrogen Refueling Stations,” working paper, 2020

Benchmark Problems for H. Kim, B.-I. Kim, and D. Thiel “Optimal Incremental Deployment Method of Hydrogen Refueling Stations,” working paper, 2020
The 5 benchmark data sets can be downloaded by click [here]([Benchmark data.zip](https://github.com/Hyunjoonkim/Hyunjoonkim.github.io/files/5733593/Benchmark.data.zip).

#1.	Introduction

  In many countries, a lack of hydrogen refueling station (HRS) infrastructure is a major barrier for Fuel Cell Electric Vehicles (FCEV) to become more popular. The high-priced installation cost of HRS make the governments afford to place a limited number of HRSs in a short period time. This paper attempts to find optimal locations of one or two HRSs for the cases in which HRSs are deployed incrementally based on FCEV market development that is currently difficult to foresee. 

  In this paper, we propose a location optimization model applied to the context of a large city like Paris where fuel prices in general are higher than in the outskirts and where refueling stations attract car owners or taxi drivers who are looking for a HRS close to their parking lot. The incremental deployment of an HRS network that we propose must be able to attract at least a minimum number of customers corresponding to an initial investment payback period of 5 years maximum.
  
  Our assumptions are as follows. The HRS deploying policy in a large metropolis aims to develop an extensive HRS network. The attractiveness of the new HRSs will therefore be essentially due to the proximity of the customers it wishes to attract. Choosing initially to maximize the number of customers will only bring a new HRS closer to the old ones, which we want to avoid. A minimum number of customers will be enough to start with a sufficient load factor. The two objectives of our model are:
  
- To ensure that the HRSs are as far as possible from each other
- To get as close as possible to a limited number of customers but sufficient to ensure a HRS investment payback period of 5 years maximum and also to capture these customers thanks to a minimal distance from their parking place.

#2.	Benchmark Problems

  Given that a set of HRSs are already located, we propose to locate incrementally one or two new HRSs at the saturation point when all HRSs have nmax of customers.
  We represent the city of Paris (11 km x 9 km) by a rectangular grid defined from (0,0) to (110,90) with 10,101 possible locations in which new HRSs can be located. The first existing HRS is installed close to Pont de l’Alma (see Figure 1). Considering that taxis are moving everywhere within the city, we assume that demand points are uniformly distributed in the city. Each HRS can supply a maximum of 200 kg/day which corresponds to a maximal number of customers per day nmax = 125. In appendix 1, we calculate the minimum number of customers to attract to reach the payback period in 5 years, nmin = 36.
  
  We choose 5 cases of incremental HRS launching as follows:
- Case 1: Extend one existing HRS to two HRSs (one additional HRS)
- Case 2: Extend two existing HRSs to three HRSs (one additional HRS)
- Case 3: Extend one existing HRS to three HRSs (two additional HRSs)
- Case 4: Extend seven existing HRSs to eight HRSs (one additional HRS)
- Case 5: Extend seven existing HRSs to nine HRSs (two additional HRSs)


![Figure 1  Rectangle of 11 km  9 km surrounding the city of Paris (Google Map)](https://user-images.githubusercontent.com/29350999/102963167-cbcc3480-452b-11eb-8b16-491b7dd11c40.jpg)
<center> Figure 1. Rectangle of 11 km x 9 km surrounding the city of Paris (Google Map) </center>
#

Table 1 shows the data used in the 5 cases. In our mathematical models and proposed algorithm, the Minkowski distance, c<sub>ij</sub>=(<abs>{dx}</abs>\<sup>p</sup> +{<abs>{dy}</abs><sup>p</sup>)<sup>(1/p)</sup> with p=1.31, where dx represents the distance between two points (locations i and j) along the first axis, and dy along the second axis.

||**Case 1**|**Case 2**|**Case 3**|**Case 4**|**Case 5**|
|:---|:---:|:---:|:---:|:---:|:---:|
|_n(D): number of customers_|125|250|125|875|875|
|_K<sub>0</sub>: number of existing HRSs_|1|2|1|7|7|
|_number of new HRSs_|1|1|2|1|2|
|_K: total number of HRSs_|2|3|3|8|9|

The parameters used in the algorithm are as follows.
- We choose to represent the city by the grid of 111 x 91 cells, considering the geography of Paris (Figure 1) with 1 cell ≈ 100 meters.
- The minimum and the maximum number of customers related to HRS capacity, denoted by n<sub>min</sub> and n<sub>max</sub>, are set to 36 and 125, respectively. The d<sub>min</sub>, used to make the eligible potential points set _I<sub>e</sub>_, is set to 35.5, which is the quarter of the city area’s diagonal length.

The 5 benchmark data sets can be downloaded by click [here]([Benchmark data.zip](https://github.com/Hyunjoonkim/Hyunjoonkim.github.io/files/5733593/Benchmark.data.zip).
There are three input files for each case.
1. “Demand_coordinate_Case#.csv” - a set of demand customers is given with the following characteristics: Demand index, X coordinate, Y coordinate
2. “Existing_HRS_coordinate_Case#.csv” - a set of existing HRSs is given with the following characteristics: Existing HRS index, X coordinate, Y coordinate
3. “Option.csv” - a set of parameters used in the experiments: X-axis range, Y-axis range, W1, W2, n<sub>min</sub>, n<sub>max</sub>, p value used in Minkowski distance calculation, d<sub>min</sub>




