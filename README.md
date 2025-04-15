# Open-Food-Fact
As part of a school project, I worked on the Open Food Facts database with the aim of structuring, transforming, and enhancing nutritional and sales data related to food products. The main goal was to make this data exploitable in a decision-making context through a PostgreSQL OLAP database, clear visualizations, and AI-driven analysis.

The project had several objectives. First, we designed a normalized relational database (OLTP), then built a multidimensional OLAP database to facilitate analysis. Our team implemented a complete customized data migration pipeline between the OLTP and OLAP using Azure Data Factory and Knime. At the same time, we created Power BI dashboards and developed two artificial intelligence models: one to predict the NutriScore and another to calculate a new environmental-nutritional score called the 'Open Food Facts Score' (OOFS).

# Database
From a technical standpoint, we first modeled and deployed a complete OLTP database on Azure PostgreSQL, including all entities (products, ingredients, brands, sales, additives, etc.), their relationships, and integrity constraints. Then, we built a star-schema OLAP database with dimensions derived from the OLTP and two fact tables—one for composition and another for sales. To ensure key consistency between the two databases hosted on different Azure servers, I wrote custom SQL scripts and used Knime to manage joins, ID matching, and required transformations.

# Knime
Thanks to Knime, our team processed and transformed the data in several steps. We designed workflows to connect nutritional and contextual data to their identifiers in the decision model, performed clustering on products based on their nutritional profile, and trained machine learning models (regression, decision tree, neural network) to automatically predict the NutriScore of incomplete products. Another AI model was developed to predict a new composite score integrating nutrition, degree of processing (Nova score), ecoscore, and data completeness.

# Power BI
Finally, we designed Power BI dashboards to track the distribution of NutriScores, explore PNNS food categories, and monitor sales by geographical area, brand, or nutritional score. The project resulted in a complete and operational analytical platform that enables visualization, prediction, and decision-making around the nutritional and financial quality of food products.

