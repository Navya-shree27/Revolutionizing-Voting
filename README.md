# Revolutionizing-Voting
import io
import os
from google.cloud import vision

# Set up Google Vision API
os.environ["GOOGLE_APPLICATION_CREDENTIALS"] = "your_service_account.json"
client = vision.ImageAnnotatorClient()

def extract_text_from_image(image_path):
    with io.open(image_path, 'rb') as image_file:
        content = image_file.read()
    
    image = vision.Image(content=content)
    response = client.text_detection(image=image)
    texts = response.text_annotations

    if texts:
        return texts[0].description  # Extracted text
    return "No text found"

# Example Usage
text = extract_text_from_image("voter_id_sample.jpg")
print("Extracted Text:", text)
