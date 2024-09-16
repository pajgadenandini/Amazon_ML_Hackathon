# Amazon ML Hackathon: Feature Extraction from Images

## Problem Statement

In this hackathon, the challenge is to develop a machine learning model that extracts entity values from product images. This capability is crucial in various domains like healthcare, e-commerce, and content moderation, where accurate product information is essential. As digital marketplaces expand, many products lack comprehensive textual descriptions. Thus, extracting key details directly from images becomes critical. These details may include weight, volume, voltage, wattage, dimensions, and more.

## Data Description

The dataset consists of the following columns:

- **index**: A unique identifier for each data sample.
- **image_link**: A public URL where the product image can be downloaded. Example: `https://m.media-amazon.com/images/I/71XfHPR36-L.jpg`. Use the `download_images` function from `src/utils.py` to fetch images. Refer to the sample code in `src/test.ipynb`.
- **group_id**: A category code representing the product's category.
- **entity_name**: The name of the product entity, such as “item_weight”.
- **entity_value**: The value of the product entity, such as “34 gram”.

> **Note:** The `entity_value` column is absent in `test.csv` as it represents the target variable.

## Output Format

The output should be a CSV file with the following two columns:

- **index**: The unique identifier of the data sample (should match the index in `test.csv`).
- **prediction**: A string formatted as “x unit”, where `x` is a float number and `unit` is one of the allowed units. Example: “2 gram”, “12.5 centimetre”, “2.56 ounce”. Invalid cases include: “2 gms”, “60 ounce/1.7 kilogram”, “2.2e2 kilogram”. If no value is found in an image, return an empty string.

## File Descriptions

**Source Files:**

- `src/sanity.py`: A script to check if the final output file adheres to formatting rules.
- `src/utils.py`: Contains helper functions for downloading images from the provided URLs.
- `src/constants.py`: Lists allowed units for each entity type.
- `sample_code.py`: A sample script demonstrating how to generate an output file in the required format. Usage is optional.

**Dataset Files:**

- `dataset/train.csv`: Training data with labels (`entity_value`).
- `dataset/test.csv`: Test data without labels. Use this to generate predictions and format the output file accordingly.
- `dataset/sample_test.csv`: A sample test input file.
- `dataset/sample_test_out.csv`: Sample output file for `sample_test.csv`. Ensure your predictions are formatted identically.

## Constraints

- Ensure your output file matches the format of the sample output file and passes the sanity checker. You will receive a message like “Parsing successful for file: ...csv” if the output file is correctly formatted.
- Outputs must be in the units specified in `constants.py` and the Appendix. Predictions in other units will be considered invalid.

## Implementation

In this repository, I have implemented a solution to the problem statement using a machine learning model. Key components include:

- **Data Processing**: Extraction of numeric values and preprocessing of image-related features.
- **Modeling**: Utilization of [insert ML algorithm used] for predicting entity values from images.
- **Evaluation**: Validation of the model performance using metrics such as RMSE.


