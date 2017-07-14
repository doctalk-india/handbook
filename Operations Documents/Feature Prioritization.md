# Feature Prioritization

### Metrics
* Effort - This value is based on a combination of time it would take to implement for one engineer.  
The scale is currently defined as:  
1: Small - 1 to 2 days  
2: Medium - 1 week  
3: Large - 1 PL  
4: XL - 1.5 PL  
5: XXL - 2 PL  
* Urgency - Urgency defines time sensitivity, with the following scale:  
0: no deadline - 0 to 4 KPI points (look below to understand KPI points)  
1: within 2 PLs - 5 to 12 KPI points  
2: this PL - 13 to 20 KPI points  
* Impact - The impact value indicates the potential impact on profitability.  
Note that the values may be negative. That indicates that the project could have a negative impact on profitability. This doesn't necessarily mean the project won't get done, but as you'll see in a bit, it means the project must give greater benefits in other ways.
-2: significant negative impact  
-1: negative impact  
0: little to no impact  
1: some impact  
2: significant impact  
* Risk Factor - This indicates the risk factor if the project is NOT implemented.  
0: Little or no risk - 0 to 4 KPI points  
1: Some risk - 5 to 12 KPI points  
2: Significant risk - 13 to 20 KPI points  
* Innovation - Indicates innovation level, which considered we consider a positive influence on long term growth.  
0: little or none 😒  
1: ahead of the curve 😎  
2: groundbreaking 💥  

Scoring for priority - With these individual scores defined, we can now calculate a priority value. We consider this priority value to be a guide, not a rule. As a guide though, it's quite helpful when making decisions about what to do next.  
Here is the formula:  
**(Impact * 3) + (Urgency * 3) + (Risk Factor * 4) + (Innovation * 2) - (Effort * 3)**

### KPI (Key Performance Indicator) Points
Doctor Engagement (DE) - 6  
Patient Conversion (PC) - 5  
Patient Engagement (PE) - 3  
Monthly Revenue (MR) - 3  
Doctor Growth (DG) - 2  
Doctor Conversion (DC) - 1  

Each value has been assigned based on how important its corresponding KPI is to the company's success.

### Scoring a Feature
* Figure out which KPIs are definitively affected by that feature.  
* Calculate KPI points.  
* Assign Metric points.  
* Score using the formula - **(Impact * 3) + (Urgency * 3) + (Risk Factor * 4) + (Innovation * 2) - (Effort * 3)**.
