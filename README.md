# Marketing-Mix-Modelling
It’s a statistical analysis technique used to measure the impact of various marketing activities on business outcomes, like sales or revenue, and to optimize marketing spend
# Bayesian Marketing Mix Modeling (MMM)

![Sales Contribution Chart](https://i.imgur.com/example-contribution-chart.png) A comprehensive Python script for performing Marketing Mix Modeling (MMM) using a Bayesian approach with **PyMC**. This project analyzes the effectiveness of different marketing channels (TV and Radio) on sales, accounting for real-world effects like advertising saturation and adstock (carryover effects).

The model provides actionable insights, including **sales contribution** by channel, **marginal ROI**, and a recommended **optimal budget allocation**.

---

## 📋 Table of Contents

- [Features](#-features)
- [How It Works](#-how-it-works)
- [Technologies Used](#-technologies-used)
- [Getting Started](#-getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
- [Usage](#-usage)
- [Understanding the Output](#-understanding-the-output)
- [License](#-license)

---

## ✨ Features

- **Adstock Transformation**: Models the lingering (carryover) effect of advertising using a geometric decay function.
- **Saturation Modeling**: Implements the Hill function to capture the diminishing returns of increased ad spend.
- **Synergy Effects**: Measures the interaction effect between different marketing channels (e.g., how TV and Radio advertising amplify each other).
- **Bayesian Inference**: Uses **PyMC** to build a robust model that quantifies uncertainty in its estimates.
- **Sales Contribution Analysis**: Decomposes total sales to show the contribution from each channel, synergy, and a baseline.
- **Marginal ROI Calculation**: Estimates the return on investment for the next dollar spent in each channel.
- **Budget Optimization**: Recommends an optimal budget split based on channel ROI.
- **What-If Simulator**: A function to simulate expected sales under different budget scenarios, with visualizations.

---

## 🤔 How It Works

The script follows a standard but powerful MMM pipeline:

1.  **Data Loading**: Downloads and loads the marketing dataset directly from Kaggle using the `kagglehub` library.
2.  **Adstock Transformation**: Applies a geometric adstock function to TV and Radio spending data to model the decaying impact of past ads.
3.  **Saturation Transformation**: The adstocked data is then passed through a Hill function to model the non-linear, saturating effect of advertising on sales.
4.  **Bayesian Modeling**: A linear model is built in PyMC to regress sales against the transformed TV and Radio data, including a baseline and a TV-Radio synergy term. The model's parameters (`beta` coefficients) are estimated via MCMC sampling.
5.  **Insight Generation**: The posterior distributions from the model are used to calculate the average contribution of each component to sales, derive marginal ROI, and simulate outcomes for budget planning.

---

## 🛠️ Technologies Used

-   **Python 3.x**
-   **PyMC**: For Bayesian modeling and MCMC inference.
-   **Pandas**: For data manipulation and analysis.
-   **NumPy**: For numerical operations.
-   **Scikit-learn**: For data preprocessing (StandardScaler).
-   **Matplotlib & Seaborn**: For data visualization.
-   **KaggleHub**: For seamless dataset downloading.

---

## 🚀 Getting Started

Follow these steps to get the project running on your local machine.

### Prerequisites

Make sure you have Python 3.8+ and Pip installed. You will also need a Kaggle account and an API token set up to use `kagglehub`. You can find instructions [here](https://www.kaggle.com/docs/api).

### Installation

1.  **Clone the repository:**
    ```sh
    git clone [https://github.com/your-username/your-repo-name.git](https://github.com/your-username/your-repo-name.git)
    cd your-repo-name
    ```

2.  **Create a virtual environment (recommended):**
    ```sh
    python -m venv venv
    source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
    ```

3.  **Install the required packages:**
    Create a `requirements.txt` file with the following content:
    ```txt
    pymc
    seaborn
    matplotlib
    scikit-learn
    kagglehub
    pandas
    numpy
    ```
    Then run the installation command:
    ```sh
    pip install -r requirements.txt
    ```

---

## 🏃 Usage

Simply run the Python script from your terminal. The script will handle downloading the data, running the model, and generating all plots and insights.

```sh
python your_script_name.py
