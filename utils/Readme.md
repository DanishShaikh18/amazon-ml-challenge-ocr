# 🧠 Amazon ML Challenge – Product Info Extractor

A computer vision-based solution developed for the **Amazon ML Challenge** that extracts structured product information (like name, size, quantity, weight, dimensions) from product images using OCR and image processing.

This project demonstrates how to extract high-confidence text from noisy or complex packaging images, similar to those used in e-commerce, and convert that into useful metadata.

---

## 📌 Challenge Context

In the **Amazon ML Challenge**, one of the real-world problems was to **extract key product details** directly from images of product packaging.  
These details often include:

- Product Name  
- Quantity (e.g., "1kg", "500ml")  
- Nutritional Info or Dimensions  
- Brand and Category Keywords

---

## 🧠 My Solution

Using a combination of **EasyOCR**, **PyTesseract**, and **OpenCV**, I created an OCR pipeline that:

- Preprocesses and resizes images for clean recognition  
- Extracts text using EasyOCR  
- Highlights the text on the image using bounding boxes  
- Applies regex and fuzzy logic (e.g., `difflib`) to classify product attributes  
- Handles multiple formats (vertical/horizontal packaging)

---

## 🛠 Technologies & Libraries Used

| Tool            | Purpose                              |
|-----------------|--------------------------------------|
| `EasyOCR`       | OCR engine for high-accuracy text    |
| `PyTesseract`   | Alternative OCR engine               |
| `OpenCV`        | Image pre-processing & annotation    |
| `PIL`           | Image loading & format conversion    |
| `Regex`         | Pattern matching in extracted text   |
| `difflib`       | Fuzzy string matching                |
| `Requests`      | Handling image URLs (Amazon S3 etc.) |
| `Matplotlib`    | Visualizing OCR output               |

---

## 📸 Sample Outputs

![Sample Image](./sample_images/image1.png)

![OCR Output](./sample_images/image2.png)

![OCR Output](./sample_images/image3.png)

> You can find more samples in the `/sample_images/` folder.

---

## 🧪 Code Snapshot

```python
reader = easyocr.Reader(['en'], gpu=False)
results = reader.readtext(np.array(img))
for (bbox, text, prob) in results:
    print(f"Detected: {text} with {prob:.2f} confidence")

pip install -r requirements.txt
Or run through Jupyter Notebook (notebooks/Text_Extraction.ipynb)

```

📌 Key Features
✅ Extracts clean text from product images
✅ Highlights detected text with bounding boxes
✅ Classifies extracted terms using regex & string matching
✅ Handles remote URLs or local images
✅ Well-commented, production-level Python code

📌 Future Enhancements
🔍 Add Named Entity Recognition (NER) to tag info like brand, size, category
📊 Store results into PostgreSQL or CSV
🧠 Add feedback loop for improving accuracy using annotation

👨‍💻 Author
Danish Shaikh
🎓 BCA Student | GDG Operations Head | Data & AI Enthusiast
📧 danish89761@gmail.com
🔗 LinkedIn

`ocr` `easyocr` `pytesseract` `computer-vision` `amazon-ml-challenge`
`product-image` `image-processing` `python` `regex` `fuzzy-matching` `machine-learning`
