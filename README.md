# Bike-sharing System Allocation
## 1. Project Description and Scope
The downtown city council intends to implement a bike-sharing system to reduce traffic congestion and promote eco-friendly transportation. However, due to limited space and budget, the council must select the most suitable locations for a limited number of bike stations.

The primary goal of this project is to develop a proof of concept for the bike-sharing planning optimization software. The project aims to demonstrate the effectiveness of the optimization software by creating a prototype using 253 points as a proxy for the target user groups and assuming the demand at each point ranges from 1 to 3. The project assumes that bike stations can be built at any of the selected points, and the demand will be fulfilled only by the nearest bike station.

The objective of the project is to determine the optimal locations for bike stations while minimizing the total distance of each demand point to the station using the lowest budget.

![image](https://user-images.githubusercontent.com/78404450/234769574-2b13e749-9605-424a-9fa4-e88ab7da925b.png)

A similar question has been discussed in the paper "Balanced maximal covering location problem and its application in bike-sharing". The BMCLP (model 4) was introduced as a model that seeks to minimize the total distance between facilities and demand points while considering facility capacity and budget constraints. In the case of the bike-sharing system, the demand points would be the important points across the downtown area, and the facilities would be the underground bike stations. The objective of minimizing the total distance between stations and points while ensuring capacity and budget constraints aligns with the objectives of the BMCLP.

## 2. Model
![image](https://user-images.githubusercontent.com/78404450/234769887-1ae002db-0c31-4250-8a4b-95827d9b58c5.png)

![image](https://user-images.githubusercontent.com/78404450/234769969-1bc359bf-747a-43cf-9b74-ef6a744ba83f.png)

## 3. Result Discussion and Model Selection
To validate the effectiveness of the model, both models are tested with the following assumptions:

1.	The demand per point is randomly generated within the range of 1 to 3

2.	The minimum number of points that need to be covered is 100

3.	The total budget for the bike station construction is $50,000


By comparing the results, both models are covering the minimum required number of points (100). The base model suggests building two stations that would cover a larger, more dispersed area, whereas the balanced model recommends constructing three stations that would each fulfill closer demand points.

![image](https://user-images.githubusercontent.com/78404450/234770501-387a7c51-8027-47a7-beab-34eba7778282.png)


![image](https://user-images.githubusercontent.com/78404450/234770205-77605d4b-869a-499c-a8d5-7b570255a233.png)       ![image](https://user-images.githubusercontent.com/78404450/234770222-8da2b031-58a9-4cc6-b147-81df81640269.png)

## 4. Scenarios Exploration
After identifying the better model based on rationality of the result, we can further test the model scalability by changing the demand amount. In the previous section, we assumed the minimum number of demand points to be covered is 100, we can increase the customer considered by increasing the minimum required number of points to be covered. This will help us understand how the cost and number of stations required change with an increase in demand. 

![image](https://user-images.githubusercontent.com/78404450/234770400-8d37b2cb-eed8-4463-90f0-b2cc392267e6.png)

## 5. Additional Approach to the Problem
In reality, to maximize the efficiency of the bike-sharing network, companies often have a set of potential locations in mind in which they can erect a station. The set of locations would help narrow down the possible locations of stations and save more resources on the optimization process. For this project, we also looked into solving the problem in the scenario of knowing a set of potential locations in advance.
Since the given data does not include any potential locations for bike stations, we decided to generate this set by using K-Means Clustering. The reason for the utilization of this method is that K-Means seeks to assign data points into clusters around a centroid to minimize within-cluster variances (squared Euclidean distances), and this coincides with the purpose of our project, which is to minimize the Euclidean distances between a bike stations and demand point.

![image](https://user-images.githubusercontent.com/78404450/234770666-089da97a-0846-4b8e-85ba-b7807f2dc8e2.png)




