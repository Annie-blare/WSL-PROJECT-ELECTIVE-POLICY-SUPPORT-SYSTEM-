# WSL-PROJECT-ELECTIVE-POLICY-SUPPORT-SYSTEM-
WSL PROJECT ELECTIVE


**POLICY SUPPORT SYSTEM**


1.)Introduction:
In our quest to enhance Sustainable Development Goal (SDG) 2, focusing on "Zero Hunger," we delve into the realm of agriculture, starting initially with 2 indicators - RICE PRODUCTION and MAIZE PRODUCTION. Leveraging the KAG2016-17 Agriculture dataset, which encompasses a rich array of factors and indicators, our focus narrows to Maize and Rice production.
The objective is to model stability from both a being's perspective and its neighbors at each district level. By analyzing the impacts of perturbations on various SDG capabilities, the project aims to understand how different indicators behave across districts and visualize these insights on Tableau.
Insights into stability from a being's perspective at each district level, enhancing our understanding of complex systems' dynamics.

Work Done Till Now:
Through rigorous correlation analysis and p-value scrutiny, our mentors have pinpointed several factors that exhibit significant correlation with production in both the  indicators.

My Work:
I am conducting various experiments related to perturbations on factors, both isolated and combined. By visualizing the impacts on all districts for various SDG capabilities, I aim to understand how different perturbations on different indicators behave across districts. My goal is to gain insights into stability from a being's perspective at each district level, enhancing our understanding of complex systems' dynamics.

This analysis aims to provide insights into the factors influencing stability in various districts, aiding in better decision-making and resource allocation for sustainable development.


------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Part A: Isolated Factor Analysis (Only TotalNPK)
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Experiment 1:
Perturbating One Factor to Study Impact Analysis on SDG Capability (Maize Production)

The initial experiment hones in on Maize Production, a crucial component of SDG 2. They have identified seven key factors from the dataset that significantly impact Maize production. Our approach involves perturbating these factors individually to observe their isolated effects on production levels across various districts. By visualizing these impacts comprehensively, we aim to unravel the intricate dynamics of how each factor influences the overall stability and productivity of Maize cultivation. Factor chosen=TOTALNPK Capability target=Maize Production

EXPERIMENT 2:

** Perturbating One Factor to Study Impact Analysis on SDG Capability (Rice Production)**

The experiment hones in on Rice Production, a crucial component of SDG 2. They have identified five key factors from the dataset that significantly impact Maize production. Our approach involves perturbating these factors individually to observe their isolated effects on production levels across various districts. By visualizing these impacts comprehensively, we aim to unravel the intricate dynamics of how each factor influences the overall stability and productivity of rice cultivation. Factor chosen=TOTALNPK Capability target=Rice Production



Approach:
Data Preprocessing: Import necessary libraries: pandas, statsmodels.api, seaborn, numpy, and matplotlib.pyplot. Define a function remove_pattern to clean column names by removing trailing numbers. Load the Kaggle 2016-17 Agriculture dataset and clean column names.

Data Manipulation: Create new columns for Total Production and FCR (TotalNPK / Total Production) as TOTALNPK is for all crops and we need a proportion for Rice Production and Maize Production. Calculate NPK_Rice and NPK_Maize based on TotalNPK and respective production values.

Perturbation Design: Select the perturbation levels (user_perturbations) for NPK_Maize and NPK_Rice separately.

Linear Regression Analysis: Implement a function perform_analysis that takes the dataset, factor (TotalNPK), Capability (Maize Production), and perturbations as input. Fit a simple linear regression model between TotalNPK and Maize Production. Calculate the slope and intercept of the regression line and similarly for Rice Production, Implement a function perform_analysis that takes the dataset, factor (TotalNPK), Capability (Rice Production), and perturbations as input. Fit a simple linear regression model between TotalNPK and Rice Production. Calculate the slope and intercept of the regression line.

Impact Analysis: For each district, calculate the impact of perturbations on Maize Production using the regression equation. Store the results in a DataFrame with columns for District, Perturbation (%), Maize Production (old), Maize Production (new), Change in Maize Production, and Percentage Change and likewise for Rice Production.

Visualization: Define a function plot_heatmap to plot a heatmap showing the percentage change in Maize Production and Rice Production separately for different NPK perturbations across districts. Use seaborn and matplotlib to create the heatmap.

