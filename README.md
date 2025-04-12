CT Scan Python Slice Extract Code

Overview
This repository provides Python scripts for processing CT scan data stored in DICOM format. It includes utilities for extracting slices from CT scans and saving them as PNG images for further analysis or visualization.

Features
- Extract pixel data from DICOM files.
- Save CT scan slices as PNG images.
- Organize extracted slices into a designated output folder.
- Easy integration with Google Colab and Google Drive.

Requirements
- Python 3.x
- Libraries:- pydicom
- imageio
- os
- shutil

Installation
Clone the repository:
git clone https://github.com/1ejheinz/CT-Scan-Python-Slice-Extract-Code.git

Install the required Python libraries:
pip install pydicom imageio


Usage
Usage
- Extract DICOM files from a ZIP archive:from zipfile import ZipFile
with ZipFile("DICOM.zip", "r") as zip_ref:
    zip_ref.extractall("dicom_data")

- Define input and output folders:dicom_folder = "dicom_data/DICOM"
output_folder = "extracted_slices"
os.makedirs(output_folder, exist_ok=True)

- Extract slices and save them as PNG:for idx in key_indices:
    ds = pydicom.dcmread(dicom_files[idx])
    image = ds.pixel_array
    filename = os.path.join(output_folder, f"slice_{idx+1}.png")
    imageio.imwrite(filename, image)
    print(f"Saved: {filename}")

Contributing
Feel free to fork this repository and submit pull requests for improvements or new features.




