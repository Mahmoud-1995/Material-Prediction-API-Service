# Material-Prediction-API-Service
# Product Price Forecasting API Service

This API service provides a price forecasting solution for a product based on the contributing materials that form the final product. The service uses machine learning models (specifically `NeuralProphet`) to predict the future price of materials over a defined period and returns a forecast of the product price based on the weights and spot prices of various input materials.

## Table of Contents

- [Description](#description)
- [Features](#features)
- [Endpoints](#endpoints)
  - [Status](#get-status)
  - [Help](#get-help)
  - [Calculate](#get-calculate)
- [Running the Service](#running-the-service)
- [How the API Works](#how-the-api-works)
- [Contributing](#contributing)
- [License](#license)

---

## Description

This service accepts multiple material types as inputs, such as weight (in KG), spot price, and forecast period (in months), and returns the predicted price of the product over the specified period. The forecast starts from **February 2023**, as that is the last timestamp in the training data.

### Key Materials Used in the Forecast:

- **ST37** (Spot price, weight)
- **Copper** (Spot price, weight)
- **High Carbon** (Spot price, weight)
- **Medium Carbon** (Spot price, weight)
- **Aluminum** (Weight)
- **Grey Cast Iron** (Spot price, weight)
- **Nodular Cast Iron** (Spot price, weight)
- **Nonalloy Cast** (Spot price, weight)
- **Labor Hours**

Users can also specify a forecasting period (`months`) to define how many months into the future the predictions should go (defaults to 24 months).

## Features

- **Flexible Input**: Accepts a wide range of materials and prices.
- **Custom Forecast Period**: Allows the user to specify how many months to predict into the future.
- **Validation**: Ensures all required inputs are provided and that no price is missing for any supplied material.
- **NeuralProphet Models**: Uses time-series forecasting models for accurate predictions.
  
## Endpoints

### 1. **GET /status**

Checks if the API service is running.

#### Example Request:

```bash
GET /status
