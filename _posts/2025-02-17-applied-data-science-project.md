---
layout: post
author: Chen Yi
title: "Applied Data Science Project Documentation"
categories: ITD214
---
## Project Background
The objective of this project is to to optimize the overall customer experience and business profitability by leveraging valuable insights derived from customer feedback, product performance, and market trends. This goal focuses on improving the products, enhancing customer satisfaction, and aligning business operations with customer preferences and demands.

We selected dataset from Kaggle: Sephora Products and Skincare Reviews (URL: https://www.kaggle.com/datasets/nadyinky/sephora-products-and-skincare-reviews)

This dataset was collected via Python scraper in March 2023 and contains:
information about all beauty products (over 8,000) from the Sephora online store, including product and brand names, prices, ingredients, ratings, and all features.
user reviews (about 1 million on over 2,000 products) of all products from the Skincare category, including user appearances, and review ratings by other users

## Work Accomplished

1. Data Preparation:
Cleaned and preprocessed the dataset to handle missing values, inconsistencies, and formatting issues.
Extracted and transformed key features such as highlights, ingredients, and review_text.

2. Customer Segmentation:
Segmented customers into high-engagement and low-engagement groups using clustering techniques.
Analyzed demographic and product preference segments.

3. Preference Analysis:
Identified popular product attributes and ingredients using frequency analysis.
Conducted association rule mining to discover preferred product variations.

4. Visualization and Reporting:
Created visualizations to communicate insights effectively.
Provided actionable recommendations for marketing and inventory management.

### Data Preparation
1. Data Cleaning:
- Handled missing values in key columns like highlights, ingredients, and review_text.
- Standardized units for size and price_usd.
- Converted string representations of lists (e.g., highlights, ingredients) into actual lists using ast.literal_eval.
- Converted the 'demographic_segment' column (skin type, skin tone) to string.

3. Feature Engineering:
- Calculated discount percentage
- Created a customer_engagement_score by combining loves_count, rating, and reviews.
- Extracted 'average_review_length' from 'review_text' in reviews
- Tokenized and cleande ingredients to extract individual components.

4. Data Transformation:
- Converedt ingredients into a list of words.
- Normalized numerical features for clustering and modeling.

5. Exploratory Data Analysis (EDA)
- Distribution of Ratings and Reviews
- Calculate correlations between numerical features

### Modelling
1. Customer Segmentation:
- Applied K-Means clustering to group customers based on engagement metrics (loves_count, rating, reviews).
- Elbow method and silhouette score were used to determine the optimal number of clusters.

2. Preference Analysis:
- Analyzed highlights and ingredients to identify popular attributes and components.
- Used frequency analysis and visualization to highlight trends.

3. Association Rule Mining:
- Applied the Apriori algorithm to identify frequent itemsets and association rules for product variations (variation_type, variation_value).

### Evaluation
1. Clustering Performance:
 - Behavioral Segmentation: 
   - Evaluated clustering results using the Silhouette Score and Elbow Method.
   - Determined that 5 clusters provided the best balance between interpretability and performance.
  
 - Demographic Segmentation:
   - Analyzed the customer engagement score, ratings, reviews, and loves_count across these new demographic segments.

 - Product Preference Segmentation
   - Five unique clusters based on skincare product preferences.
   - Each cluster represents a different brand preference.
   - Brand-Specific Customer Trends.
  
2. Preference Analysis:
 - Product Attribute Preferences
   - Identified the most popular ingredients (e.g., "Hyaluronic Acid", "Retinol") and product attributes (e.g., "Vegan", "Cruelty-Free").
   
 - Association Rules:
   - Evaluated rules based on support, confidence, and lift.
   - Identified the most preferred product variations (e.g., "Size: 100 mL", "Color: Golden Sand").

## Recommendation and Analysis
1. Clustering Performance:
 - Behavioral Segmentation:
   - Key Insights:
     - Cluster 0: Luxury Buyers: 
      High price, good engagement, but moderate reviews. Target with exclusive, high-end products.
     - Cluster 1: Bargain Hunters:
      Low price, high engagement, but low satisfaction. Target with discounts, promotions, and value-driven marketing.
     - Cluster 2: Engaged Enthusiasts:
      Low price, high engagement, high satisfaction. Offer frequent deals, upsell mid-range products.
     - Cluster 3: Casual Shoppers:
      Low price, moderate engagement, high satisfaction. Engage with loyalty programs or occasional promotions.
     - Cluster 4: Loyal Brand Advocates:
      Low price, very high engagement and satisfaction. Focus on building brand loyalty with rewards, referral programs, and premium offers.
   - Actionable Strategies:
     - Luxury Buyers → Offer exclusive promotions, premium services
     - Engaged Enthusiasts → Encourage social sharing, upsell high-end items
     - Bargain Hunters → Use flash sales, budget-friendly product recommendations
     - Casual Shoppers & One-Time Buyers → Convert them using personalized discounts

 - Demographic Segmentation:
   - Key Insights:
     - High- Engagement & Most Popular Segments: "Normal - Dark", "Normal - Porcelain". High review counts and loves_count. Key for marketing efforts segments 
     - Skin Tones with Highest Ratings: "Oily - Ebony" , "Normal - Ebony". Lower engagement but high satisfaction.
     - Skin Types with Lowest Engagement: "Combination - Ebony", "Oily - Ebony". Underrepresented in the dataset.
   - Actionable Strategies:
     - For High-Engagement Groups
       - Target with Loyalty & Retargeting Campaigns. Normal-Dark, Oily-Porcelain, Dry-Dark customers engage a lot.
       - Offer exclusive discounts, subscriptions, or early access to new products.
       - Feature These Segments in Ads & Content
       - Use testimonials, social proof, or influencers from these segments.
     - For Low-Engagement or Underrepresented Groups
       - Investigate the Market Gap
       - The Ebony and Dark categories have fewer users but high ratings. Are there fewer products available for them? Do marketing images mostly show lighter skin tones?
       - Action: Introduce more diverse product ranges & representation.
     - For Low-Rated Segments (e.g., Combination - Ebony)
       - Find the Pain Points
       - Conduct sentiment analysis on reviews.
       - Identify common complaints (e.g., shade mismatch, texture issues).
       - Improve product descriptions and recommendations.

 - Product Preference Segmentation
   - Key Insights:
     - Five unique clusters based on skincare product preferences.
     - Each cluster represents a different brand preference.
     - Brand-Specific Customer Trends.
   - Actionable Strategies:
     - Targeted Marketing: Tailor marketing campaigns for each cluster, targeting customers who prefer brands like CLINIQUE, Tatcha, or Shiseido.
     - Product Recommendations: By associating products in the same cluster, recommend products with similar characteristics (e.g., skincare products from similar brands) to customers.
     - Inventory Management: Prioritize stock for the most popular clusters (like skincare with CLINIQUE and Tatcha).
  
2. Preference Analysis:
 - Product Attribute Preferences
   - Key Insights:
     - The word cloud highlights Extracts (Leaf, Fruit, Root), Glycerin, and Seed Oils as dominant ingredients. Indicates a strong consumer preference for plant-based and moisturizing components.
     - The bar chart shows Vegan and Cruelty-Free as the top product highlights. Suggests ethical and clean beauty is a major deciding factor for customers.
     - Highlights like Hydrating, Good for Dryness, and Without Parabens reinforce a focus on skin-friendly formulations.
   - Actionable Strategies:
     - Brands should emphasize natural, ethical, and skin-nourishing attributes in their product marketing.
     - Formulations featuring clean, hydrating, and plant-based ingredients will likely continue to dominate the market.
   
 - Association Rules:
   - Key Insights:
     - Color and “Original” Variation are strongly linked → If a product is tagged as "Original," it is highly likely to have a color variation. This suggests that "Original" may be a default option for color-based variations.
     - Size variations are perfectly predictable → All products with sizes like "2 oz" or "1.35 oz" are always categorized under the "Size" variation type. This can help in automatic categorization of new products.
     - Reinforce Color Variation Marketing → Given the strong relationship between "Original" and "Color," it may be beneficial to focus marketing strategies on color variations rather than size-based options.
   - Actionable Strategies:
     - Enhance Product Categorization
       - Automate variation type classification (e.g., size, color) based on frequent item sets.
       - Optimize search filters on the website by emphasizing color-based selections.
     - Personalized Marketing for Color Variations
       - Highlight "Original" variations in targeted promotions since they are strongly linked to color.
       - Use A/B testing to determine the best way to promote color-based variations.
     - Refine Inventory Management
       - Prioritize stocking "Original" variations with high color association.
       - Forecast demand trends based on strong variation relationships.
     - Leverage Insights for New Product Development
       - Develop color-centric product lines based on the strong "Original" and "Color" association.
       - Focus on introducing new shades or color variations to match customer preferences.

## AI Ethics
1. Privacy
- Potential Issues
  - User Data Exposure: The dataset contains sensitive user information, such as author_id, skin_type, skin_tone, eye_color, and hair_color. If not handled properly, this data could be used to identify individuals or infer personal attributes.
- Mitigation Strategies
  - Anonymization: Remove or anonymize personally identifiable information (PII) such as author_id before analysis.
  - Data Access Control: Restrict access to sensitive data to only authorized team members.

2. Fairness
- Potential Issues
  - Bias in Data: The dataset might overrepresent certain demographics (e.g., specific skin tones or hair colors), leading to biased insights that do not generalize to all customers.
- Mitigation Strategies
  - Bias Detection: Analyze the dataset for representation gaps (e.g., underrepresented skin types or tones) and address them through data augmentation or reweighting. 
  - Diverse Representation: Ensure that marketing and product recommendations cater to all customer segments, not just the majority.

3. Accuracy
- Potential Issues
  - Misinterpretation of Clusters: If clustering is based on poorly chosen features or parameters, the resulting segments may not accurately reflect customer behavior.
- Mitigation Strategies
  - Model Validation: Use cross-validation and robust evaluation metrics (e.g., F1-score, precision, recall) to ensure model accuracy.

4. Accountability
- Potential Issues
  - Unintended Consequences: Insights from the project (e.g., discontinuing low-performing products) might negatively impact certain customer groups or stakeholders.
- Mitigation Strategies
  - Stakeholder Communication: Engage with stakeholders (e.g., customers, product teams) to ensure their concerns are addressed.

5. Transparency
- Potential Issues
  - Lack of Documentation: If the data sources, methodologies, and assumptions are not documented, it might be difficult to reproduce or validate the results.
- Mitigation Strategies
  - Documentation: Maintain detailed documentation of data sources, preprocessing steps, modeling choices, and assumptions.
  - Open Communication: Share findings and methodologies with stakeholders in a clear and accessible manner.

## Source Codes and Datasets
[Dataset URL: https://www.kaggle.com/datasets/nadyinky/sephora-products-and-skincare-reviews
Upload your model files and dataset into a GitHub repo and add the link here. ](https://github.com/cynthiayiyi/ITD214_project)
