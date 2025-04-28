# Fingerprint-Based Cryptographic Key Generation

A secure biometric encryption system that generates cryptographic keys from fingerprint images using deep learning and cryptographic techniques.

## Description

This project implements a novel approach to biometric encryption by combining deep learning-based fingerprint feature extraction with cryptographic key generation. The system uses a CNN-based architecture to extract unique features from fingerprint images and converts them into secure cryptographic keys.

## Features

- Deep learning-based fingerprint feature extraction
- Secure cryptographic key generation
- ECC (Elliptic Curve Cryptography) integration
- SHA-256 hashing for key stability
- Robust encryption and decryption capabilities

## Dependencies

- opencv-python==4.5.3.56
- numpy==1.21.2
- tensorflow==2.15.0
- pandas==2.2.2
- cryptography==42.0.5
- datasketch==1.5.10
- reedsolo==1.7.0

## Project Structure

```
MiniProject/
├── Dataset/                 # Contains fingerprint dataset
├── results/                 # Stores model outputs and results
├── requirements.txt         # Project dependencies
└── fingerprint-based-cryptographic-key-generation.ipynb  # Main implementation notebook
```
## Dataset Used : FVC 2000 Dataset
FVC2000 is a standard fingerprint dataset released during the First International Fingerprint Verification Competition (FVC 2000).
It was designed to benchmark fingerprint verification algorithms by providing a diverse, real-world collection of fingerprint images.
## Model Architecture

The model uses a CNN architecture with the following layers:

```
┏━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┳━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┳━━━━━━━━━━━━━━━━━┓
┃ Layer (type)                         ┃ Output Shape                ┃         Param # ┃
┡━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━╇━━━━━━━━━━━━━━━━━━━━━━━━━━━━━╇━━━━━━━━━━━━━━━━━┩
│ conv2d (Conv2D)                      │ (None, 126, 126, 32)        │             320 │
├──────────────────────────────────────┼─────────────────────────────┼─────────────────┤
│ max_pooling2d (MaxPooling2D)         │ (None, 63, 63, 32)          │               0 │
├──────────────────────────────────────┼─────────────────────────────┼─────────────────┤
│ conv2d_1 (Conv2D)                    │ (None, 61, 61, 64)          │          18,496 │
├──────────────────────────────────────┼─────────────────────────────┼─────────────────┤
│ max_pooling2d_1 (MaxPooling2D)       │ (None, 30, 30, 64)          │               0 │
├──────────────────────────────────────┼─────────────────────────────┼─────────────────┤
│ conv2d_2 (Conv2D)                    │ (None, 28, 28, 128)         │          73,856 │
├──────────────────────────────────────┼─────────────────────────────┼─────────────────┤
│ max_pooling2d_2 (MaxPooling2D)       │ (None, 14, 14, 128)         │               0 │
├──────────────────────────────────────┼─────────────────────────────┼─────────────────┤
│ flatten (Flatten)                    │ (None, 25088)               │               0 │
├──────────────────────────────────────┼─────────────────────────────┼─────────────────┤
│ dense (Dense)                        │ (None, 128)                 │       3,211,392 │
├──────────────────────────────────────┼─────────────────────────────┼─────────────────┤
│ dropout (Dropout)                    │ (None, 128)                 │               0 │
├──────────────────────────────────────┼─────────────────────────────┼─────────────────┤
│ dense_1 (Dense)                      │ (None, 64)                  │           8,256 │
└──────────────────────────────────────┴─────────────────────────────┴─────────────────┘
```

## Model Performance

- Training Duration: 200 epochs
- Generated Stable Key (SHA-256): 117b1b5ecf7ce3dd0dca795302d5f8daacc864e422742ffc3c90a02a70658a25
- ECC Private Key: 101424033646691196556206856324060542031991695985712986961885645282870766677362

## Usage

1. Clone the repository:
```bash
git clone https://github.com/PhilipGunjari/MiniProject.git
cd MiniProject
```

2. Install dependencies:
```bash
pip install -r requirements.txt
```

3. Run the Jupyter notebook:
```bash
jupyter notebook fingerprint-based-cryptographic-key-generation.ipynb
```

4. Follow the instructions in the notebook to:
   - Load and preprocess fingerprint images
   - Train the model
   - Generate cryptographic keys
   - Perform encryption/decryption

## Encryption Example

Original Message: "Secure Biometric Encryption"
Encrypted Ciphertext: d11426a468b9af6d2d27b63c354bed03e3f3be3df94d103755c3f9
Decrypted Message: "Secure Biometric Encryption"

## Contributions

Contributions are welcome! Please feel free to submit a Pull Request.

## Acknowledgements

- OpenCV for image processing capabilities
- TensorFlow for deep learning framework
- Cryptography library for secure key generation
- All contributors and maintainers

## Security Considerations

- The system uses industry-standard cryptographic algorithms
- Private keys are securely generated and stored
- The model has been trained to ensure stable key generation
- Regular security audits are recommended

## License

This project is licensed under the MIT License - see the LICENSE file for details. 
