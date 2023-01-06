# ai-cli

This is a command line interface for sending text to the [OpenAI Completion API](https://beta.openai.com/docs/api-reference/completions/create).

## Installation

To install, clone the repository and run:

```bash
pip install -r requirements.txt
```

Then set the file to executable:

```bash
chmod +x ai
```

And place the folder in your PATH, and set your API key in the OPENAI_API_KEY environment variable. 

## Usage

To use the CLI, run:

```bash
ai [text] [options]
```

Where `[text]` is the text you want to send to the API and `[options]` are any of the optional arguments listed below.

## Options
    --model, default='text-davinci-003', type=str, help='The model to use for completion'
    --max_tokens, default=256, type=int, help='The maximum number of tokens to generate'
    --stop, default='', type=str, help='A string that, if encountered, will cause the API to stop generating tokens'
    --temperature, default=0.0, type=float, help='sampling temperature (default: 0.0)'
    --top_p, default=1.0, type=float, help='top-p filtering value (default: 1.0)'
    --frequency_penalty, default=0.0, type=float, help='penalty for generating frequent tokens (default: 0.0)'
    --presence_penalty, default=0.0, type=float, help='penalty for generating tokens not present in the prompt (default: 0.0)'
    --best_of, default=3, type=float, help='An optional integer specifying the number of completions to generate server-side and return the "best" (the one with the highest log probability per token)'

## Examples

Input:
```bash
ai write a python function that prints hello world
```

Output:
```python
def print_hello_world():
  print("Hello World")

print_hello_world()
```

Input:
```bash
ai write a Flask app that has 2 endpoints: / and /about
```

Output:
```python
from flask import Flask

app = Flask(__name__)

@app.route('/')
def home():
    return 'This is the home page'

@app.route('/about')
def about():
    return 'This is the about page'

if __name__ == '__main__':
    app.run()
```

Input:
```bash
ai write a sonnet about a dog named chip
```

Output:
```bash
Chip, my loyal pup, so full of love and joy,
Your wagging tail and happy bark bring me delight.
Your furry coat of brown and white, a sight to enjoy,
Your playful nature, so full of life and light.

Your eyes so bright, your nose so wet and cold,
Your bark so loud, your tail so full of wag.
Your love so strong, your loyalty so bold,
Your friendship, a treasure I will never lag.

Your loyalty and love, so strong and true,
Your friendship, a bond that will never break.
Your joy and happiness, so pure and true,
Your presence, a blessing I will never forsake.

Chip, my loyal pup, so full of love and joy,
Your friendship, a blessing I will always enjoy.
```