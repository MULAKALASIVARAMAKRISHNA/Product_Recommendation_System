This Python script implements a **collaborative filtering-based recommendation system** using K-Nearest Neighbors (KNN) on the **Amazon Product Review dataset**. The goal is to recommend products to users based on their past interactions.  

Step-by-Step Explanation:
1. Load and Preprocess Data:  
   - The dataset (`ratings_Beauty.csv`) is loaded into a Pandas DataFrame.  
   - The unnecessary `Timestamp` column is dropped.  
   - The `Rating` column is converted to numeric values, and invalid ratings are removed.  

2. Mapping Users and Products:
   - Users and products are mapped to numerical indices using Python's `enumerate()` function to create **user_map** and **product_map**.  
   - These mappings help in transforming the dataset into a sparse matrix format.  

3. Creating a Sparse Matrix:
   - A sparse **User-Product Interaction matrix** is created using `csr_matrix`.  
   - The matrix stores only nonzero rating values, making it efficient for large datasets.  

4. Training the KNN Model:
   - The `NearestNeighbors` model from `sklearn` is trained using **cosine similarity** to find similar users.  

5. Generating Recommendations:  
   - The function `recommend_real_time()` retrieves the nearest neighbors for a given user.  
   - Recommended product indices are converted back to **original ProductIDs** using a **reverse mapping**.  
   - If no recommendations are found, it falls back to the **most popular products** based on rating counts.  

6. Example Usage:  
   - The script selects a **random user** and recommends products.  
   - The recommended product list is printed as output.  

This approach efficiently suggests relevant Amazon products using collaborative filtering. 
