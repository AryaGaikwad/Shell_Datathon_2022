![Shell.ai Hackathon 2022 - EV Charging Network Challenge](https://media-fastly.hackerearth.com/media/hackathon/shellai-hackathon-2022/images/9996e1d614-hackerearth_banner.jpg)

## Description

This repository contains the solution for the Shell.ai Hackathon 2022 EV Charging Network Challenge. Our team achieved a score of 72% using an ARIMA model to optimize the placement of EV charging stations to cater to forecasted demand.

## Problem Statement

In the mobility sector, the demand for electric vehicle (EV) charging stations is rapidly increasing. The main challenge is to optimally place these charging stations to ensure a comfortable and efficient charging experience for EV owners while reducing carbon emissions. This challenge is particularly significant as EVs become more popular in different geographies and scales.

The goal of the Shell.ai Hackathon was to find a solution to optimally place EV charging stations that remain robust to demographic changes. This involved forecasting EV charging demand and optimizing EV infrastructure placement.

## Solution Overview

Our team used an ARIMA (AutoRegressive Integrated Moving Average) model to address the problem. The ARIMA model is a time-series forecasting method that can be applied to predict future EV charging demand based on historical data.

### Data Preparation

- We started by dividing the geographic region into equal-sized blocks.
- Each block was represented by a demand point, indicating the total EV charging demand for that block.
- We created demand maps using historical data to forecast the EV charging demand for each demand point.
- We identified supply points, which are predefined public parking locations for installing charging stations.
- Each supply point had a fixed number of parking slots, which represented potential places for EV charging stations.
- We calculated the maximum supply that each supply point could provide based on the number and capacity of slow charging stations (SCS) and fast charging stations (FCS).

### Model Training

- We used the ARIMA model to predict future EV charging demand for each demand point.
- We considered demand-supply constraints to ensure that each demand point had an adequate number of charging stations.
- The objective was to optimize the placement of EV charging stations to cater to the forecasted demand while considering the supply constraints.

### Cost Optimization

- Distance Matrix Calculation:

    - We Utilized the scipy.spatial.distance_matrix to calculate the distance matrix between demand points (locations where EV charging is - required) and supply points (potential charging stations).
    - We Considerd the geographical coordinates (latitude and longitude) of each location.

- Cost Optimization:

    - We Optimized the cost by assigning demand points to the most suitable charging stations based on distance and available charging capacity.
    - We Implemented a prioritization strategy for optimal assignment, considering factors such as distance, charging capacity, and existing charging infrastructure.

- Charging Station Types:

    - We Classified charging stations into Slow Charging Stations (SCS) and Fast Charging Stations (FCS).
    - We Optimized the allocation of demand points to these stations to maximize overall efficiency.

- File Preparation for Submission:

    - We Prepared submission files in CSV format, containing information about the assigned demand points to supply points along with the associated values.
    - We Created additional files providing details about the optimized number of Slow Charging Stations (SCS) and Fast Charging Stations (FCS) for each location.

### Results

Our solution achieved a score of 72%, demonstrating the effectiveness of our approach in optimizing the placement of EV charging stations.



## Acknowledgments

We would like to thank Shell.ai for organizing the hackathon and providing the opportunity to work on this challenging problem.
