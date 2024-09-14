# D2CAssistant: Direct-to-Consumer Customer Support Chatbot

D2CAssistant is an AI-powered customer service chatbot designed to assist with order-related queries for Direct-to-Consumer (D2C) businesses. It provides fast, personalized, 24/7 support, managing routine customer interactions such as placing orders, modifying or canceling existing orders, and handling returns or exchanges. D2CAssistant streamlines the customer service experience, making it more efficient for both businesses and customers.

## Features

- Greets customers and collects order numbers
- Handles common customer service areas such as:
  - Placing new orders
  - Checking order status
  - Modifying or canceling orders
  - Processing returns or exchanges
  - Addressing payment-related queries
  - Providing delivery tracking information
- Offers product recommendations and promotions
- Escalates complex issues to human representatives
- Collects necessary details for follow-up calls, such as contact number and preferred callback time
- Generates JSON summaries of customer interactions, capturing key details such as order ID, issue description, resolution status, and more

## Prerequisites

Before running D2CAssistant, ensure you have the following installed:

- Python 3.7 or higher
- pip (Python package installer)

## Installation

1. Clone this repository:
   ```
   git clone https://github.com/yourusername/D2CAssistant.git
   cd D2CAssistant
   ```

2. Install the required libraries:
   ```
   pip install openai python-dotenv panel
   ```

## OpenAI API Key

To use the OpenAI API, you will need to obtain an API key:

1. Sign up for an account at [OpenAI](https://openai.com/)
2. Navigate to the API section and create a new API key
3. Create a `.env` file in the project root directory
4. Add your API key to the `.env` file:
   ```
   OPENAI_API_KEY=your_api_key_here
   ```

## Usage

1. Run the Python script:
   ```
   python d2c_assistant.py
   ```

2. Interact with D2CAssistant using the provided chat interface to simulate customer support interactions.

## How it Works

1. **API Setup**: The code uses the OpenAI API to generate AI-driven responses. It securely loads the API key from the `.env` file using the `dotenv` library.

2. **Helper Functions**:
   - `get_completion()`: Sends a single prompt to the OpenAI API.
   - `get_completion_from_messages()`: Sends a list of conversational messages to the API, enabling more natural interactions.

3. **Chat Interface**: The `collect_messages()` function manages user input and bot responses, and it uses the `Panel` library to create a live, interactive chat interface.

4. **Context and Knowledge Base**: The bot's behavior is controlled through the `context` variable, which defines how it handles various order-related queries and escalations.

5. **User Interaction**: 
   - The bot greets the customer and requests their order number or relevant details.
   - It identifies the customer's issue (e.g., placing an order, tracking delivery) and provides an immediate resolution if possible.
   - For unresolved issues, it escalates the conversation to a human representative, collecting necessary information for a follow-up call, such as preferred callback time and language.

6. **JSON Summary**: After each conversation, the bot generates a detailed JSON summary of the customer interaction. This includes the order ID, issue type, resolution status, product recommendations (if any), and more, which can be stored for future reference or analysis.

## Customization

You can customize D2CAssistant's behavior by modifying the `context` variable within the script. This allows you to tweak the types of customer issues it handles, add new features, or adjust its conversational tone and style.

## Contributing

Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to modify.

## License

[MIT License](LICENSE)

## Acknowledgments

- OpenAI for providing the GPT model
- Panel library for powering the interactive interface
