# Deep Learning Interview Questions

This folder contains interview questions focused on deep learning concepts, neural network architectures, and training techniques.

## Topics Covered

1. **Neural Network Fundamentals**
2. **Convolutional Neural Networks (CNNs)**
3. **Recurrent Neural Networks (RNNs)**
4. **Transformers**
5. **Training and Optimization**

---

## Questions

### 1. What is a neural network and how does it learn?
**Answer:** A neural network is a computational model inspired by biological neurons, consisting of layers of interconnected nodes. It learns through forward propagation (computing outputs) and backpropagation (computing gradients of the loss function and updating weights using gradient descent).

### 2. Explain the vanishing gradient problem.
**Answer:** In deep networks, gradients can become extremely small as they propagate backward through many layers, especially with activation functions like sigmoid or tanh. This causes early layers to learn very slowly or not at all. Solutions include ReLU activation, residual connections, batch normalization, and LSTM/GRU for RNNs.

### 3. What is the difference between ReLU and sigmoid activation functions?
**Answer:** 
- **Sigmoid**: Output between 0-1, suffers from vanishing gradients, computationally expensive
- **ReLU**: f(x) = max(0, x), faster computation, helps with vanishing gradients, but can cause "dying ReLU" problem where neurons output zero for all inputs. Variants like Leaky ReLU address this.

### 4. What is batch normalization and why is it useful?
**Answer:** Batch normalization normalizes layer inputs by subtracting the batch mean and dividing by batch standard deviation, then applies learnable scale and shift parameters. Benefits include:
- Faster training convergence
- Allows higher learning rates
- Reduces sensitivity to initialization
- Acts as a regularizer

### 5. Explain the architecture of a CNN.
**Answer:** CNNs consist of:
- **Convolutional layers**: Apply learnable filters to detect features
- **Pooling layers**: Reduce spatial dimensions (max pooling, average pooling)
- **Fully connected layers**: Combine features for final classification
Key concepts: kernel size, stride, padding, feature maps, receptive field.

### 6. What is dropout and how does it prevent overfitting?
**Answer:** Dropout randomly sets a fraction of neurons to zero during training. This prevents co-adaptation of neurons, forces the network to learn redundant representations, and acts as an ensemble of multiple networks. At inference time, all neurons are used but outputs are scaled.

### 7. Explain the transformer architecture.
**Answer:** Transformers use self-attention mechanisms instead of recurrence:
- **Self-attention**: Computes attention weights between all positions in a sequence
- **Multi-head attention**: Multiple attention mechanisms in parallel
- **Positional encoding**: Adds position information since there's no inherent sequence order
- **Feed-forward layers**: Process attention outputs
Key advantage: Parallelizable, captures long-range dependencies effectively.

### 8. What is the difference between LSTM and GRU?
**Answer:** Both are RNN variants designed to handle long-term dependencies:
- **LSTM**: Has forget gate, input gate, output gate, and cell state
- **GRU**: Simpler with reset gate and update gate, no separate cell state
GRU has fewer parameters and trains faster, but LSTM may perform better on complex sequences.

### 9. What are residual connections and why are they important?
**Answer:** Residual (skip) connections add the input of a layer directly to its output: y = F(x) + x. Benefits:
- Enable training of very deep networks
- Help with vanishing gradient problem
- Allow gradient to flow directly through shortcut
Introduced in ResNet, now widely used in many architectures.

### 10. Explain transfer learning in deep learning.
**Answer:** Transfer learning uses a model pre-trained on a large dataset (like ImageNet) as a starting point for a new task:
- **Feature extraction**: Freeze pre-trained layers, train only new classifier layers
- **Fine-tuning**: Unfreeze some/all layers and train with a lower learning rate
Benefits: Requires less data, faster training, often better performance, especially for small datasets.
