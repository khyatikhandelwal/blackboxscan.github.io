# BlackBoxScanner Documentation

## Installation

```bash
pip install blackbox-scanner
```

## Classes and Methods

### `ScannedOutputs`

A utility class for storing and manipulating model outputs.

#### Methods

- `add_token_output(token, output)`: Add a token and its corresponding output to the collection.
- `get_total()`: Calculate the total of all outputs.
- `get_tokens()`: Retrieve all tokens and their outputs.
- `get_perplexity()`: Compute the average output value.
- `get_top_tokens(greedy_top_tokens, greedy_score_list)`: Generate a dictionary of top tokens with their scores.
- `word_embeddings(word_embeds)`: Store and return word embeddings.

### `GenerativeModelOutputs`

Analyze generative language model outputs.

#### Methods

##### `sentence_log_likelihoods(words)`

Compute negative log-likelihoods for tokens in a given context.

**Parameters:**
- `words` (list or str): Context provided to the model

**Returns:** 
- `ScannedOutputs`: Object containing tokens and their negative log-likelihoods

**Example:**
```python
context = "The furry pet is a ..."
output = gmo.sentence_log_likelihoods(context)
```

##### `view_topk(input_sentence, k, get_plot=False)`

Retrieve top-k probable next tokens for a given context.

**Parameters:**
- `input_sentence` (str): Input context
- `k` (int): Number of top tokens to retrieve
- `get_plot` (bool, optional): Generate visualization of token probabilities

**Returns:**
- `ScannedOutputs`: Dictionary of top tokens and their scores

**Note:** Uses a greedy approach for token selection.

### `EmbeddingOutputs`

Analyze and visualize word embeddings for encoder models.

#### Methods

##### `get_embeddings_output(words_list)`

Extract normalized word embeddings.

**Parameters:**
- `words_list` (list): List of words to analyze

**Returns:**
- `ScannedOutputs`: Dictionary of word embeddings

### Future Roadmap

- Implement more sophisticated token selection strategies
- Enhance embedding visualization methods
- Add support for additional model architectures

## Contributing

We welcome contributions! Please submit pull requests to help improve BlackBoxScanner.

## License

[Insert License Information]
