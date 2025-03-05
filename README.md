# Fine-Tuning LLaMA-3.1-8B for Quote Generation

## Overview
This project fine-tunes the LLaMA-3.1-8B model using **Unsloth** to generate meaningful quotes based on user-provided tags. The dataset consists of thousands of English quotes, each labeled with relevant tags, and has been formatted in the **Alpaca** style. The model learns to associate different topics and themes with appropriate quotes, improving its ability to generate insightful and contextually relevant responses.

The goal of this fine-tuning process is to create a system that allows users to input a set of tags (e.g., "philosophy, wisdom, life") and receive a well-formed quote that aligns with those themes. The dataset and fine-tuning approach ensure that the generated quotes remain diverse, meaningful, and high-quality.

## Dataset
The dataset consists of quotes along with their respective authors and tags. The original dataset can be found [here](https://huggingface.co/datasets/Abirate/english_quotes).

### Data Instance Example
```
{
    "author": "Ralph Waldo Emerson",
    "quote": "To be yourself in a world that is constantly trying to make you something else is the greatest accomplishment.",
    "tags": ["accomplishment", "be-yourself", "conformity", "individuality"]
}
```

### Fields
- author: The name of the quote's author.
- quote: The actual quote.
- tags: Topics related to the quote.

The dataset was reformatted into the **Alpaca** format, where each entry includes an instruction, input, and output. Below is an example of the dataset after reformatting:
```
{
    "quote": "Be the change that you wish to see in the world.",
    "author": "Mahatma Gandhi",
    "tags": ["action", "change", "inspirational", "philosophy", "wish"],
    "text": "Below is an instruction that describes a task, paired with an input that provides further context. Write a response that appropriately completes the request.

### Instruction:
You are a quote generator, who generates quotes based on the input tags.

### Input:
action, change, inspirational, philosophy, wish

### Response:
\"Be the change that you wish to see in the world.\"
<|end_of_text|>"
}
```

## Example output
Input tags: _carpe-diem, educational, learning, inspirational_

Output quote: 
> "Do not let your schooling interfere with your education."

## Using the Fine-Tuned Model
The fine-tuned LLaMA-3.1-8B model has been uploaded to Hugging Face and can be accessed using this [link](https://huggingface.co/sidd-py/llama3.1-8b-fine-tuned).

To load and use this model, you can refer to this [notebook](Using_fine_tuned_llama_model.ipynb).
The notebook demonstrates how to:

- Load the fine-tuned model using Unsloth
- Format the input in the required Alpaca-style prompt
- Generate quotes based on the provided tags

To generate quotes for different topics, simply replace the input in the last cell with your desired set of tags.
