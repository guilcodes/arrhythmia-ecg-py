# 🫀 Classifying Arrhythmia using Electrocardiogram Results as Matrices

Arrhythmia refers to an irregular heartbeat, and is a fairly common condition that can be detected via ECG/EKG. However, several factors ranging from human error or faulty equipment to asymptomatic presentation can result in arrhythmias being overlooked. Given the growing prevalence in the use of software to aid in diagnostic techniques, it is possible that these aforementioned sources of error can be offset by incorporating them in the process. This paper employs various linear algebra principles to simplify ECG information for faster, more accurate analyses using publicly available datasets. The graph representing the derivative of ECG voltage vs. time was produced, although further analysis was limited by absence of P and T waves and the lack of a continuous waveform. Nevertheless, the graph produced can be used to identify sudden changes in heart rate, and the study as a whole provides strong evidence for this method’s potential and for the benefit of further research.

# Methodology & Data Processing

* **Dataset Overview:**
    * **Source:** [ECG Heartbeat Categorization Dataset](https://www.kaggle.com/datasets/shayanfazeli/heartbeat) by Shayan Fazeli (Kaggle).
    * **Origin:** Derived from the **MIT-BIH Arrhythmia Database**.
    * **Size:** 109,446 ECG heartbeat samples featuring labeled signal segments and heartbeat annotations.

* **Data Preprocessing:**
    * **Format Conversion:** Utilized **Python** to transform the raw `.csv` files into structured Excel (`.xlsx`) format.
    * **Tech Stack:** Leveraged `pandas` for data manipulation and `numpy` for efficient numerical operations.
    * **Feature Extraction:** Extracted **Time (s)** and **ECG signal (mV)** values for longitudinal analysis.

* **Mathematical Analysis:**
    * **First Derivative Calculation:** Computed the rate of voltage change to identify rapid waveform transitions using the slope formula:
    $$\text{First Derivative} = \frac{Y_3 - Y_2}{X_3 - X_2}$$
    > Where:
    > * **$Y$**: ECG signal amplitude (mV)
    > * **$X$**: Time (s)

* **QRS Complex Detection:**
    * **Slope Analysis:** The derivative computes the slope between consecutive points, allowing for the detection of the **QRS complex**—the most prominent feature of an ECG signal.
    * **HRV & R-Peak Localization:** By applying a squaring function to the differentiated signal (as established in Pan-Tompkins foundational research), we emphasize steep voltage transitions.
    * **Efficiency:** This derivative-based approach is computationally optimized, making it ideal for the real-time classification of large-scale arrhythmia datasets.

