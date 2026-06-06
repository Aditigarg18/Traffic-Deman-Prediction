# Traffic Demand Prediction

## Project Overview
Traffic congestion is a significant challenge in urban areas globally, disrupting transportation flows and hindering economic growth. This project focuses on leveraging AI-powered solutions to understand travel patterns and predict traffic demand. 

As outlined in `Screenshot 2026-06-05 200752.png`, the core task is to design a system capable of providing valuable insights into passenger travel patterns, booking behaviors, and trip cancellations to accurately predict demand in the travel industry.

---

## Dataset Description
The dataset consists of structured information captured across multiple urban locations and timestamps. The data files are split as follows:
*   **`train.csv`**: Contains 77,299 rows and 11 columns (includes the target variable).
*   **`test.csv`**: Contains 41,778 rows and 10 columns.
*   **`sample_submission.csv`**: An example template demonstrating the expected format.

### Variable Descriptions
The features provided in the dataset (referenced from `Screenshot 2026-06-05 200810.png`) are:

| Column Name | Description |
| :--- | :--- |
| **Index** | Unique identifier for each data point. |
| **geohash** | Geographic information regarding a specific location. |
| **day** | The day when the information was recorded. |
| **timestamp** | The exact timestamp of the record inserted into the system. |
| **RoadType** | The type of road in the nearby location. |
| **NumberofLanes** | The number of roads/lanes present in the location. |
| **LargeVehicles** | Indicator of whether large vehicles are permitted on the specific roads/lanes. |
| **Landmarks** | Indicator of whether there are landmarks near the location. |
| **Temperature** | Ambient temperature of the place. |
| **Weather** | Weather condition of the place. |
| **demand** | **[Target Variable]** The traffic demand at the given timestamp. |

---

## Evaluation Metric

The performance of the predictive model is evaluated based on the $R^2$ (Coefficient of Determination) score, scaled to a maximum score of 100. If the $R^2$ score is negative, the final score defaults to 0.

The scoring formula is defined as:

Score = max(0, 100 * r2_score(actual, predicted))

* **Maximum Score:** 100 (Perfect prediction)
* **Minimum Score:** 0 (Baseline performance or worse)$

---

## Submission Guidelines
To ensure your predictions are successfully evaluated, strictly adhere to the guidelines from `Screenshot 2026-06-05 200810.png` and `Screenshot 2026-06-05 200822.png`:

*   **Format**: The final submission must be a `.csv` file.
*   **Dimensions**: The submission file must exactly match the shape `41778 x 2`.
*   **Structure**: 
    *   The index column must be **Index** (matching the test file values exactly).
    *   The target prediction column must be **demand**.
    *   Column names and configurations must match the format provided in `sample_submission.csv`.

---

## Instructions for Execution
Follow these operational steps to complete and submit the project (`Screenshot 2026-06-05 200822.png`):

1.  **Download Dataset**: Obtain the dataset via the platform's platform interface.
2.  **Local Development**: Build, train, and validate your model within your local development environment.
3.  **Generate Predictions**: Export your model's test predictions to a `.csv` file ensuring it matches the submission guidelines.
4.  **Upload Prediction File**: Upload your generated `.csv` file under the **Upload File** section.
5.  **Upload Source Code**: Upload your notebook (`.ipynb`) and any auxiliary presentation materials under the **Upload Source Code** section.
6.  **Finalize**: Document any notes or specific approaches in the **Your Answer** text section, and click **Submit**.
