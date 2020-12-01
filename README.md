# Extracting-the-Grand-Total-amount-from-a-receipt

### Problem Statement
* Using OCR to automate extracting of total amounts for receipts.
* This would help in book-keeping and save man hours in manually verifying and noting the receipt values.
* This leaves no room for human error. BUt here are some limitations the current solution has.
* The pictures need to be high resolution, such that the smallest white line separating text should be atleast 4px wide.
* Some fonts work better than others.

### Solution Overview
* Adaptive gaussian thresholding was used to preprocess images into a more usable format for the API.
* Images were aligned using a CNN to minimize errors while passing the images for OCR.
* Tesseract OCR API parameters were tweaked to achieve an R<sup>2</sup> score of 0.91. 

## Current Pitfalls and future scope
* The Tesseract OCR API fails to distinguish between 6 and &. This leads to many entries such as '$1.00' to be misinterpreted as '61.00'.
* A CNN model may prove useful in correcting the final values. The idea is that it will capture the neighbouring data points and detect outliers ($1 as 61).
