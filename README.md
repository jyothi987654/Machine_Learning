# Is an Autoencoder Just a Fancy PCA?

A short, focused tutorial on the **autoencoder bottleneck**, using Fashion-MNIST to show
exactly when an autoencoder behaves like PCA and exactly what its nonlinearity adds.

> **In one line:** a *linear* autoencoder rediscovers PCA, and every advantage an
> autoencoder has over PCA comes from its nonlinear activation functions.

This repository accompanies the tutorial (`tutorial_autoencoder_vs_pca.pdf`) and contains
all the code needed to reproduce its figures from scratch.

## What it shows

1. A **linear** autoencoder trained with mean-squared error reaches the same reconstruction
   error as **PCA** (0.0153 vs 0.0152 at 32 dimensions)  a textbook confirmation of the
   Baldi & Hornik (1989) / Bourlard & Kamp (1988) result.
2. A **nonlinear** autoencoder beats PCA at every bottleneck size, with the largest gap
   under hard compression (≈ one-third lower error at 2 dimensions).
3. The autoencoder's 2-D latent space separates the clothing classes more cleanly than the
   first two principal components.



## How to run

# 1. (optional) create a virtual environment
python -m venv venv && source venv/bin/activate      # Windows: venv\Scripts\activate

# 2. install dependencies
pip install -r requirements.txt

# 3. launch the notebook
jupyter notebook autoencoder_vs_pca.ipynb


Run the cells top to bottom. The notebook downloads Fashion-MNIST automatically from the
dataset authors' GitHub mirror on the first run, trains every model, and regenerates all
four figures. Everything runs on a **CPU in roughly two minutes**  no GPU required.

## Accessibility

The figures are designed to be readable without relying on colour: each class in the
scatter plot has both a distinct colour (the colour-blind-safe Okabe–Ito palette) and a
distinct marker shape, and every figure is fully described in its caption in the PDF.

## References

- Baldi, P., & Hornik, K. (1989). *Neural networks and principal component analysis.*
  Neural Networks, 2(1), 53–58.
- Bourlard, H., & Kamp, Y. (1988). *Auto-association by multilayer perceptrons and SVD.*
  Biological Cybernetics, 59(4), 291–294.
- Hinton, G. E., & Salakhutdinov, R. R. (2006). *Reducing the dimensionality of data with
  neural networks.* Science, 313(5786), 504–507.
- Xiao, H., Rasul, K., & Vollgraf, R. (2017). *Fashion-MNIST.* arXiv:1708.07747.
- Goodfellow, I., Bengio, Y., & Courville, A. (2016). *Deep Learning*, Ch. 14. MIT Press.

## License

Released under the MIT License  see [`LICENSE`](LICENSE). You are free to use, modify and
share this material, including for your own teaching, with attribution.
