# Brain-Signal-Analysis-Topomaps
# EEG Data Analysis and Visualization

## Overview

This repository provides scripts and guidelines for analyzing a given EEG dataset featuring 64 channels, 640 time points, and 99 trials. The data spans from -1000 ms to approximately 1500 ms, with relevant time points documented in `EEG.times`. The analysis involves extracting epochs, computing ERPs, identifying peak times, plotting topographical maps, and optionally applying a Laplacian filter to enhance the spatial resolution.

## Steps

### 1. Epoch Extraction and ERP Computation

- Extract epochs from 0 to 800 ms.
- Compute the Event-Related Potentials (ERPs) at each electrode and average them over all trials.
- Select nine time points between 0 and 800 ms (e.g., in 100ms steps) to show topographical plots.
- Average the activity from 20 ms before until 20 ms after each time point to improve signal-to-noise ratio.
- Present a series of topographical plots at these time points in a single figure, indicating the center time point on each subplot.

### 2. Peak Time Identification and Topographical Plotting

- Loop through each electrode to find the peak time of the ERP between 100 and 800 ms.
- Store these peak times in a separate variable.
- Create a topographical plot illustrating the peak times in milliseconds.
- Include a color bar in the figure, ensuring the representation of times in milliseconds from time 0.
- Identify areas of the scalp showing the earliest and latest peak responses to the stimulus within this window.

> Note: Use ‘jet’ format for colormaps and maintain consistent color limits across topoplots.

### Advanced Analysis (Optional)

#### 3. Laplacian Filter Application and Comparison

- Apply a large Laplacian filter to the data obtained in step 1.
- Transfer the polar coordinates in `eloc64C2.txt` file into Cartesian coordinates.
- For each electrode of interest, retain only those electrodes that are in the radius [0.18, 0.28] and compute the weights.
- Obtain the Laplacian filtered signal and compare the results with step 1.
- Provide observations and comments on the differences noted and the effects of the Laplacian filter on spatial resolution.

## Conclusion

Following these steps will assist in analyzing the EEG dataset, visualizing the ERPs, and identifying areas of varied peak responses across the scalp. The application of a Laplacian filter can further enhance the spatial resolution of the findings, providing a more localized representation of brain activity.
