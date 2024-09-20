# AI-Powered Negotiation Chatbot

## Overview
This repository contains an AI-powered negotiation chatbot implemented using Hugging Face's `DialoGPT` model. The chatbot simulates a price negotiation process, allowing users to accept, reject, or propose counteroffers. The project features two models: a basic negotiation model and an advanced model that incorporates sentiment analysis to enhance user interactions.

---

## Features

### Basic Negotiation Model
* **Price Negotiation Logic**: 
    * Starts with a predefined maximum price.
    *  Accepts counteroffers within a specified range.
    *  Rejects offers below the minimum price.
    *  Proposes a new counteroffer based on the average of the last offer and the user's price.

### Advanced Negotiation Model with Sentiment Analysis
* **Sentiment Evaluation**:
    * Analyzes user input to detect sentiment (positive, neutral, or negative).
* **Dynamic Offer Adjustments**:
    * **Positive Sentiment**: Generates more generous counteroffers.
    * **Negative Sentiment**: Slightly increases the offer while maintaining a firm tone.
    * **Neutral Sentiment**: Makes moderate adjustments to offers.

---

## Getting Started

### Prerequisites
Ensure you have Python installed, along with the necessary libraries:

```bash
pip install transformers torch datasets

```

## Model Setup
Load the DialoGPT-medium model and tokenizer using the following code:

```python
from transformers import AutoModelForCausalLM, AutoTokenizer

tokenizer = AutoTokenizer.from_pretrained("microsoft/DialoGPT-medium")
model = AutoModelForCausalLM.from_pretrained("microsoft/DialoGPT-medium")
```

## Architecture

### Basic Model Logic
* The bot starts with a maximum price and evaluates user input.
* The negotiation logic is straightforward, responding with either acceptance, rejection, or a new counteroffer.

### Advanced Model Logic
* Utilizes sentiment analysis to adapt responses based on user sentiment:
    * Positive Sentiment: Generates more favorable offers.
    * Negative Sentiment: Responds with increased offers, while acknowledging the user's feelings.
    * Neutral Sentiment: Maintains a moderate approach to negotiation.
 
## Contributing
Contributions are welcome! If you have suggestions or improvements, please create a pull request or open an issue.



