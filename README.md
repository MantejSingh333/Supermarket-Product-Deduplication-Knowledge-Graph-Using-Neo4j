# Supermarket-Product-Deduplication-Knowledge-Graph-Using-Neo4j
End-to-end project cleaning, deduplicating, and modeling supermarket product data into a Neo4j knowledge graph to enable unified product comparison across multiple retailers.

Supermarket Product Deduplication & Knowledge Graph
Project Overview

This project focuses on cleaning, deduplicating, and modeling supermarket product data to create a unified structure that enables users to search for a product once and compare equivalent items and prices across multiple supermarket chains in New Zealand.

Different supermarkets often use inconsistent product names, categories, and identifiers, making price comparison difficult for everyday users. This project solves that problem by standardizing raw data and modeling it into a Neo4j knowledge graph that links equivalent products across stores.


Objective:

To enable a single-search experience where users can:

Find equivalent products across different supermarket chains

Compare prices and listings in one place

Avoid confusion caused by inconsistent naming and categorization

Data Cleaning & Deduplication (Excel & Power Query)

Raw supermarket data was cleaned and consolidated using Excel and Power Query:

Standardized text fields using TRIM, CLEAN, and lowercase

Removed exact duplicate rows (~20,000 rows reduced to ~700 unique records)

Removed redundant and unused columns

Converted price fields to currency data type

Converted all identifier columns to text to preserve uniqueness

Added a store name column to distinguish listings

Consolidated multiple raw files into a single CSV dataset

This process significantly reduced noise and prepared the data for graph modeling.


Knowledge Graph Design (Neo4j)

The cleaned data was modeled into a knowledge graph using Neo4j with the following nodes:

Node Types

Product

Category

Brand

Listing

Store


Relationship Design Principle

Relationships were designed to flow from less stable entities to more stable entities to prevent duplication and ensure consistency:

Listing → Product

Product → Brand

Product → Category

Listing → Store

This structure allows multiple store listings to reference the same core product entity while maintaining store-specific pricing and metadata.


Key Outcomes

Reduced raw data size by over 96% through deduplication

Created a scalable graph model for cross-store product comparison

Enabled flexible querying for:

Price comparison across stores

Brand-based and category-based searches

Store-specific listings


Tools & Technologies

Excel & Power Query (data cleaning and consolidation)

Neo4j (knowledge graph modeling)

CSV data pipelines

Entity resolution & deduplication techniques
