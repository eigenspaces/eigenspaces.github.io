---
layout: post
title: Hello world!
---
Hi!  


```python
def norm_pdf(X, mu, C):
    d = mu.size

    if np.linalg.matrix_rank(C) < d:
        raise ValueErro('Covariance matrix must be non-singular')

    X_cen = X - mu

    term1 = 1 / (np.sqrt(np.linalg.det(C) * (2 * np.pi) ** d))
    term2 = np.exp(-0.5 * np.sum(np.linalg.solve(C, X_cen.T).T * X_cen, axis=1))

    y = term1 * term2

    return y
```
