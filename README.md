# MechaCar_Statistical_Analysis
Statistical review of production data for auto manufacturing team's prototype vehicles.

## Linear Regression to Predict MPG

![image of MPG_linear_regression_output](/Images/MPG_linear_regression_output.png)

### Some variables provide non-random amount of variance to the MPG values in our dataset
Using multiple linear regression, and loading all variables into the model using the MechaCars dataset, we find that ground_clearance, vehicle_length, and Intercept all have a significant impact on MPG. 

Each ```Pr(>ltl)``` value in the summary output represents the probability that the coefficient contributes a random amount of variance to the linear model. According to the results pictured above, we can see the following statistically significant p-values, providing a non-random amount of variance to the mpg values:

- (Intercept) 5.08e-08
- vehicle-length 2.60e-12
- ground_clearance 5.21e-08

Because these values are so low (p<0.0001 in all cases), we can **reject the null hypothesis** and conclude that both vehicle length and ground clearance likely influence MPG.  

### The slope of the linear model is not zero

Because we found variables (ground clearance and vehicle length) which are statistically significant in predicting the response variable (MPG), there is a non-zero slope. 

```MPG = 6.27(vehicle_length) + 0.001(vehicle_weight) + 0.07(spoiler_angle) + 3.55(ground_clearance) - 0.01```

### Further study is warranted to predict MPG

Because Intercept is statistically significant, there may be other factors and variables contributing to the variation in MPG that were not included in this model. Therefore, this model does not predict MPG of MechaCar prototypes effectively. Other variables which contribute to the variation in MPG may still need to be collected or observed.

## Summary Statistics on Suspension Coils

The MechaCar manufacturers are interested in the following question: 

    * The design specifications for the MechaCar suspension coils dictate that the variance of the suspension coils must not exceed 100 pounds per square inch. Does the current manufacturing data meet this design specification for all manufacturing lots in total and each lot individually? 

To provide the data the manufacture needs to answer this question, I ran used the summarize() function to create a table of summary statistics on the PSI column in the Coils dataset for all the lots. 

```
total_summary <- summarize(Coils, meanPSI=mean(PSI), medianPSI=median(PSI), variancePSI=var(PSI), SDPSI=sd(PSI))
```

![image of summary_table for PSI across all lots](/Images/total_summary.png)

The variance of suspension coils for all manufacturing lots in total is 62.29 pounds per square inch. This meets their design specifications that PSI should not exceed 100 pounds per square inch.

Then, the data was grouped by Manufacturing Lot in order to summarize the statistics for PSI within each lot. 

```
lot_grouping <- group_by(Coils, Manufacturing_Lot)

lot_summary <- summarize(lot_grouping, Mean=mean(PSI), Median=median(PSI), Variance=var(PSI), SD=sd(PSI))
```

![image of total_summary for PSI in each lot](/Images/lot_summary.png)

By breaking down the statistics for each lot, we can see that in Lot 3, there is a variance in PSI of 170.29 pounds per square inch. This does not meet the MechaCar design specifications as it exceeds 100PSI. 

