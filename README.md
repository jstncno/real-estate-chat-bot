Real Estate Chat Bot
====================

Final project for [Udacity's Generative AI course][genai].

## Setup

1.  Install dependencies for your workbook kernal from `requirements.txt`
2.  This uses OpenAI's GPT-3 model. Set your OpenAI API key in the `.env` file
    (along with the appropriate URL base). The `%dotenv` stanza will load these
    values into the environment
3.  To use the LLM to generate real estate listings, remove the
    `real_estate_listings.json` file and run the notebook.
      - **Note:** the LLM does not 100% reliably generate proper JSON responses
        as instructed in the prompt, and it may take a few tries for it to
        generate all 10 listings successfully. The `real_estate_listings.json`
        file is included as a backup.

## Project Overview

### Project Introduction

Imagine you're a talented developer at "Future Homes Realty", a forward-thinking
real estate company. In an industry where personalization is key to customer
satisfaction, your company wants to revolutionize how clients interact with real
estate listings. The goal is to create a personalized experience for each buyer,
making the property search process more engaging and tailored to individual
preferences.

### The Challenge
Your task is to develop an innovative application named "HomeMatch". This
application leverages large language models (LLMs) and vector databases to
transform standard real estate listings into personalized narratives that
resonate with potential buyers' unique preferences and needs.

### Core Components of "HomeMatch"

**Understanding Buyer Preferences:**
- Buyers will input their requirements and preferences, such as location,
  property type, budget, amenities, and lifestyle choices.
- The application uses LLMs to interpret these inputs in natural language,
  understanding nuanced requests beyond basic filters.

**Integrating with a Vector Database:**
- Connect "HomeMatch" with a vector database, where all available property
  listings are stored.
- Utilize vector embeddings to match properties with buyer preferences, focusing
  on aspects like neighborhood vibes, architectural styles, and proximity to
  specific amenities.

**Personalized Listing Description Generation:**
- For each matched listing, use an LLM to rewrite the description in a way that
  highlights aspects most relevant to the buyer’s preferences.
- Ensure personalization emphasizes characteristics appealing to the buyer
  without altering factual information about the property.

**Listing Presentation:**
- Output the personalized listing(s) as a text description of the listing.

## Project Instructions
In order to create the "HomeMatch" application, you can use these steps for
uidance. Build the "HomeMatch" application in a Jupyter Notebook or Python
file(s).

**Step 1: Setting Up the Python Application**
- _Initialize a Python Project:_ Create a new Python project, setting up a
  virtual environment and installing necessary packages like LangChain, a
  suitable LLM library (e.g., OpenAI's GPT), and a vector database package
  compatible with Python (e.g., ChromaDB or LanceDB). If you don't wish to
  create your files from scratch, starter files are available in the workspace
  on the next page as an application skeleton.

**Step 2: Generating Real Estate Listings**
- Generate real estate listings using a Large Language Model. Generate at least
  10 listings This can involve creating prompts for the LLM to produce
  descriptions of various properties. An example of a listing might be:

  ```
  Neighborhood: Green Oaks
  Price: $800,000
  Bedrooms: 3
  Bathrooms: 2
  House Size: 2,000 sqft

  Description: Welcome to this eco-friendly oasis nestled in the heart of Green Oaks. This charming 3-bedroom, 2-bathroom home boasts energy-efficient features such as solar panels and a well-insulated structure. Natural light floods the living spaces, highlighting the beautiful hardwood floors and eco-conscious finishes. The open-concept kitchen and dining area lead to a spacious backyard with a vegetable garden, perfect for the eco-conscious family. Embrace sustainable living without compromising on style in this Green Oaks gem.

  Neighborhood Description: Green Oaks is a close-knit, environmentally-conscious community with access to organic grocery stores, community gardens, and bike paths. Take a stroll through the nearby Green Oaks Park or grab a cup of coffee at the cozy Green Bean Cafe. With easy access to public transportation and bike lanes, commuting is a breeze.
  ```
- You'll use these listings to populate the database for testing and development
  of "HomeMatch".

**Step 3: Storing Listings in a Vector Database**
- _Vector Database Setup:_ Initialize and configure ChromaDB or a similar vector
  database to store real estate listings.
- _Generating and Storing Embeddings:_ Convert the LLM-generated listings into
  suitable embeddings that capture the semantic content of each listing, and
  store these embeddings in the vector database.

**Step 4: Building the User Preference Interface**
- Collect buyer preferences, such as the number of bedrooms, bathrooms,
  location, and other specific requirements from a set of questions or telling
  the buyer to enter their preferences in natural language. You can hard-code
  the buyer preferences in questions and answers, or collect them interactively
  however you'd like, example:

  ```
  questions = [
    "How big do you want your house to be?",
    "What are 3 most important things for you in choosing this property?",
    "Which amenities would you like?",
    "Which transportation options are important to you?",
    "How urban do you want your neighborhood to be?",
  ]
  answers = [
    "A comfortable three-bedroom house with a spacious kitchen and a cozy living room.",
    "A quiet neighborhood, good local schools, and convenient shopping options.",
    "A backyard for gardening, a two-car garage, and a modern, energy-efficient heating system.",
    "Easy access to a reliable bus line, proximity to a major highway, and bike-friendly roads.",
    "A balance between suburban tranquility and access to urban amenities like restaurants and theaters.",
  ]
  ```
- _Buyer Preference Parsing:_ Implement logic to interpret and structure these
  preferences for querying the vector database.

**Step 5: Searching Based on Preferences**
- _Semantic Search Implementation:_ Use the structured buyer preferences to
perform a semantic search on the vector database, retrieving listings that most
closely match the user's requirements.
- _Listing Retrieval Logic:_ Fine-tune the retrieval algorithm to ensure that
  the most relevant listings are selected based on the semantic closeness to the
  buyer’s preferences.

**Step 6: Personalizing Listing Descriptions**
- _LLM Augmentation:_ For each retrieved listing, use the LLM to augment the
  description, tailoring it to resonate with the buyer’s specific preferences.
  This involves subtly emphasizing aspects of the property that align with what
  the buyer is looking for.
- _Maintaining Factual Integrity:_ Ensure that the augmentation process enhances
  the appeal of the listing without altering factual information.


## Rubric

### Synthetic Data Generation

- [x] Generating Real Estate Listings with an LLM
    - The submission must demonstrate using a Large Language Model (LLM) to
      generate at least 10 diverse and realistic real estate listings containing
      facts about the real estate.

### Semantic Search

- [x] Creating a Vector Database and Storing Listings
    - The project must demonstrate the creation of a vector database and
      successfully storing real estate listing embeddings within it.
      The database should effectively store and organize the embeddings
      generated from the LLM-created listings.

- [x] Semantic Search of Listings Based on Buyer Preferences
    - The application must include a functionality where listings are
      semantically searched based on given buyer preferences. The search should
      return listings that closely match the input preferences.

### Augmented Response Generation

- [x] Logic for Searching and Augmenting Listing Descriptions
    - The project must demonstrate a logical flow where buyer preferences are
    used to search and then augment the description of real estate listings.
    The augmentation should personalize the listing without changing factual
    information.

- [x] Use of LLM for Generating Personalized Descriptions
    - The submission must utilize an LLM to generate personalized descriptions
      for the real estate listings based on buyer preferences. The descriptions
      should be unique, appealing, and tailored to the preferences provided.


[genai]: https://www.udacity.com/course/computer-vision-and-generative-AI--cd13331
