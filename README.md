41.4171715.355-0.03652.251

pip install numpy
pip install pandas
pip install seaborn
pip install matplotlib
pip install scikit-learn
pip install tensorflow
pip install ipython

# 💧 Water Potability Analysis & Visualization

A comprehensive Jupyter notebook for exploring water quality characteristics and predicting potability using data analysis, statistical methods, and visualization techniques.

---

## 📋 Table of Contents

- [Overview](#overview)
- [Dataset](#dataset)
- [Features](#features)
- [Requirements](#requirements)
- [Installation](#installation)
- [Usage](#usage)
- [Notebook Structure](#notebook-structure)
- [Key Findings](#key-findings)
- [Visualizations](#visualizations)
- [Author](#author)

---

## 🎯 Overview

This notebook performs an in-depth exploratory data analysis (EDA) of water potability data. It includes:
- **Data Loading & Cleaning** - Handle missing values and invalid entries
- **Statistical Analysis** - Descriptive statistics, correlations, and distributions
- **Exploratory Visualizations** - Animated charts, heatmaps, and comparative plots
- **Outlier Detection** - Identify anomalies using IQR method
- **Class Imbalance Analysis** - Understand potable vs non-potable distribution
- **Distribution Shifts** - Visualize how features differ between classes

**Perfect for:** Water quality researchers, data scientists, and ML practitioners building potability prediction models.

---

## 📊 Dataset

**Source:** Water Quality & Potability Dataset (Kaggle)

**Size:** 3,276 samples × 10 features

**Target Variable:** `Potability` (Binary: 0 = Non-Potable, 1 = Potable)

### Features:
| Feature | Type | Description | Unit |
|---------|------|-------------|------|
| `ph` | Float | Acidity/alkalinity level | pH (0-14) |
| `Hardness` | Float | Mineral content | mg/L |
| `Solids` | Float | Total dissolved solids | ppm |
| `Chloramines` | Float | Chloramines level | ppm |
| `Sulfate` | Float | Sulfate concentration | mg/L |
| `Conductivity` | Float | Electrical conductivity | μS/cm |
| `Organic_carbon` | Float | Organic carbon content | ppm |
| `Trihalomethanes` | Float | Halogenated methane content | μg/L |
| `Turbidity` | Float | Water clarity | NTU |
| `Potability` | Int | Water potability (target) | 0 or 1 |

### Data Quality Issues:
- **Missing Values:** Sulfate (23.8%), pH (15%), Trihalomethanes (4.9%)
- **Invalid Values:** pH = 0 found (physically impossible)
- **Outliers:** Present in multiple features due to sensor errors
- **Imbalance:** 61% non-potable vs 39% potable water

---

## ✨ Features

### 1. **Data Exploration** 📈
- Load and inspect dataset structure
- Display basic statistics and correlations
- Identify missing values and data types

### 2. **Statistical Analysis** 📊
- Descriptive statistics (mean, median, std, variance, skewness)
- Correlation heatmap between features
- Distribution analysis per potability class

### 3. **Visualizations** 🎨
- **Animated bar charts** for class imbalance evolution
- **Pair plots** showing relationships between features
- **Box plots** for potable vs non-potable comparison
- **Violin plots** for distribution comparison
- **KDE plots** for distribution shifts
- **Heatmaps** for correlation analysis

### 4. **Outlier Detection** 🎯
- IQR (Interquartile Range) method
- Identify extreme values per feature
- Flag anomalies for investigation

### 5. **Advanced Analysis** 🔬
- Class imbalance visualization
- Distribution shift analysis between classes
- Feature importance identification
- Data quality assessment

---

## 🛠️ Requirements

### Python Version
- Python 3.7+

### Required Libraries
```
numpy>=1.20.0
pandas>=1.5.0
matplotlib>=3.5.0
seaborn>=0.12.0
scikit-learn>=1.0.0
tensorflow>=2.10.0
ipython>=7.0.0
```

### Optional Libraries
- `tensorflow` - For neural network models (included for future use)
- `PIL` (Pillow) - For GIF generation in animations

---

## 📦 Installation

### Step 1: Clone or Download
```bash
# If using git
git clone <repository-url>
cd water-potability-analysis

# Or download the notebook manually
```

### Step 2: Create Virtual Environment (Recommended)
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

### Step 3: Install Dependencies
```bash
pip install -r requirements.txt
```

Or install individually:
```bash
pip install numpy pandas matplotlib seaborn scikit-learn tensorflow ipython
```

### Step 4: Launch Jupyter
```bash
jupyter notebook main.ipynb
```

---

## 🚀 Usage

### Running the Notebook

1. **Open Jupyter:**
   ```bash
   jupyter notebook main.ipynb
   ```

2. **Run All Cells:** Click `Cell` → `Run All` or press `Ctrl+A` then `Ctrl+Enter`

3. **Or Run Sequentially:** 
   - Press `Shift+Enter` to run each cell one by one
   - This is recommended to see progress and handle potential errors

### Output Files Generated
- **Animated charts** (GIF format) - Class imbalance and distribution shifts
- **Static visualizations** - Heatmaps, box plots, violin plots
- **Statistical summaries** - Console output with key metrics

### Customizing Analysis

**Change Color Scheme:**
```python
# In visualization cells, modify the palette
palette = {0: '#FF0087', 1: '#00F7FF'}  # Pink and Cyan
```

**Filter Data:**
```python
# Keep only high-solids water
high_solids = df[df['Solids'] > df['Solids'].quantile(0.75)]
```

**Adjust Outlier Sensitivity:**
```python
# In outlier detection, modify IQR multiplier (1.5 is standard)
lower = Q1 - 1.5 * IQR  # Change 1.5 to higher value for less sensitivity
upper = Q3 + 1.5 * IQR
```

---

## 📑 Notebook Structure

| Cell # | Type | Purpose |
|--------|------|---------|
| **0** | Code | Import libraries (numpy, pandas, matplotlib, seaborn, sklearn, tensorflow) |
| **1** | Code | Load dataset from Kaggle CSV file |
| **2** | Code | Display first 5 rows of data |
| **3** | Code | Calculate correlation matrix |
| **4** | Code | Descriptive statistics (mean, median, std, variance, skewness, spread) |
| **5** | Code | 🎬 Animated bar chart - Class imbalance evolution |
| **6** | Code | Missing values visualization - Bar chart with color-coded severity |
| **7** | Code | 🎬 Animated distribution shift visualization |
| **8** | Code | Pair plot - Feature relationships by potability class |
| **9** | Code | Box plots - Potable vs non-potable comparison |
| **10** | Code | Violin plots - 3×3 grid showing distributions |
| **11** | Code | KDE (Kernel Density Estimation) plots - Distribution density |
| **12** | Code | 🎬 Animated KDE distribution shift panel |
| **13** | Code | Outlier detection using IQR method |
| **14** | Code | Correlation heatmap (RdPu colormap) |
| **15** | Code | Filter extreme values (high solids & turbidity) |
| **16** | Code | Summary and conclusions |

---

## 🔍 Key Findings

### 1. **Class Imbalance** 
- 61% non-potable vs 39% potable
- Affects model training → requires balancing techniques (SMOTE, class weights)

### 2. **Missing Values**
- Sulfate: 781 missing (23.8%) - Most critical
- pH: 491 missing (15%)
- Trihalomethanes: 162 missing (4.9%)
- **Solution:** Use KNN imputation or median filling

### 3. **Feature Correlations**
- Conductivity ↔ Solids (strong positive correlation)
- pH ↔ Most features (weak correlations)
- Potability has weak correlations with individual features

### 4. **Outliers Detected**
- Solids: High-value outliers (>4000 ppm)
- pH: Impossible values (pH=0)
- Turbidity: Extreme clarity anomalies
- **Action:** Investigate sensor malfunctions or extreme water conditions

### 5. **Distribution Shifts**
- **pH:** Potable water tends toward neutral (7.0)
- **Solids:** Non-potable has higher TDS
- **Conductivity:** Strong difference between classes
- **Turbidity:** Slight difference (less discriminative)

---

## 📊 Visualizations

### Static Plots
- ✅ **Correlation Heatmap** - Feature relationships
- ✅ **Missing Values Bar Chart** - Data quality overview
- ✅ **Box Plots** - Outlier identification
- ✅ **Violin Plots** - Distribution comparison
- ✅ **Pair Plot** - Multi-feature relationships
- ✅ **KDE Plots** - Probability density

### Animated Visualizations 
- 🎞️ **Class Imbalance Evolution** - Shows how class counts build up
- 🎞️ **Distribution Shift Animation** - How feature distributions differ between potable/non-potable

---

##  Next Steps

### For Classification Models:
1. **Data Cleaning** - Handle missing values (use provided cleaning script)
2. **Feature Engineering** - Create polynomial/interaction features
3. **Balancing** - Use SMOTE for class imbalance
4. **Scaling** - StandardScaler or MinMaxScaler
5. **Modeling** - Logistic Regression, Random Forest, XGBoost, Neural Networks
6. **Evaluation** - ROC-AUC, F1-Score, Confusion Matrix

### For Prediction:
```python
# Example: Predict potability for new water sample
new_water = {
    'ph': 7.0,
    'Hardness': 200,
    'Solids': 20000,
    'Chloramines': 7.5,
    'Sulfate': 300,
    'Conductivity': 400,
    'Organic_carbon': 20,
    'Trihalomethanes': 80,
    'Turbidity': 4.0
}

prediction = model.predict(new_water)

##  File Structure

water-potability-analysis/
├── main.ipynb                    # Main analysis notebook
├── requirements.txt              # Python dependencies
├── README.md                     # This file
├── data/
│   └── water_potability.csv     # Raw dataset (from Kaggle)
└── outputs/
    ├── class_imbalance.gif      # Animated bar chart
    ├── distribution_shift.gif   # Animated KDE plot
    └── visualizations/          # Static plots

---

## 🔧 Troubleshooting

| Issue | Solution |
|-------|----------|
| `ModuleNotFoundError: No module named 'pandas'` | Run `pip install pandas` |
| `No module named 'sklearn'` | Run `pip install scikit-learn` |
| Plots not showing in notebook | Ensure Jupyter is installed: `pip install jupyter` |
| Memory error on large animations | Reduce figure size or reduce number of frames |
| Missing CSV file | Ensure data file is in correct path or download from Kaggle |

---

## 📈 Performance Tips

1. **Run cells sequentially** - Don't skip cells, dependencies exist
2. **Use kernel restart** - If errors occur: `Kernel` → `Restart & Clear Output`
3. **Reduce animation frames** - For faster rendering on slower machines
4. **Save visualizations** - Use `plt.savefig()` to export high-quality images

---

## 📚 References

- **Pandas Documentation:** https://pandas.pydata.org/docs/
- **Matplotlib Guide:** https://matplotlib.org/stable/contents.html
- **Seaborn Tutorial:** https://seaborn.pydata.org/tutorial.html
- **Scikit-learn:** https://scikit-learn.org/stable/documentation.html
- **IQR Outlier Detection:** https://en.wikipedia.org/wiki/Interquartile_range

---

## 📝 Data Source

**Dataset:** Water Quality & Potability  
**Platform:** Kaggle  
**URL:** https://www.kaggle.com/datasets/uom190346a/water-quality-and-potability  
**License:** Check Kaggle dataset page for license information

---

## ⚖️ License

This notebook is provided as-is for educational and research purposes. Please cite the original Kaggle dataset in your work.

---

## 🤝 Contributing

Found a bug or want to improve the analysis? 
- Add statistical tests (t-tests, chi-square)
- Implement feature engineering techniques
- Add predictive models
- Improve visualizations

Feel free to fork, modify, and submit improvements!

---

## ✉️ Contact & Support

- **Questions?** Check the notebook comments - they explain each section
- **Issues?** Verify all dependencies are installed correctly
- **Suggestions?** This notebook can be extended with more advanced analyses

---

## 🎓 Learning Outcomes

After running this notebook, you'll understand:

✅ How to perform exploratory data analysis (EDA)  
✅ Statistical methods for water quality analysis  
✅ Data visualization best practices  
✅ Handling missing values and outliers  
✅ Identifying class imbalance in datasets  
✅ How to prepare data for machine learning  
✅ Distribution comparison techniques  
✅ Working with animated visualizations  

---

*Last Updated: May 22, 2026*  
*Notebook Version: 1.0*  
*Status: Ready for analysis*
