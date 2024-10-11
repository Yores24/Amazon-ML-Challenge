# Project Name: Entity Value Extraction from Product Images

## Overview
This project was developed for a hackathon with the goal of creating a machine learning model that extracts **entity values** (e.g., weight, volume, voltage) from **product images**. The ability to automatically extract such information is crucial in industries like **healthcare**, **e-commerce**, and **content moderation**, where precise product details are essential but often missing from text-based descriptions. As digital marketplaces grow, product images become a critical source of information, offering details like **weight**, **volume**, **dimensions**, and more.

## Project Structure
This GitHub repository contains all the necessary resources, including datasets, preprocessing scripts, and Jupyter notebooks that document the step-by-step approach to solving the problem.

### Key Files:
- **`src/utils.py`**: Contains the function `download_images()` for downloading product images using the `image_link` provided in the dataset.
- **`src/test.ipynb`**: A sample notebook demonstrating how to use `download_images()` to fetch images for training and testing.
- **`preprocessed_dataset.csv`**: The preprocessed dataset used to train the model.
- **`output.ipynb`**: Contains the logs and step-by-step execution for preprocessing, training, and evaluating the model.
- **`prediction.ipynb`**: Includes the logs and process followed to generate predictions on the test set and evaluate model performance.

## Dataset Description
The dataset consists of the following columns:

- **index**: A unique identifier (ID) for each data sample.
- **image_link**: A public URL where the product image can be downloaded.
  - Example: `https://m.media-amazon.com/images/I/71XfHPR36-L.jpg`
- **group_id**: A category code that groups products into broader categories.
- **entity_name**: The name of the product entity (e.g., "item_weight").
- **entity_value**: The corresponding value of the product entity (e.g., "34 gram"). **(Note**: In `test.csv`, this column is missing, as it is the target variable to be predicted.)

### Sample Dataset
| index | image_link                                                | group_id | entity_name  | entity_value |
|-------|------------------------------------------------------------|----------|--------------|--------------|
| 0     | https://m.media-amazon.com/images/I/71XfHPR36-L.jpg        | 101      | item_weight  | 34 gram      |
| 1     | https://m.media-amazon.com/images/I/81eNLP4KdXL._SL1500_.jpg| 102      | item_volume  | 500 ml       |

## Problem Statement
The main task is to develop a machine learning model that can predict the **entity value** (e.g., "34 gram", "500 ml") directly from product images. This functionality is key in domains where textual descriptions are incomplete or missing, and images hold valuable product information.

## Steps Followed
1. **Image Downloading**: Used the `download_images()` function from `src/utils.py` to download product images using the URLs in the dataset.
2. **Preprocessing**: Applied preprocessing steps to clean and prepare the dataset for model training. This included resizing and normalizing images, and encoding the `group_id` and `entity_name`.
3. **Model Development**: Developed a machine learning model that utilizes computer vision techniques to extract entity values from product images. Logs detailing the model selection, architecture, and training process can be found in the `output.ipynb` notebook.
4. **Evaluation**: After training the model, predictions were generated on the test set (found in `prediction.ipynb`). Evaluation metrics and logs are included to demonstrate model performance.
   
## How to Run
1. Clone the repository:
   ```bash
   git clone https://github.com/your-repo/entity-extraction-from-images.git
   cd entity-extraction-from-images
   ```

2. Install the required dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Download the product images:
   - Use the provided `src/test.ipynb` notebook to download images using the `download_images()` function.

4. Run the preprocessing and model training:
   - Follow the steps outlined in `output.ipynb` to preprocess the dataset and train the model.

5. Make predictions:
   - Use `prediction.ipynb` to generate predictions on the test dataset.

## Conclusion
This project demonstrates the development of a machine learning model capable of extracting key entity values from product images. The solution is versatile and can be applied in various fields, providing a critical tool for digital stores and marketplaces that require precise and automatic information extraction from visual data.

---

Feel free to explore the notebooks and adjust the model or preprocessing steps as needed.