Formula used: # New Capability value= m* Perturbed Value +c
            # Percentage change= ((New Capability value)-(Old Capability Value))/Old Capability Value
            # Example:
              # You can perform this by taking the example formula below for (NPK_Rice+10%) i.e. there has
              # been an increase in NPK_Rice values by 10%:
              # (based on y=mx+c)
              # Rice_Production_old = {the original Capability values from the dataset}
              # Rice_Production_new = m*(1.1*NPK_Rice) + c
              # Change in Rice_Production = Rice_Production_new - Rice_Production_old
              # Predicted Change in Rice_Production = m*0.1*NPK_Rice
              # Percentage Change in Rice Production = Predicted Change in Rice Production/Rice_Production_old


------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Part B:  Multiple Factor Analysis (NPK+ other factors)
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

EXPERIMENT1: MAIZE CASE FILE
-----------------------------


I RECEIVED A MAIZE CASE FILE TO CONSIDER WHERE IT HAS COLUMNS AS FACRORS THAT CORRELATED VERY WELL WITH MAIZE PRODUCTION WHICH WAS BROUGHT OUT BY CORELATION ANAYSIS AND P-VALUE. FACTORS WERE:

#1. NPK_Maize(which is perturbed)

#2.NetAreaIrrigated_Wells_NetAreaIrrigated_Maize

#3.NetAreaIrrigatedUnderDifferentSources_TubeWells_NetIrrigatedArea_Maize

#4.NetAreaIrrigatedUnderDifferentSources_LiftIrrigation_No_Maize

#5.MotorVehicles_Tractors_Maize

#6.TotalAgricultureLoan_Maize

#7.AreaUnderCereals_Maize

MY WORK: ** Perturbating One Factor in presence of other factors as well to Study Impact Analysis on SDG Capability (Maize Production)**

The experiment hones in on Maize Production, a crucial component of SDG 2. They have identified seven key factors from the dataset that significantly impact Maize production. Our approach involves perturbating a single factor in presence of other factors(regressing with all factors but perturbating one factor) to observe the effects on production levels across various districts. By visualizing these impacts comprehensively, we aim to unravel the intricate dynamics of how each factor influences the overall stability and productivity of rice cultivation. Factor chosen=TOTALNPK, Capability target=Maize Production



EXPERIMENT2: RICE CASE FILE
-----------------------------


I RECEIVED A RICE CASE FILE TO CONSIDER WHERE IT HAS COLUMNS AS FACRORS THAT CORRELATED VERY WELL WITH RICE PRODUCTION WHICH WAS BROUGHT OUT BY CORELATION ANAYSIS AND P-VALUE. FACTORS WERE:

#1.TOTALNPK(which is perturbed)

#2.NetAreaIrrigated_Tanks_NetAreaIrrigated

#3.NetAreaIrrigatedUnderDifferentSources_LiftIrrigation_No

#4.NetAreaIrrigatedUnderDifferentSources_LiftIrrigation_NetIrrigatedArea

#5.AreaUnderCereals_Paddy

MY WORK: ** Perturbating One Factor in presence of other factors as well to Study Impact Analysis on SDG Capability (Rice Production)**


 Approach:
-------------

The experiment hones in on Rice Production and Maize Production, a crucial component of SDG 2. They have identified seven key factors from the dataset that significantly impact Maize production and Rice Production. Our approach involves perturbating a single factor in presence of other factors(regressing with all factors but perturbating one factor) to observe the effects on production levels across various districts. By visualizing these impacts comprehensively, we aim to unravel the intricate dynamics of how each factor influences the overall stability and productivity of rice cultivation. Factors(there are 5 total), Capability target=Rice Production

1.Data Preprocessing:

Import necessary libraries: pandas, statsmodels.api, seaborn, numpy, and matplotlib.pyplot. Define a function remove_pattern to clean column names by removing trailing numbers. Load the Kaggle 2016-17 Agriculture dataset and clean column names.

2.Data Manipulation: Create new columns for Total Production and FCR (TotalNPK / Total Production) as TOTALNPK is for all crops and we need a prportion for Rice Production and Maize Production. Calculate NPK_Rice and NPK_Maize based on TotalNPK and respective production values.

3.Perturbation Design: Select the perturbation levels (user_perturbations) for NPK_Rice and NPK_Maize.

