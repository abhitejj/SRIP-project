# SRIP-project: AI/ML-based Downscaling of CMIP6 Climate Scenarios for Predicting Asphalt Pavement Performance.
This project was done under the guidance of Prof. Sushobhan Sen, IIT Gandhinagar, in the Summer Research Internship Program, May-July 2025. I developed a flexible and efficient deep learning pipeline to downscale daily climate outputs (e.g., CMIP‑6) into 24‑hour temperature profiles for multiple weather stations across India. Hourly temperature data is essential for predicting asphalt pavement performance because it captures daily thermal cycles that significantly affect the material’s behavior. Unlike daily averages, hourly data reflects temperature extremes and timing, which influence rutting during peak heat, thermal fatigue due to expansion and contraction, and freeze-thaw cycles in colder regions. These variations impact the stiffness, cracking potential, and overall durability of asphalt layers. Accurate hourly temperatures are especially important for mechanistic-empirical design tools and long-term climate-resilient pavement modeling.

I built ANN and RNN models which were trained on the historical hourly temperature data (ERA5) of 8 different locations in India and evaluated on 2 new locations to see the performance of the model. The main idea was to input the minimum and maximum temperature values of a day and get the 24 hour temperature values of that day. However, we know that the weather on the previous day (or 2 days back) can have some relation to the weather on the current day. It also depends on the day of the year too, which accounts for the seasonal changes. Thus I made 3 models each for ANNs and RNNs - varying the number of min. and max. temperatures being given as inputs.

## Models      
### ANN           
- 1 min-max temperatures (current day)  
- 2 min-max temperatures (current and previous day)
- 3 min-max temperatures (current and previous 2 days)           
### RNN          
- 1 min-max temperatures (current day)  
- 2 min-max temperatures (current and previous day)
- 3 min-max temperatures (current and previous 2 days)
### Hybrid RNN (ANN+RNN layers)
- Learns to blend the two kinds of information—today’s true min/max & seasonal signals, plus yesterday’s forecast‑based scalars—via its hidden state and recurrence.

