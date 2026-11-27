# Ethereum phishing detection with directed graph embeddings

Does a wallet’s transaction neighbourhood help identify phishing accounts beyond its own transfer history? This experiment compares random forests trained on the same EPTransNet wallets. One uses 12 behavioural features. The other adds a 32-dimensional representation learned by a directed graph convolutional network.

[Read the research manuscript (PDF)](report/manuscript.pdf) · [Explore the experiment notebook](notebooks/experiment.ipynb)

## Results

| Test metric | Wallet features | Wallet features + graph |
| --- | ---: | ---: |
| Average precision | 0.8743 | 0.9006 |
| Phishing-class F1 at threshold 0.5 | 0.6667 | 0.6875 |

At threshold 0.5, the augmented forest produced 17 fewer false alarms and missed one additional labelled phishing wallet. The single transductive split included 3,675 test wallets, 175 of them labelled phishing. A separate five-seed validation experiment compares neighbour aggregation with an identity operator.

## Running the notebook

Open the notebook in Google Colab, use a high-memory runtime if available, and run the cells in order. The notebook downloads EPTransNet with KaggleHub. Allow memory for the approximately 1.2 GB graph file and its in-memory representation.
