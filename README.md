# VAE
VAE VS  standard autoencoder using fashion_mnist

### Advanced Deep Learning Midterm - Karma El Gendy

#### Original Model: Deep Autoencoder
- **Architecture**:
  - **Encoder**: 
    - Three dense layers with 128, 64, and 32 units.
    - ReLU activation function.
    - Gradual reduction in input dimensionality.
  - **Bottleneck Layer**:
    - Dense layer with 18 units, ReLU activation.
    - Captures essential features.
  - **Decoder**:
    - Mirrors encoder architecture.
    - Gradual expansion back to the original size (784 units).
- **Training**:
  - Loss Function: Mean Squared Error (MSE).
  - Optimizer: Adam.

#### Improved Model: Variational Autoencoder (VAE)

- **Improvements Over Deep Autoencoder**:
  - **Latent Space Regularization**: 
    - Introduces Gaussian distribution in the latent space.
    - Combines mean and log variance vectors for regularization.
  - **Diverse Output**: 
    - Stochastic sampling from the latent space allows for diverse outputs.

#### Implementation

- **Libraries**:
  - Keras, TensorFlow, NumPy, Matplotlib.
  - Loaded Fashion MNIST dataset.

- **Encoder**:
  - Latent Dimension: 10.
  - Dense Layers: 512, 256, 128 units.
  - Outputs: Mean and log variance vectors.

- **Sampling Layer**:
  - Samples from Gaussian distribution.
  - Introduces stochasticity.

- **Decoder**:
  - Dense Layers: 128, 256, 512 units.
  - Output Layer: Sigmoid activation, 784 units.

- **Custom Loss Function**:
  - **Components**:
    - Reconstruction Loss: Binary cross-entropy.
    - KL Divergence Loss: Regularizes latent space.
  - **Total Loss**: Sum of reconstruction and KL divergence losses, scaled by 784.

- **Model Compilation**:
  - Optimizer: Adam.
  - Loss Function: Mean Squared Error.

- **Training**:
  - **Dataset**: Fashion MNIST.
  - **Epochs**: 50.
  - **Batch Size**: 128.
  - **Validation Loss**: Gradual decrease observed over epochs.

#### Results and Predictions
- **Encoding & Decoding**:
  - Encoded and decoded test images.
  - Displayed original, encoded, and decoded images.

- **Capabilities**:
  - **Interpolation**: Smooth transition between data points in the latent space.
  - **New Samples Generation**: Sampling from the Gaussian distribution allows generating new data points.
