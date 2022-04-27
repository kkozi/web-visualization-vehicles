# Project: Visual Comparison of Vehicle Models

This set of visualizations was built to demonstrate simple techniques useful in visual analytics. The plots display relationships between pairs of attributes from a given dataset of vehicle models.

## Visualizing Similarity using Distance Measures

The scatterplot below visualizes the relationship between the vehicle attributes of car weight and horsepower, focusing on a subset of vehicles that are similar to a given model with regard to these features. The bar chart below plots the attribute of acceleration for each of the vechicles in the subset highlighted in the scatterplot, sorted in order of similarity to the given model.

In the interactive web version of this visualization, users can hover over any point in the scatter plot to reveal the corresponding vehicle's model name. Additionally, a legend is included to help the user make sense of the color scheme.

![Scatterplot + Bar Chart: Vehicle Weight vs. Horsepower](https://user-images.githubusercontent.com/59906090/165416688-e08a95e3-d7d9-47fb-81dc-dc694d5034cc.PNG)

For these visualizations, vehicle similarity scores were obtained by calculating the Euclidean distances from the selected (and normalized) attributes of the given model to that of every other model in the dataset. In this example, the nearest 15 models are selected for further processing.

These web visualizations were built using [D3.js](https://d3js.org/). In the scatterplot, partial opacity allows the user to notice occlusion of the circular marks used to represent the vehicles in the dataset.

The identity channel of color hue is used to distinguish the given model (represented by an opaque red), the subset of similar models (represented by a semi-transparent blue), and the rest of the data (represented by a semi-transparent gray). The red and blue colors were chosen to be visually distinct from each other and to stand out among the marks with a light gray color—a hue that was chosen to form a sort of "data background" which stays out of the user’s immediate focus.

The magnitude channel of color saturation is used in the bar chart to emphasize the relative strengths of the similar vehicles' computed similarity scores. The saturation factor is calculated as a function of the computed distance measures; here, the exact color values are scaled to make the color gradations more visible to the user than a direct mapping.

## Visualizing Similarity using Clustering

The visualization below plots the relationship between the vehicle attributes of engine displacement and MPG. There are five distinct clusters grouping vehicle models that are similar with regard to these features.

In the interactive web version of this visualization, users can hover over any point in the scatter plot to reveal more detailed information about its corresponding vehicle (i.e., its full set of attributes).

![Scatterplot: Engine Displacement vs. MPG](https://user-images.githubusercontent.com/59906090/165417091-61c7cbbc-d6b6-4fd0-a18d-0a72e9dd6c86.png)

For this visualization, clustering was performed in Python using a Jupyter Notebook. Clusters are formed using the k-means clustering algorithm from the [scikit-learn](https://scikit-learn.org/) library. Although the k-means algorithm produces fairly reasonable results for these visualizations, it poses  several limitations. For example, the number of clusters must be chosen before the clustering process is performed. Furthermore, outliers can be difficult to represent and can negatively affect the results of the clustering process.

This web visualization was built using [D3.js](https://d3js.org/). Clusters are visually differentiated by the identity channel of color hue. Partial opacity allows the user to notice occlusion of the circular marks used to represent the vehicles in the dataset.

## Code

Code available upon request.

## References

Munzner, T., 2014. Visualization analysis and design. CRC press.
