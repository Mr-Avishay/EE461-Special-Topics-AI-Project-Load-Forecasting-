# EE461-Special-Topics-AI-Project-Load-Forecasting-
This project focuses on applying advanced machine learning and dimensionality reduction techniques to forecast electricity load demand for Tonga Power Limited (TPL).

# Accurate load forecasting is vital for:
- Ensuring grid stability
- Managing renewable integration (solar, wind, BESS)
- Improving energy efficiency
- Supporting future planning initiatives in Tonga

### Weeks 2–6 Progress: Data Familiarization and Visualization

## Objective
- Understand the historical electrical load data from Tonga Power Limited (TPL)
- Preprocess the data: handle missing values, normalize, and clean inconsistencies
- Visualize datasets to observe patterns, trends, and anomalies
- Begin dimensionality reduction (PCA)

## Tasks Completed
- Mapping generation sites
  ![image](https://github.com/user-attachments/assets/7a1b5542-93d8-4ba0-9ded-03e3c1c8d7cc)

This image is provied to show the pinpoints of the location of the 10 power stations. The imagery was built/made using the inbuilt "geoscatter" command and using 'topographic' as our choice of color trace. The code uses the latitude and the longitude provided from the "GSL" file to map out the accuracy of the location.
- Importing and preprocessing data
![image](https://github.com/user-attachments/assets/5b0b26b9-9956-432f-8799-6e77f143e247)
The table above is the datasets that was collected from TPL. It was than preprocessed using the primary EDA methods. Firstly the data was imported and checked  for any irregularites. The common irregularity founc was the absnce of data for some years, for instance, the "RE_GEN", which is the generation of power using renewable energy sources, was recorded from the month of August in the year 2012. The rest of the previous years was labeled as 'NaN' as it was empty. Using the skills learnt from the practicals, the commands "fillmissing" and "removevars" were used to tidy up the table. 
- Visualizations:
  - Histograms of:
    - Generation
       ![image](https://github.com/user-attachments/assets/8c2980fd-e9d1-4ccf-8d1e-ecec5f0c0b90)
Using the "histogram" command we were able to generate a graphical representation of the generation of power produced over a monthly basis. Through this we are able to identify patterns, see trends in the production stages and/or anomalies in the data. Through the visualization we can identify facts as such, the production of energy within the range of 4.5 x10^6 kW/H till 4.675 x10^6 kW/H was generated at a count of 26 times.
    - Parasitic losses
      ![image](https://github.com/user-attachments/assets/fc2a772b-681a-4986-8297-b1fb1f0d1dbe)
This histogram plays a crucial in understanding the behavior of parasitic losses within a generation system. It provides a more clear insight into how these losses are distributed across different time zones (Monthly basis). It helps the engineers and technicians in assessing the system performance and indentifying key ares for improvements.
    - Line losses
      ![image](https://github.com/user-attachments/assets/230ddacc-0586-4f5a-b385-71b1243b77d8)
The histogram above shows the line losses and the amount of time a certain amount of line loss was expeerienced. The histogram shows that the line losses are predominantly around the range of 400,000 to 600,000 kWh with the most around 500,000 kWh. Additionally, the histogram shows that the line loss has also varied greatly wtih some recordings being around 2,000,000 kWh, altough with very very less recurrence. This histogram allows users especially engineers to well grasp the range within line losses occur.
  - Scatter plots of generation metrics (Generated, Sent Out and Billed)
    ![image](https://github.com/user-attachments/assets/7eab80d3-d281-42c1-a671-16e0bb10f518)
The above scatter plot shows the Generated(total electricity generated), Sent out(total electricity sent out to the grid), and Billed(Electricity billed to consumers) against the duration. Through this scatter plot, it can be noted that all three variables have an increasing trend with over time, indicating great electricity generation, sent out and consumption over time. It is also seen that the Generated power (blue) is greater than the other two variables due to lossess.
- Principal Component Analysis (PCA) with Pareto chart and component variance analysis
  ![image](https://github.com/user-attachments/assets/6ef5411d-7079-4cfa-aa35-d9fdc24cb4d5)

In the above Pareto chart, each bar gives the component wtih the height of the bar showing how much that single component contributes. Meanwhile the redline gives the cumulative percentage of the components combined. Here, it can be seen that 80% is reached by the third component.

## Remarks
Upon completion of Data collection and preprocessing which included examing, cleansing and visualizing the data, normalization was carried out along with PCA. In the coming weeks, other linear techniques such as LDA will be explored and non linear techniques such as CCA will also be explored before moving onto feature engineering.

# Week 7 Progress: Advanced Exploratory Analysis

## Objective For Week 7
- Explore deeper relationships through PCA, CCA, and t-SNE
- Analyze intrinsic dimensionality
- Visualize clustering and transitions

## Tasks Completed
- Cleaned Dataset
  ![image](https://github.com/user-attachments/assets/4744de7c-7664-43fd-ae8c-8745f880987b)

Important variables are being kept by filtering out other variables.

- 3D Scatter plots
  ![image](https://github.com/user-attachments/assets/1856536d-4c8d-4be4-81de-6181ae218501)

This 3D scatter plot visually compares the three key operational variables: generated, sent-out, and billed power. Each point is colored by the corresponding line loss, helping to identify how efficiently power is being transmitted and where losses may be excessive. It provides a high-level overview of the relationship between production and consumption and highlights potential outliers or inefficiencies in the energy flow, forming a baseline understanding of system performance.

- grouped scatter plots
  ![image](https://github.com/user-attachments/assets/968d8500-afa2-40a9-9296-10ecfc237aec)

This 2D scatter plot groups monthly billed and sent-out power data by year using distinct colors. It allows for the observation of annual trends, detecting any systemic shifts or performance variations over time. This visualization is particularly useful for spotting gradual improvements or deteriorations in the energy distribution system and understanding the temporal evolution of billing accuracy relative to transmission.

- Principal Component Analysis (PCA) (2D biplots)
  ![image](https://github.com/user-attachments/assets/2c35fecc-cb95-43a0-895b-1f1b6c2af71d)

The 2D Biplot above is of normalized data with respect to the principle components (PC1 and PC2) and the variables Billed, Genereated, Sent out and Re_Gen which represents the power that is generated from renewable energy which in this case is solar energy, wind energy and BESS. It can be seen that Re_Gen has a very high positive correlation on PC1. Billed can be said to have least influence on PC1 and PC2. Due to its weak correlation, billed may require feature engineering to improve forecasting accuracy. Meanwhile, there is very little separation between the Generated and Sent out variables due to the difference from line loss.

- PCA (3D biplots)
  ![image](https://github.com/user-attachments/assets/6358be27-134e-4ab7-b6b0-81ee42774db5)

The figure above is a 3D plot of normalized data with respect to principle components and the variables, Billed, Generated, Sent ot and Re_Gen.

- Correlation heatmap
  ![image](https://github.com/user-attachments/assets/6e68dfcc-9f1f-4386-8470-8492d4b89cf8)

The heatmap above shows the pairwise relationships between the four variables—GENERATED, SENT_OUT, BILLED, and REGEN—are displayed in this correlation heatmap. The Pearson correlation coefficient, which measures the strength and direction of a pair of variables' linear relationship, is displayed in each cell of the matrix. Since every variable has a perfect correlation with itself, all of the diagonal values are 1. Stronger positive correlations are indicated by darker blue hues in the heatmap, which shows the correlation's magnitude. All four variables are positively and strongly associated, according to this heatmap, GENERATED, SENT_OUT, and BILLED are close correlated. This suggests that energy flows and is tracked consistently throughout the generation, distribution, and billing operations. REGEN's somewhat lower correlation raises the possibility that it has a secondary function or is more variable.

- Dy/Dx plot & Pareto
  ![image](https://github.com/user-attachments/assets/25af2ef7-c291-41ef-bd2a-d05b1a59638c)

  ![image](https://github.com/user-attachments/assets/4495a46c-736b-4314-af22-44773a481f92)

The Pareto chart above shows the variance explained by both the principle components that were deduced from PCA dimensionality reduction. The chart shows that the first component, PC1, captures almost all the variance while the second component has very minimal contribution which also makes the intrinsic dimensionality of the dataset to be 1. This shows that the variables are highly redundant which may be due to the three variables Billed, Generated and Sent out as they are only separated by small losses. Meanwhile, the dy-dx plot shows that the distance in the reduced dimensional space remains very close to that of the original.

# Remarks
Upon completion of the PCA techniques the techniques to look at will be the:
- Curvilinear Component Analysis (CCA).
- t-distributed Stochastic Neighbor Embedding (t-SNE).
- Engineering Features.


### Week 8 Progress: Feature Engineering

## Objectives For Week 8
- Engineer new features for model improvement
- Compare Techniques with original data

## Tasks Completed
- Feature creation:
Five Key Engineered Features
          -  Lagged Bill
This is used for predicting the current or the next months billed power or consumed power by utilizing the previous months data.
          - 12  Month Rolling Average
This uses the average of the last 12 months data to simply smooth out any irregularites.
          - System Efficiency
Summarizes the efficiency by comparing the generation with consumption(billed).
          - Demand Growth Rate
This represents the growth rate of the demand in percentage. In order words, how fast the demand changes.
          - Seasonal Encoding
This represents the different weather patterns which in this case will be summer and winter(slightly colder period in Tonga) by using sine and cosine.
- PCA on engineered features (dy/dx plots)
  ![image](https://github.com/user-attachments/assets/699dd16e-a79e-4308-bd5b-c5c6f7bfa3c8)

- CCA on engineered features (dy/dx plots)
  ![image](https://github.com/user-attachments/assets/515a60f8-ed54-444b-8779-c10d3821a8b4)

### Week 9 Progress: Feature Engineering

## Objectives For Week 9

- Creating models to test our data and predict values
  
## Modelling for our Original Features

  - 1) The ARIMA - Autoregressive Integrated & Moving Average
  
  ![image](https://github.com/user-attachments/assets/a0de6dc7-590b-4efd-a87a-c3003f4b14e0)
       
  - 2) SARIMA - Seasonal Autoregressive Integrated & Moving Average
  
  ![image](https://github.com/user-attachments/assets/bd16a455-730a-4f8d-884f-0cd82a477e04)
       
  - 3) LSTM - Long Short Term Memory
  
  ![image](https://github.com/user-attachments/assets/fc2b293d-e74d-45fa-958a-ffbeca37e1c3)
       
  - 4) CNN -  Convolutionary Neural Newtworks
       
  ![image](https://github.com/user-attachments/assets/efb25707-2c9e-4b98-8094-c17bbf135d2b)

   
## Modelling for our Original features together with the Engineered Features

  - 1) The ARIMA - Autoregressive Integrated & Moving Average
       
  ![image](https://github.com/user-attachments/assets/37766484-6ee2-4b9f-9572-b9d930993e51)


  - 2) SARIMA - Seasonal Autoregressive Integrated & Moving Average
       
  ![image](https://github.com/user-attachments/assets/477f2e1c-8011-49b7-81aa-96b69d217f94)
       
  - 3) LSTM - Long Short Term Memory
       
  ![image](https://github.com/user-attachments/assets/4340192c-d89d-428e-98c4-9839aed6d6ab)


  - 4) CNN -  Convolutionary Neural Newtworks
       
   ![image](https://github.com/user-attachments/assets/ad0143f6-e425-4239-bbd6-a81e0013f585)

# Remark
So far 4 models have been trained and tested, ARIMA, SARIMA, LSTM, CNN and Linear Regression. After inspecting the results obtained, the ARIMA and Linear Regression model produced the best results as the RMSE, MAE and MAPE values more desirable. However, the next tasks will include improving all the models particularly the LSTM and CNN by adding more layers and complexity to the model in order to increase the performance of the models. Also, at least two other models will be researched on in the coming weeks and trained, allowing a wider range possible models to choose from. 
  
### Week 10 Progress: Feature Engineering

## Objectives For Week 10

- Creating models for Generation Scheduling
  
##  MANUAL INPUT SECTION
#  Total load demand for the month (in MWh)
 totalLoad =  1400/720

# Define generation sites manually
# Format: {'SiteName', 'Type', Capacity_MW}
sites = {
    %'Diesel Powerplant Popua', 'diesel', 600;
    'Solar Farm Maama Mai ',      'solar',  1.412;
    'Solar Farm Mata o e Laa',      'solar',  1.3;
    'Solar Farm Singyes',    'solar',   2.13;
    'Solar Farm Sunergise 1',    'solar',   2.3;
    'Solar Farm Sunergise 2',    'solar',   2.3;
    'Solar Farm Sunergise 3',    'wind',   2.3;
    'Wind Farm I o Manumataongo',    'solar',   1.375;
![image](https://github.com/user-attachments/assets/c7b0b95d-f90c-453c-beb7-3ce75bcfee97)

The table above shows the Renewable sites with its Capacity in MW

#  Generation Scheduling
remainingLoad = totalLoad;

for i = 1:height(genTable)
    cap = genTable.Capacity(i);
    alloc = min(cap, remainingLoad);
    genTable.Allocated(i) = alloc;
    remainingLoad = remainingLoad - alloc;
    if remainingLoad <= 0
        break;
    end
end

# OUTPUT 

 Generation Scheduling 
 ![image](https://github.com/user-attachments/assets/97272852-7305-4793-b201-4555e3f9c243)
 As evident fro the table above, the load demand is met and being supplied from two solar farm generation site. 

## Remark
So far the first priority for supplying load demand from Renewable Generations sites first and the remaining load demand to be supplied by Diesel Generators. Although this is not practical enough since solar irradiance and wind speed, there is still a need to turn ON diesel generators for spinning reserves. 
