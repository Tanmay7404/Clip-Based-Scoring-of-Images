# Improving Text-to-Image Coherence with CLIP-based Re-ranking

### Project Description

This project addresses the common failure of text-to-image diffusion models on complex prompts involving multiple objects, attributes, and spatial relationships. We propose and evaluate an automated pipeline that generates multiple candidate images and uses the CLIP model to score and select the one with the highest semantic coherence to the original prompt.

### Proposed Pipeline Diagram



<img width="1500" height="611" alt="image" src="https://github.com/user-attachments/assets/dd523cad-3ce2-40e0-b72a-3c7b207db40c" />


---

## Instructions to Run the Code

This guide will walk you through setting up the environment and running the image generation and evaluation notebook.

### 1. Prerequisites

*   Python 3.8+
*   `pip` and `venv` for package management
*   Git for cloning the repository
*   **Hardware:** A CUDA-enabled NVIDIA GPU with at least 8GB of VRAM is **highly recommended** for reasonable performance. The script will fall back to the CPU if a GPU is not available, but generation will be extremely slow.

### 2. Setup and Installation

** Clone the Repository**
Open your terminal and clone this repository to your local machine:
```bash
git clone <your-repository-url>
cd <repository-directory-name>
```

### 3. Running the Notebook

**a. Launch Jupyter Notebook**
Ensure your virtual environment is activated, then start the Jupyter server:
```bash
jupyter notebook
```
This will open a new tab in your web browser.

**b. Open and Run the Main Notebook**
1.  In the browser tab, navigate to and open the python notebook (`minor-final-tanmay-tanvi.ipynb`).
2.  To run the entire pipeline, execute the cells in order from top to bottom. You can do this by clicking `Cell > Run All` in the menu bar.
3.  The first time you run the code, the script will download the Stable Diffusion XL and CLIP models from Hugging Face. This may take several minutes and requires a stable internet connection.

**c. Experiment with Your Own Prompts**
To generate your own images, find the cell containing the `prompt` variable and change its value. For example:

```python
# Find this cell and modify the prompt
prompt = "A high-quality photo of a red apple sitting to the left of a blue banana on a wooden table."

best_image_adaptive, candidates_adaptive, scores_adaptive = generate_adaptively(prompt, pipe)

print("\n--- FINAL SELECTED IMAGE (ADAPTIVE METHOD) ---")
display(best_image_adaptive)

# Change it to your own idea:
prompt = "A photorealistic masterpiece of a red fox in a spacesuit, looking at the Earth from the moon."
```
Also you can change the patience level, max number of candidates, and other paramteters of the function. After changing the prompt, re-run that cell and all subsequent cells to see your new results and analysis.
