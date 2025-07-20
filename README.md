# Project--Covid19_Data_analysis
## Project Overview
This project aims to analyze the maximum COVID-19 infection rates across different countries and correlate them with indicators of happiness such as GDP per capita, social support, health and freedom using the COVID-19 Confirmed Dataset and the World Happiness Report. We explore patterns using data visualization and regression analysis to investigate if there's relationship between national well-being and infection spread.

## Methodology
 1. Importing Libraries
    We used essential Python libraries such as:
    - numpy and pandas for data manipulation.
    - matplotlib.pyplot and seaborn for data visualization.
2. Loading and Preprocessing the COVID-19 Dataset
   - Loaded the CSV file using pd.read_csv().
   - Aggregated the COVID-19 dataset at the country level using groupby() and sum() to get a       consolidated timeline per country.
  
3. Visualizing the Spread
   Plotted the cumulative confirmed cases for countries like:
    - China
    - India
    - Spain
    - Canada
    - Greece, etc.
4. Calculating Infection Growth
   We computed the first derivative of each country's confirmed cases timeline using .diff() to     measure daily new infections. The maximum value of this derivative gave us the peak infection    rate.
5. Creating a Refined Dataset
   We created a new DataFrame corona_data that only contains the peak infection rates per  country.
6. Processing the Happiness Dataset
      - Dropped unnecessary columns like Overall rank, Score, Generosity, and Perceptions of     corruption.
      - Set "Country or region" as the index to facilitate joining with the COVID-19 dataset.
 7. Merging the Datasets
    Merged both datasets using an inner join on the country index to align the countries present     in both datasets.
## Exploratory Data Analysis & Visualizations
We visualized the relationship between happiness indicators and maximum infection rates using seaborn scatter plots and regression plots.
    - GDP per capita vs Max Infection Rate
    - Social Support vs Max Infection Rate
    - Healthy Life Expectancy vs Max Infection Rate
    - Freedom to Make Life Choices vs Max Infection Rate 
  Since infection rates are skewed, we used log scaling to normalize the infection rate variable:
     ex- np.log(data["Max_infection_rates"])
## Key Findings
    - Countries with higher GDP per capita generally had lower maximum infection spikes,    indicating a potential link between economic development and better control over virus spread.
    - Social support and freedom to make life choices showed negative correlations with infection peaks, suggesting countries with strong societal systems and governance may have handled the pandemic more effectively.
    - A similar trend was observed with healthy life expectancy—implying robust healthcare systems may have mitigated the spread.
## Conclusion
By combining COVID-19 case data with happiness indicators, this analysis suggests that nations with higher standards of living and well-being metrics tend to experience lower peaks in infection rates. These insights underline the importance of investing in public health infrastructure and societal support systems for managing pandemics.
