## 🎨 ArtExplorer: Your Personal AI Museum Docent

A Submission for the BigQuery AI Hackathon

### 1. The Challenge: Overcoming "Gallery Fatigue"

Museums house humanity's greatest treasures, yet visitors often experience "**gallery fatigue**"—a a feeling of being overwhelmed by vast collections. Traditional **keyword searches** fall short when trying to find art that matches a feeling or a mood, like "a quiet, lonely night." Our project solves this problem by transforming art discovery from a simple search into a **personalized, guided conversation.**

---

### 2. The Solution: A Conversation with Art

**ArtExplorer** is a fully interactive prototype that allows users to:

* **Search by Meaning, Not Just Keywords:** Describe a feeling, a mood, or an abstract concept in natural language.
* **Discover Relevant Art:** Using the power of BigQuery's `VECTOR_SEARCH`, the application finds artworks that are semantically similar to the user's query.
* **Receive a Personalized Story:** Once an artwork is selected, our "**AI Docent**," powered by a **Gemini model in BigQuery**, generates a unique and engaging narrative, explaining the piece in the context of the user's original search.

<img width="2426" height="1147" alt="capture_motherly love" src="https://github.com/user-attachments/assets/0bb06f42-a149-4bf5-bc0c-927614c1e458" />

*Users can search for art using feelings and discover relevant pieces with similarity scores.*

<img width="2437" height="1107" alt="2_AI_Docent" src="https://github.com/user-attachments/assets/3d226d17-0cdc-4c4d-89c2-a1b6fbf9654f" />

*The AI Docent provides a unique and engaging narrative for the selected artwork, tailored to the user's initial query.*

---

### 3. Repository Structure

This repository contains all the necessary components for the ArtExplorer project.

* `ArtExplorer_Data_Pipeline.ipynb`: The **backend notebook** responsible for the one-time setup. It handles data ingestion, enrichment, AI model creation in BigQuery, and feature engineering (embedding generation).
* `ArtExplorer_AI_Docent_(Application).ipynb`: The **main, user-facing notebook**. This file runs the interactive application that allows users to search for art and receive AI-generated stories.
* `survey.txt`: The user survey file submitted as part of the hackathon requirements for bonus points.

---

### 4. How to Reproduce the Project

To run this project from scratch, please follow these steps:

#### GCP Prerequisites:

* Ensure you have a Google Cloud project with billing enabled.
* Enable the **BigQuery API**, **Cloud Storage API**, and **Vertex AI API**.
* Create a Service Account with **BigQuery User**, **Storage Admin**, and **Vertex AI User** roles, and download its JSON key.
* In BigQuery, create a Connection for Vertex AI in the `us-central1` region named `vertex_ai_connection_us`.

#### Kaggle Setup:

* Create a Kaggle Secret named `GCP_CREDENTIALS` and paste the contents of your Service Account JSON key into it.

#### Run the Data Pipeline:

1.  Open the `ArtExplorer_Data_Pipeline.ipynb` notebook in Kaggle.
2.  Attach the `GCP_CREDENTIALS` secret when prompted.
3.  Run all cells (`Run` -> `Run All`) once. This will prepare all the necessary data and models in your BigQuery project.

#### Launch the Application:

1.  Open the `ArtExplorer_AI_Docent_(Application).ipynb` notebook in Kaggle.
2.  Attach the `GCP_CREDENTIALS` secret when prompted.
3.  Run all cells (`Run` -> `Run All`). The interactive UI will appear at the bottom.

---

### 5. Project Links

* Kaggle Writeup & Submission: `https://www.kaggle.com/competitions/bigquery-ai-hackathon/writeups/artexplorer-your-personal-ai-museum-docent`
* Live Demo Video: `https://youtu.be/peg343OrvPk`
