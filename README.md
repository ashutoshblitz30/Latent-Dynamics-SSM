## Model Performance & Results

The model was evaluated on a held out test set consisting of the most recent **450 days** of Bitcoin price action (concluding March 2026). 

### **Key Metrics**
| Metric | Value | Interpretation |
| :--- | :--- | :--- |
| **Test MSE** | **0.5453** | Error on standardized log-returns. |
| **Baseline MSE** | **0.8841** | Persistence Model (Random Walk). |
| **Variance Reduction** | **~38%** | Improvement over a naive guess. |

### **Visualization: Predicted vs. Actual Returns**
The following plot illustrates the model's ability to track the underlying 'latent' volatility clusters of Bitcoin.

![BTC-USD Forecast vs Actual](results_plot.png)

### **Analysis of the Results**
* **Volatility Clustering:** The model successfully identifies "regimes" of high and low volatility. In the plot, you can observe the SSM correctly predicting the magnitude of returns during the February 2026 market shifts.
* **Signal-to-Noise Ratio:** While the raw MSE of 0.54 may appear high in a standard ML context, in high-entropy financial markets, this represents a substantial extraction of signal. 
* **Phase Lag:** A slight phase lag is visible during "Black Swan" reversals, suggesting that while the GRU transition is robust for momentum, it could be further enhanced by a **Switching State Space** mechanism to handle discrete jumps in market regime.
