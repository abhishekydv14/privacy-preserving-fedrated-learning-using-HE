# Privacy-Preserving Federated Learning Using Homomorphic Encryption

This project demonstrates a privacy-preserving federated learning (FL) system using **Homomorphic Encryption (HE)**, focusing on a **Privacy-Enhanced Multi-Layer Perceptron (PEMLP)** model. The system enables secure model aggregation without revealing the raw local model weights or training data.

> 🔐 **Federated Learning + Homomorphic Encryption = Secure & Private Model Training**

---

## 🧠 Project Highlights

- Implements **Federated Averaging (FedAvg)** using encrypted weights.
- Uses **CKKS homomorphic encryption scheme** (via [TenSEAL](https://github.com/OpenMined/TenSEAL)).
- Trains **local MLP models** on simulated clients using **PyTorch**.
- Aggregates encrypted model weights on the server without decryption.
- Supports binary classification on synthetic/tabular datasets.

---

## 🛠️ Technologies Used

- 🐍 Python 3
- 🔐 [TenSEAL](https://github.com/OpenMined/TenSEAL) – for homomorphic encryption
- 🔦 PyTorch – for model building and training
- 📊 NumPy, Scikit-learn – for data generation and preprocessing
- 📓 Jupyter Notebook

---

## 📁 Project Structure

privacy-preserving-fedrated-learning-using-HE/
│
├── PEMLP_implemantation.ipynb # Main notebook with FL and HE implementation
├── README.md # Project documentation (this file)
└── requirements.txt # List of dependencies (optional, see below)

yaml
Copy
Edit

---

## 🚀 How It Works

1. **Dataset Creation**  
   Synthetic classification data is generated using `sklearn.datasets.make_classification`.

2. **Client Initialization**  
   Data is split among multiple clients, each training its own MLP model locally.

3. **Local Training**  
   Each client trains for a few epochs on its local data.

4. **Encryption**  
   Model weights are encrypted using CKKS before being sent to the server.

5. **Aggregation**  
   The server performs Federated Averaging directly on encrypted weights.

6. **Decryption and Evaluation**  
   Final global weights are decrypted and used for evaluation.

---

## 📷 Sample Output

Some metrics visualized in the notebook:

- Accuracy comparison between plaintext and encrypted models
- Weight convergence graphs
- Communication rounds and training loss

---

## 🧪 Requirements

Install the required packages using:

```bash
pip install torch scikit-learn tenseal numpy matplotlib
Note: TenSEAL may require CMake and PyTorch version compatibility. Refer to TenSEAL installation guide if issues arise.

▶️ Running the Notebook
Clone the repository:

bash
Copy
Edit
git clone https://github.com/abhishekydv14/privacy-preserving-fedrated-learning-using-HE.git
cd privacy-preserving-fedrated-learning-using-HE
Launch Jupyter Notebook:

bash
Copy
Edit
jupyter notebook PEMLP_implemantation.ipynb
Run the cells in order to see FL + HE in action.

🔒 Why Homomorphic Encryption?
Homomorphic Encryption allows computations on encrypted data without needing to decrypt it. This makes it ideal for federated learning where privacy of user data and model parameters is critical.

📌 Future Work
Add support for real-world datasets like MNIST or CIFAR-10.

Extend to CNNs and other deep models.

Benchmark against Differential Privacy (DP).

Improve performance and scalability.

🤝 Acknowledgements
OpenMined for TenSEAL

PyTorch community

Inspired by research in privacy-preserving machine learning

📜 License
This project is licensed under the MIT License.

✍️ Author
Abhishek Kumar Yadav
IIIT Allahabad | M.Tech in Network Security
🔗 GitHub

yaml
Copy
Edit

---

Let me know if you’d like a version with installation instructions for Google Colab or want badges (
