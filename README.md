# Extracting-the-Grand-Total-amount-from-a-receipt

### Problem Statement
* Using OCR to automate extracting of total amounts for receipts.
* This would help in book-keeping and save man hours in manually verifying and noting the receipt values.
* This leaves no room for human error. The only constraint here is that pictures need to be of a higher resolution.

## Current Pitfalls and future scope
* The Tesseract OCR API fails to distinguish between 6 and &. This leads to many entries such as '$1.00' to be misinterpreted as '61.00'.
* A CNN model may prove useful in correcting the final values. The idea is that it will capture the neighbouring data points and detect outliers ($1 as 61).
