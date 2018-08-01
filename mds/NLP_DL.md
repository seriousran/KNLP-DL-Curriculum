## NLP_DL (Natural Language Processing using Deep Learning)

### Libraries

### Datasets

### Papers
- Character-level Text Classification
  - Siwei Lai, Liheng Xu, Kang Liu and Jun Zhao, "Character-level Convolutional Networks for Text Classification," NIPS, 2015.
  - Yoon Kim, Yacine Jernite, David Sontag and Alexander M. Rush, "Convolutional Neural Networks for Sentence Classification, AAAI, 2016.
    - [released code by writer](https://github.com/yoonkim/lstm-char-cnn) | Lua + Torch
      - install Lua
        ```bash
        conda install -c alexbw lua-torch 
      - install torch and dependencies
        ```bash
          luarocks install nngraph
          luarocks install luautf8
          luarocks install cutorch
          luarocks install cunn
          git clone https://github.com/soumith/cudnn.torch.git
          cd cudnn.torch
          luarocks make cudnn-scm-1.rockspec
        ```

    - Abstract
      - CNN + LSTM RNN-LM
      - having fewer parameters, same as state-of-the-art performance
    - Introduction
      - language modeling
        - count-based model
          - traditional methods
          - making an n-th order Markov assumption and estimating n-gram probabilities via counting and seubsequent smoothing (Chen and Goodman 1998)
          - simple to train
          - probabilities of rare n-grams can be poorly estimated due to data sparsity
        - Neural Language Models (NLMs)
          - parameterization of words as vectors (word embeddings) and using them as inputs to a neural network (Bengio, Ducharme, and Vincent 2003; Mikolov et al. 2010)
          - NLMs have been shown to outperform count-based n-gram language models (Mikolov et al. 2011)
          - Embeddings of rare words can thus be poorly estimated, leading to high perplexities for rare words (and words surrounding them)
        - Proposed method
          - propose a language model that leverages subword information through a character-level CNN, RNN-LM
          - proposed model does not require morphological tagging as a pre-processing step
          - proposed model does not utilize word embeddings at all in the input layer
      - contributions
        - ahieve results on par with the existing state-of-the-art on the Penn TreeBank, despite having approximately 60% fewer parameters
        - on morphologically rich languages (Arabic, Czech, French, German, Spanish, and Russian). proposed model outperforms various baselines
    - Model
      - RNN
      - RNN-LM
      - Character-level CNN
        - input at time t = output from a character-level character-level CNN
        - temporal rather than spatial convolutions
        - capture the most important feature 0the one with the highest value0 for a given filter.
        - A filter is eseentially picking out a character n-gram, where the size of the n-gram corresponds to the filter width
        

