**Product Category Prediction App**

**A simple Streamlit application that predicts a product category using text inputs such as title, description, and tags.**

**1. Data Cleaning**

  * The dataset contains product categories.
  * Each category text is cleaned by:
      Converting to lowercase
      Removing special characters using regex
      Stripping extra spaces
      This helps the model understand the categories clearly.

**2. User Query Cleaning**

  * Whatever the user types (title, description, tags) is also cleaned using the same cleaning function.
  * Cleaned text is combined into one query string.
  * This ensures the model compares clean text to clean categories.

**3. Model Preparation**

  * Hugging Face model used: all-mpnet-base-v2

  * Steps:
      Convert every category text into an embedding vector.
      Store all embeddings.
      When a user enters text, convert that input into an embedding as well.

**4. Prediction (Cosine Similarity)**

    * Cosine similarity is used to find how close the user input is to each category.
    * The category with the highest similarity score is selected.
    * The score itself is shown as the confidence.

**5. How to Run the App**

    * Step 1: Install dependencies`
       pip install -r requirements.txt
       
    * Step 2: Run the Streamlit app   
        streamlit run app.py    
