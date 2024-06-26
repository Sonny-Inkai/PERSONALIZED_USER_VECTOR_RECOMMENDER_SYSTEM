

---

# PUV: Personalized User Vectors Using Vector Database Recommender System

## Overview

With the rapid development of online platforms, recommendation systems have emerged to quickly provide users with the necessary information. Building personalized user profiles is crucial for accurate suggestions. However, creating user vectors through user demographics like age, location, work, etc., has many limitations due to users' unwillingness to provide information or providing incorrect information.

In this project, we propose **PUV: Personalized User Vectors**, a technique that addresses these shortcomings by personalizing user vectors based on the hotels they have reviewed. Additionally, the PipeCone vector database is used to store user vectors, improving accuracy when finding top-k similar users by utilizing the advantages of search algorithms.

## Table of Contents

- [Overview](#overview)
- [Introduction](#introduction)
- [Proposed Architecture](#proposed-architecture)
- [Dataset](#dataset)
- [Empirical Evaluation](#empirical-evaluation)
- [Results](#results)
- [Usage](#usage)
- [Contributing](#contributing)
- [License](#license)

## Introduction

Recommender systems play an important role in today’s society due to the rapid development of online platforms. Providing information quickly to users, a good recommendation system not only helps improve user experience but also optimizes profits for the manufacturer. This project aims to enhance the personalization of recommendation systems using user vectors derived from their reviews and ratings of hotels.

## Proposed Architecture

The architecture of the PUV recommender system is designed to enhance the recommendation process through several steps:

1. **Personalization of User Vectors**: We capture and process various user-specific data points such as stay history and user ratings, creating a unique vector representation for each user.
2. **Storing User Vectors**: The personalized vectors are transferred to the Pinecone vector database for efficient storage and retrieval.
3. **Retrieving Similar Users**: Using advanced search algorithms, the system queries the Pinecone vector database to retrieve the top-k most similar users for a given user vector.
4. **Generating Recommendations**: From the pool of similar users, the system selects the top-m items with the highest ratings to recommend to the user.

![Architecture Diagram](https://github.com/Sonny-Inkai/PERSONALIZED_USER_VECTOR_RECOMMENDER_SYSTEM/blob/main/image/PUV.png)

## Dataset

We used the Hotel Booking Rating Dataset, which includes:

- 38,801 rows of data
- 9 attributes including Hotel URL, Location, HotelID, Hotel Name, Descriptions, Address, UserID, User Name, and Ratings
- Data from 4,506 hotels in 10 different provinces/cities, and 6,471 users


### Data Pre-processing

The dataset was filtered to include users with 30 or more ratings, resulting in a training set of 38,066 rows and a testing set of 695 rows.

## Empirical Evaluation

We compared the performance of the PUV architecture using different pre-trained word embeddings against three baseline models: GLocal-K, AutoRec, and DeepICF. The RMSE metric was used for evaluation.

### Baseline Models

- **AutoRec**: Combines autoencoder techniques with collaborative filtering.
- **DeepICF**: Uses deep neural networks to capture nonlinear and high-order relationships between items.
- **GLocal-K**: Combines global and local features to improve performance.

### Evaluation Metric

The Root Mean Squared Error (RMSE) metric was used to evaluate and compare the experiments.

## Results

The PUV model, when integrated with the CafeBERT pre-trained word embedding, achieved the best performance with an RMSE of 1.581, outperforming all other baseline models.

| Model         | RMSE  |
|---------------|-------|
| AutoRec       | 2.145 |
| DeepICF       | 1.894 |
| GLocal-K      | 1.687 |
| PUV ViSoBERT  | 1.609 |
| PUV PhoBERTv2 | 1.597 |
| PUV CafeBERT  | 1.581 |



## Usage

To use the PUV recommender system, follow these steps:

1. **Clone the Repository**:
   ```sh
   git clone https://github.com/Sonny-Inkai/PERSONALIZED_USER_VECTOR_RECOMMENDER_SYSTEM.git
   cd PERSONALIZED_USER_VECTOR_RECOMMENDER_SYSTEM
   ```

## Contributing

We welcome contributions! Please read our [contributing guidelines](CONTRIBUTING.md) for details on the process for submitting pull requests.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

Feel free to replace the placeholders for images with the actual paths where you will store your images. If you need any further customization or additional sections, let me know!
