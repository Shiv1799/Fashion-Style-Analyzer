# 🧠👗 Fashion Style Analyzer

A vision-LLM powered fashion analysis tool that takes a user-uploaded outfit image, finds visually similar items from an embedding database, and generates a clean, retailer-friendly fashion description using multimodal AI.

<p align="center"> <img src="https://raw.githubusercontent.com/Shiv1799/Fashion-Style-Analyzer/main/fashion%20analyser%202.png" width="600"> </p>
<p align="center"> <img src="https://raw.githubusercontent.com/Shiv1799/Fashion-Style-Analyzer/main/fashion%20analyser.png" width="600"> </p>

# 📌 Overview

Fashion Style Analyzer is an end-to-end pipeline combining:
Computer Vision (ResNet50) – extract image embeddings
Similarity Search – match uploaded images to a dataset of embedding vectors
Utility Logic – aggregate all fashion items for the matched look
Vision-LLM (Llama Vision / Watsonx) – generate a professional fashion analysis
Gradio UI – simple and interactive web interface
The result is a clean, human-readable “fashion review” similar to professional styling platforms.

# 🚀 Project Flow (How It Works)
# 1. User Uploads Image
Through the Gradio interface, the user uploads a fashion image.
# 2. Image Encoding
The image is:
preprocessed
converted to base64 (for LLM)passed through ResNet50 to generate a feature embedding

# 3. Similarity Search
The system compares the embedding with a database (swift-style-embeddings.pkl) to find the closest-matching outfit using cosine similarity.

# 4. Retrieve All Items
Once the closest outfit is found, all items belonging to that outfit (blazer, shoes, skirt, accessories, etc.) are collected from the dataset.

# 5. LLM Fashion Analysis
A tailored prompt is sent to the Llama Vision model (via Watsonx API):
The base64 image
The set of found item details
Instructions to generate a polished, structured analysis

# 6. Output Post-Processing
Helper functions clean up:

formatting sections like ITEM DETAILS / SIMILAR ITEMS markdown compatibility

# 7. UI Display

The final Markdown description is rendered in Gradio.
