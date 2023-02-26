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