4.MULTIPLE Regression Analysis: Implement a function perform_analysis that takes the dataset, factor (NPK_Rice,NetAreaIrrigated_Tanks_NetAreaIrrigated_Rice,NetAreaIrrigatedUnderDifferentSources_LiftIrrigation_No_Rice,NetAreaIrrigatedUnderDifferentSources_LiftIrrigation_NetIrrigatedArea_Rice,AreaUnderCereals_Paddy), Capability (Rice Production), and perturbations as input. Fit a multiple linear regression model between TotalNPK and Rice Production. Calculate the slope and intercept of the regression line and similarly for Maize, Implement a function perform_analysis that takes the dataset, factor (TotalNPK,NetAreaIrrigated_Wells_NetAreaIrrigated_Maize,NetAreaIrrigatedUnderDifferentSources_TubeWells_NetIrrigatedArea_Maize,NetAreaIrrigatedUnderDifferentSources_LiftIrrigation_No_Maize,MotorVehicles_Tractors_Maize,TotalAgricultureLoan_Maize,,AreaUnderCereals_Maize), Capability (Maize Production), and perturbations as input. Fit a multiple linear regression model between TotalNPK and Rice Production. Calculate the slope and intercept of the regression line.

5.Impact Analysis: For each district, calculate the impact of perturbations on Maize Production using the regression equation. Store the results in a DataFrame with columns for District, Perturbation (%), Rice Production (old), Rice Production (new), Change in Rice Production, and Percentage Change and likewise for Maize Production.

6.Visualization: Define a function plot_heatmap to plot a heatmap showing the percentage change in Rice Production for different NPK perturbations across districts. Use seaborn and matplotlib to create the heatmap and likewise for Maize Production.

# Formula used:
           # New Capability value= m1* Perturbed Value +c + m2* old Capability value +...
            # Percentage change= ((New Capability value)-(Old Capability Value))/Old Capability Value
            # Example:
              # You can perform this by taking the example formula below for (NPK_Rice+10%) i.e. there has
              # been an increase in NPK_Rice values by 10%:
              # (based on y=mx+c)
              # Rice_Production_old = {the original Capability values from the dataset}
              # Rice_Production_new = m*(1.1*NPK_Rice) + c+m2* old Capability vlue +...
              # Change in Rice_Production = Rice_Production_new - Rice_Production_old
              # Predicted Change in Rice_Production = m*0.1*NPK_Rice
              # Percentage Change in Rice Production = Predicted Change in Rice Production/Rice_Production_old



------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
HOW TO RUN THE CODE:
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
If  you want to run it on your local machine, you can do so by following these steps:

(1.)Download the Notebook: Download the Colab notebook (.ipynb file) to your local machine.

(2.)Install Jupyter Notebook: If you haven't already installed Jupyter Notebook, you can install it using pip:
     >>>       pip install notebook
(3.)Open Jupyter Notebook: Open a terminal or command prompt and navigate to the directory where your downloaded .ipynb file is located. Start Jupyter Notebook by running the following command:
    >>>        jupyter notebook
This will open a new tab in your web browser with the Jupyter Notebook interface.

(4.)Upload the Notebook: Click on the "Upload" button in the top right corner of the Jupyter Notebook interface and select your downloaded .ipynb file to upload it.

(5.)Upload the dataset given and Run the Notebook: Once the notebook and dataset is uploaded, you can run it cell by cell by clicking on a cell and pressing Shift + Enter. Make sure to update any file paths in the notebook to point to the correct locations on your local machine.

(6.)Review the Results: As you run each cell, you should see the output generated by your code. You can analyze the impact of perturbations on Maize Production across districts based on the output.



OR

(1.)simply open the Colab notebook (.ipynb file) in Google Colab ,first Upload Dataset: Upload the Kaggle 2016-17 Agriculture dataset (Agriculture_KAG_2016_17(AgricultureIndicatorsandFactors).csv) to your Colab environment. You can do this by clicking on the "Files" icon in the left sidebar and then selecting "Upload".

(2.)Execute the Code: Run each code cell by clicking the play button next to the cell or by pressing Shift + Enter. This will execute the code and display the results or visualizations.



 ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
   Tableau Visualisations
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------    The attached case files act as data source for tableau visualisations.       
