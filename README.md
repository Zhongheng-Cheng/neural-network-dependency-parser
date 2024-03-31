# Neural Network Dependency Parser

In this assignment you will train a feed-forward neural network to predict the transitions of an arc-standard dependency parser. The input to this network will be a representation of the current state (including words on the stack and buffer). The output will be a transition (shift, left_arc, right_arc), together with a dependency relation label.

[Description](https://courseworks2.columbia.edu/courses/191061/assignments/1233455)

# Obtaining the Vocabulary

```bash
python3 get_vocab.py data/train.conll data/words.vocab data/pos.vocab
```

# Saving Training Matrices

```bash
python3 extract_training_data.py data/train.conll data/input_train.npy data/target_train.npy
python3 extract_training_data.py data/dev.conll data/input_dev.npy data/target_dev.npy
```

# Run the Training

```bash
python3 train_model.py data/input_train.npy data/target_train.npy data/model.pt
```

# Print CoNLL Formatted Parse Trees

```bash
python3 decoder.py data/model.pt data/dev.conll
```

# Evaluate the Parser

```bash
python3 evaluate.py data/model.pt data/dev.conll
```
