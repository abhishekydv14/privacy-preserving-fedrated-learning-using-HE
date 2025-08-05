Privacy-Preserving Federated Learning Using Homomorphic Encryption
<div align="center">

</div>

This project demonstrates a privacy-preserving federated learning (FL) system using Homomorphic Encryption (HE). It features a Privacy-Enhanced Multi-Layer Perceptron (PEMLP) model, enabling multiple clients to collaboratively train a global model without revealing their raw data or local model updates to a central server.

🔐 Federated Learning + Homomorphic Encryption = Secure & Private Model Training
The core idea is to perform model aggregation on encrypted parameters, ensuring that the server can combine knowledge from all clients without ever seeing the individual contributions in plaintext.

🧠 Project Highlights
Secure Aggregation: Implements the Federated Averaging (FedAvg) algorithm where client model weights are encrypted before transmission.

Homomorphic Encryption: Uses the CKKS (Cheon-Kim-Kim-Song) scheme via the TenSEAL library to perform computations on encrypted data.

Local Training: Trains local Multi-Layer Perceptron (MLP) models on simulated, distributed client datasets using PyTorch.

Server-Side Operations: The central server aggregates the encrypted model weights without needing the decryption key.

Classification Task: Designed for binary classification on synthetic tabular data.

🛠️ Technologies Used
Python 3

TenSEAL: For homomorphic encryption operations.

PyTorch: For building and training the neural network models.

NumPy & Scikit-learn: For data generation, manipulation, and evaluation.

Jupyter Notebook: For interactive demonstration and visualization.

📁 Project Structure
privacy-preserving-fedrated-learning-using-HE/
│
├── PEMLP_implemantation.ipynb    # Main notebook with FL and HE implementation
├── README.md                     # Project documentation (this file)
└── requirements.txt              # List of dependencies
🚀 How It Works
The system follows a standard federated learning workflow, augmented with homomorphic encryption at the communication step.

<p align="center">
<img src="https://i.imgur.com/gKRAMYm.png" alt="Workflow Diagram" width="800"/>
</p>

Initialization: A global model is initialized on the server. Synthetic classification data is generated and distributed among multiple clients.

Local Training: Each client trains its local MLP model on its partition of the data for a few epochs.

Encryption: Before sending the updated model weights to the server, each client encrypts them using a public HE key.

Secure Aggregation: The server receives the encrypted weights from all clients. It performs Federated Averaging by summing the encrypted weight tensors and dividing by the number of clients—all without decryption.

Decryption & Update: The resulting aggregated (and still encrypted) global model weights are sent back to the clients (or decrypted by a trusted entity). For this simulation, we decrypt the final model at the end of all rounds to evaluate its performance.

🧪 Getting Started
Prerequisites
Python 3.8+

CMake (may be required for TenSEAL installation)

Installation
Clone the repository:

Bash

git clone https://github.com/abhishekydv14/privacy-preserving-fedrated-learning-using-HE.git
cd privacy-preserving-fedrated-learning-using-HE
Install the required packages:
It is recommended to use a virtual environment.

Bash

pip install -r requirements.txt
Alternatively, you can install packages manually:

Bash

pip install torch scikit-learn tenseal numpy matplotlib
⚠️ Note on TenSEAL Installation:
TenSEAL's installation can be tricky due to its C++ backend. Ensure your PyTorch version is compatible. If you encounter issues, please consult the official TenSEAL installation guide.

▶️ Running the Notebook
Launch Jupyter Notebook:

Bash

jupyter notebook
Open and Run:
Open the PEMLP_implemantation.ipynb notebook and run the cells in order to see the simulation in action. The notebook includes visualizations of model accuracy, weight convergence, and training loss.

📌 Future Work
[ ] Add support for real-world datasets like MNIST or CIFAR-10.

[ ] Extend the implementation to Convolutional Neural Networks (CNNs) and other complex architectures.

[ ] Benchmark performance and privacy guarantees against other techniques like Differential Privacy (DP).

[ ] Optimize the encryption/decryption process to improve scalability and reduce computational overhead.

🤝 Acknowledgements
The OpenMined community for developing and maintaining TenSEAL.

The PyTorch team for their excellent deep learning framework.

The broader research community in privacy-preserving machine learning whose work inspired this project.

📜 License
This project is licensed under the MIT License. See the LICENSE file for details.

✍️ Author
Abhishek Kumar Yadav
M.Tech in Information Security @ IIIT Allahabad
