# mlkdocrelease2025
A script for scraping PDFs from government website, appending, and OCRing.

# MLK Assassination Records Processing & Analysis

A Python script using Jupyter Lab to **bulk download, merge, and OCR the recently released Martin Luther King Jr. assassination records from the National Archives.** This prepares the documents for powerful text analysis tools like Google's NotebookLM.

## Problem Solved

Manually downloading hundreds or thousands of individual PDF documents and then converting them into a searchable format can be incredibly time-consuming. This script automates that entire process, transforming scattered, potentially non-searchable PDFs into a single, cohesive, and fully OCR'd document ready for advanced research.

## Features

* **Automated Download:** Scrapes the National Archives website to automatically download the first 100 available PDF files related to the MLK assassination.
* **PDF Merging:** Combines all downloaded individual PDFs into a single, comprehensive document.
* **Optical Character Recognition (OCR):** Applies OCR to the merged PDF, creating a hidden text layer that makes the entire document searchable and its content extractable for text analysis.
* **NotebookLM Ready:** The final OCR'd PDF is perfectly formatted for upload into Google's NotebookLM, allowing for instant summarization, Q&A, and exploration of complex historical data.

## Getting Started

Follow these steps to set up and run the script on your local machine.

### Prerequisites

You need **Python 3.8+** and a few system-level tools:

1.  **Python Libraries:** Install the necessary Python packages using pip. It's recommended to do this in a virtual environment.
    ```bash
    pip install -r requirements.txt
    ```
    (Note: If running in Jupyter Lab and you prefer seeing a live progress bar, you might also want to install `ipywidgets`: `pip install ipywidgets` and then `jupyter nbextension enable --py widgetsnbextension` followed by `jupyter labextension install @jupyter-widgets/jupyterlab-manager` if in Jupyter Lab, then restart Jupyter Lab.)

2.  **Tesseract OCR Engine (System-Level):** `ocrmypdf` relies on Tesseract.
    * **Windows:** Download the installer from [Tesseract-OCR GitHub page](https://github.com/UB-Mannheim/tesseract/wiki) (choose the 64-bit version).
    * **macOS (Homebrew):** `brew install tesseract`
    * **Linux (Debian/Ubuntu):** `sudo apt install tesseract-ocr`

3.  **Ghostscript (System-Level):** Crucial for PDF processing (especially on Windows).
    * **Windows:** Download the latest 64-bit AGPL release from [Ghostscript's Official Website](https://www.ghostscript.com/download/gsdnld.html). **During installation, ensure it's added to your system's PATH, or manually add its `bin` directory (e.g., `C:\Program Files\gs\gs10.05.1\bin`) to your system's PATH environment variables.** Verify by opening a *new* command prompt and typing `gswin64c -v`.
    * **macOS (Homebrew):** `brew install ghostscript`
    * **Linux (Debian/Ubuntu):** `sudo apt install ghostscript`

### Usage

1.  **Clone the Repository:**
    ```bash
    git clone [https://github.com/darredo1/mlkdocrelease2025.git](https://github.com/darredo1/mlkdocrelease2025.git)
    cd mlkdocrelease2025
    ```
2.  **Open in Jupyter Lab:**
    ```bash
    jupyter lab
    ```
3.  **Run the Notebook:** Open the `merge_mlk_pdfs.ipynb` notebook.
    * **Option 1 (Run All):** Go to `Run` -> `Run All Cells`.
    * **Option 2 (Step-by-Step):** Run each cell sequentially. The notebook is structured to guide you through folder setup, web scraping, downloading, merging, and OCR.

### Output

Upon successful execution, the script will:

* Create a folder named `mlk_pdfs` in the same directory as your notebook.
* Download the first 100 unique PDF files from the National Archives into `mlk_pdfs`.
* Create `merged_mlk_records.pdf` (a single PDF containing all downloaded documents) inside `mlk_pdfs`.
* Create `searchable_mlk_records.pdf` (the OCR'd, searchable version of the merged file) inside `mlk_pdfs`.

### Integrating with NotebookLM

1.  Go to [NotebookLM](https://notebooklm.google.com/) and create a new Notebook.
2.  Click "Add Source" or "Upload".
3.  Upload the `mlk_pdfs/searchable_mlk_records.pdf` file.

You can now ask questions, summarize, and explore the content of thousands of pages of MLK assassination records effortlessly!

## Citation

If you find this script useful for your own work or if it inspires further projects, please consider citing this repository:

* **APA Style (adapted for software):**
    Darredo1. (2025). *MLK Assassination Records Processing & Analysis Script* (Version 1.0) \[Computer software]. GitHub. https://github.com/darredo1/mlkdocrelease2025

* **MLA Style (adapted for software):**
    Darredo1. *MLK Assassination Records Processing & Analysis Script*. Version 1.0, 2025, GitHub, https://github.com/darredo1/mlkdocrelease2025.

**Note on NotebookLM:** As NotebookLM environments are currently private, direct public linking is not possible. You can, however, describe its use in your methodology: "This research utilized Google's NotebookLM (alpha/beta version) for interactive analysis and summarization of the processed documents."

## Source Data

The original documents processed by this script are from the National Archives and Records Administration (NARA). Please cite the original source as:

* **APA Style:**
    National Archives and Records Administration. (n.d.). *Records Related to the Assassination of the Reverend Dr. Martin Luther King, Jr.* Retrieved from https://www.archives.gov/research/mlk

* **MLA Style:**
    National Archives and Records Administration. "Records Related to the Assassination of the Reverend Dr. Martin Luther King, Jr." *National Archives*, https://www.archives.gov/research/mlk. Accessed July 21, 2025.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---
