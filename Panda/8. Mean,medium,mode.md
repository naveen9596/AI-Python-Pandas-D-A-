### Descriptive statistics provide a summary of the central tendency, dispersion, and shape of a dataset’s distribution. Here is an example using a simple dataset to calculate the mean, median, mode, variance, and standard deviation:

### Example Dataset
Let's consider the following dataset:
\[ 4, 8, 6, 5, 3, 8, 7, 9, 5, 8 \]

### Calculations

1. **Mean (Average)**
   \[
   \text{Mean} = \frac{\sum_{i=1}^{n} x_i}{n}
   \]
   Where \( x_i \) are the data points and \( n \) is the number of data points.

   \[
   \text{Mean} = \frac{4 + 8 + 6 + 5 + 3 + 8 + 7 + 9 + 5 + 8}{10} = \frac{63}{10} = 6.3
   \]

2. **Median**
   - Sort the data: \( 3, 4, 5, 5, 6, 7, 8, 8, 8, 9 \)
   - For an even number of observations, the median is the average of the two middle numbers.

   \[
   \text{Median} = \frac{6 + 7}{2} = 6.5
   \]

3. **Mode**
   - The mode is the value that appears most frequently in the dataset.
   - In this dataset, the number 8 appears three times.

   \[
   \text{Mode} = 8
   \]

4. **Variance**
   - Variance measures the dispersion of the dataset.

   \[
   \text{Variance} (s^2) = \frac{\sum_{i=1}^{n} (x_i - \bar{x})^2}{n-1}
   \]
   Where \( \bar{x} \) is the mean of the data.

   First, calculate each deviation from the mean, square it, and then average those squared deviations.

   \[
   \begin{align*}
   (4 - 6.3)^2 & = 5.29 \\
   (8 - 6.3)^2 & = 2.89 \\
   (6 - 6.3)^2 & = 0.09 \\
   (5 - 6.3)^2 & = 1.69 \\
   (3 - 6.3)^2 & = 10.89 \\
   (8 - 6.3)^2 & = 2.89 \\
   (7 - 6.3)^2 & = 0.49 \\
   (9 - 6.3)^2 & = 7.29 \\
   (5 - 6.3)^2 & = 1.69 \\
   (8 - 6.3)^2 & = 2.89 \\
   \end{align*}
   \]

   Sum of squared deviations: 
   \[
   5.29 + 2.89 + 0.09 + 1.69 + 10.89 + 2.89 + 0.49 + 7.29 + 1.69 + 2.89 = 36.1
   \]

   Variance:
   \[
   s^2 = \frac{36.1}{9} = 4.01
   \]

5. **Standard Deviation**
   - Standard deviation is the square root of the variance.

   \[
   \text{Standard Deviation} (s) = \sqrt{s^2} = \sqrt{4.01} \approx 2.00
   \]

### Summary of Descriptive Statistics

- **Mean:** 6.3
- **Median:** 6.5
- **Mode:** 8
- **Variance:** 4.01
- **Standard Deviation:** 2.00

These calculations provide a concise summary of the central tendency and variability of the dataset.
