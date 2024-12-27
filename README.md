# version format ex. "0.0.1"
version: "0.1.11"
#version: "0.0.2"

# Basic metadata for the agent
metadata:
  name: "recipe generator"
  description: "This flow helps you get recipe for provided food item."
  author: "sahasrakruthi" # This username should match your account username
  tags: [food, recipe, cooking, kitchen, dishes] # Tags are keywords used to categorize your flow
  private: false # Access control for your flows (true/false)
# Define the input variables required
inputs:
  dish:
    type: string #Currently we only support String format
    description: "Enter the name of dish."
    required: true
    example: "kheer, biriyani, garlic bread, etc."
  specification:
    type: string
    description: "Enter the name of the rapper whose style you want to mimic."
    required: true
    example: "not very sweet, spicy, with less fat, etc."

# LLM configuration
model:
  provider: "meta" # e.g., anthropic, openai, meta, etc.
  name: "llama-3.3-70b-instruct"


# For supported LLM models, refer to the documentation: https://docs.mira.network/sdk/core-concepts
#provider: "anthropic" # e.g., anthropic, openai, meta, etc.
 # name: "claude-3.5-s
# # Dataset configuration (Optional)
# dataset:
#   source: "author_name/dataset_name" # Make sure this data set exists
# Prompt template configuration
prompt: |
  give the recipe to make {dish} which is {specification}.
# ReadME configuration
readme: |
  This flow helps you get the recipe. Name the dish and specification, get the recipe. The model used in this flow is llama-3.1-8b-instruct:free.
  Example: Input1: kheer, Input2: not very sweet
