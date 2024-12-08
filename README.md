# Ferrum Overall Project Breakdown
##### 2025 Goal

## Step 1: Establish Foundations
- [ ] **Learn Transformer Basics**
  - [ ] Read "Attention Is All You Need" paper  
  - [ ] Review simplified tutorials or blog posts on Transformers  
  - [ ] Understand attention mechanisms and positional embeddings  
- [ ] **Familiarize With Candle**
  - [ ] Explore Candle’s documentation and example models  
  - [ ] Run a small toy experiment (e.g., MLP or CNN) to understand Candle’s workflow  
- [ ] **Plan Project Scope**
  - [ ] Decide on target model complexity (e.g., small parameter count)  
  - [ ] Set hardware and time constraints  

## Step 2: Prepare Data and Tokenization
- [ ] **Data Selection**
  - [ ] Identify a small, open-domain text dataset (e.g., Project Gutenberg texts)  
  - [ ] Download and clean the corpus (remove extraneous formatting, non-UTF8 chars)  
- [ ] **Tokenization Approach**
  - [ ] Choose a tokenization method (e.g., byte-pair encoding)  
  - [ ] Implement a simple tokenizer or integrate an existing Rust tokenizer library  
  - [ ] Verify tokenization on sample text (ensure reasonable subwords)  
- [ ] **Data Pipeline**
  - [ ] Build scripts to convert raw text into training batches (e.g., fixed sequence length)  
  - [ ] Shuffle and split data into training and validation sets  

## Step 3: Implement the Transformer Model in Rust/Candle
- [ ] **Core Components**
  - [ ] Implement embedding layers (word embeddings, positional embeddings)  
  - [ ] Implement multi-head attention mechanism:
    - [ ] Q, K, V projection layers  
    - [ ] Attention score computation and scaling  
    - [ ] Output projection layer  
  - [ ] Implement feed-forward network (FFN) module:
    - [ ] Two-layer MLP with nonlinearity  
    - [ ] Layer normalization modules  
- [ ] **Assemble the Encoder/Decoder**
  - [ ] Stack multiple attention + FFN blocks  
  - [ ] Add layer norms and dropout as needed  
  - [ ] Implement final output projection to logits  
- [ ] **Test Individual Components**
  - [ ] Run a forward pass on dummy data and check output shapes  
  - [ ] Verify attention output correctness with small test inputs  

## Step 4: Training Loop and Optimization
- [ ] **Training Setup**
  - [ ] Choose optimizer (e.g., Adam) and learning rate  
  - [ ] Define loss function (cross-entropy on next-token prediction)  
  - [ ] Implement gradient calculation and parameter updates in Candle  
- [ ] **Training Utilities**
  - [ ] Implement a simple training loop over epochs  
  - [ ] Add checkpointing (save model weights periodically)  
  - [ ] Add logging for loss, validation perplexity  
- [ ] **Initial Training Runs**
  - [ ] Train on a small subset to ensure code runs and loss decreases  
  - [ ] Check if gradients flow and no NaN values appear  

## Step 5: Evaluate and Refine
- [ ] **Basic Evaluation**
  - [ ] Prompt the model with simple texts and observe generated output  
  - [ ] Measure perplexity on a held-out validation set  
- [ ] **Hyperparameter Tuning**
  - [ ] Experiment with learning rate, batch size, and sequence length  
  - [ ] Adjust model depth or hidden size if training is stable  
- [ ] **Data Improvements**
  - [ ] Expand dataset if training stabilizes at smaller scale  
  - [ ] Improve tokenization (e.g., build a better vocabulary) if needed  

## Step 6: Documentation and Project Wrap-Up
- [ ] **Code Documentation**
  - [ ] Comment code thoroughly, explaining each module and class  
  - [ ] Add a README detailing setup, training instructions, and usage  
- [ ] **Reflections**
  - [ ] Document lessons learned, pitfalls encountered, and future improvements  
- [ ] **Optional Enhancements**
  - [ ] Explore adding sampling techniques (top-k, top-p) to improve generation quality  
  - [ ] Consider integrating simple interactive demos or notebooks  

## Step 7: Longer-Term Iteration (If Desired)
- [ ] **Model Scaling**
  - [ ] Increase number of parameters and layers if resources allow  
  - [ ] Try different architectures (e.g., GPT-style decoder-only vs. full encoder-decoder)  
- [ ] **Deployment**
  - [ ] Package model weights and inference script for easy sharing  
  - [ ] Possibly host the model on a local server to interact with it  
