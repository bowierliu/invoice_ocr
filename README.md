# Invoice Table Extraction using OCR and OpenCV

This project demonstrates how to extract structured table data from invoice images using Tesseract OCR and OpenCV. The process involves preprocessing the image, detecting table regions using contours, and extracting text into a structured format.

## Steps Involved

### 1. Image Preprocessing
- **Grayscale Conversion**: The invoice image is converted to grayscale to reduce complexity.
- **Thresholding**: Adaptive thresholding is applied to binarize the image, making text and table lines more distinguishable.

### 2. Table Detectio
- **Contour Detection**: OpenCV is used to detect contours in the image. These contours help identify potential table regions by their size and shape.
- **Region of Interest (ROI)**: The largest contour resembling a table is extracted as the ROI for further processing.

### 3. OCR (Optical Character Recognition)
- **Text Extraction**: Tesseract OCR is applied to the table region to extract textual data.
- **Confidence Filtering**: Only text with a confidence score above a threshold is retained to improve accuracy.

### 4. Row and Column Alignment
- **Grouping by Rows**: Extracted text is grouped into rows using vertical positions (`top` coordinates).
- **Dynamic Parsing**: Multi-word entries, such as product names, are combined, and numerical columns are aligned dynamically.
- **Validation**: Only rows with valid data across all expected columns are included in the final output.

## Techniques and Tools Used
- **OpenCV**: For image preprocessing and contour detection.
- **Tesseract OCR**: For extracting textual data from images.
- **Python**: For scripting and integrating the workflow.

## Challenges Addressed
- Handling irregular table layouts with inconsistent spacing.
- Extracting multi-word entries and aligning them into structured columns.
- Filtering noisy data to improve the accuracy of text extraction.

## Applications
This approach can be used for:
- Automating data entry from invoices and receipts.
- Extracting structured data from scanned documents.
- Enhancing workflows in business automation and document processing.
