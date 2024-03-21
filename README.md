import numpy as np

def lagrange_basis(x, xi):

    return np.prod([(x - xj) / (xi - xj) for j, xj in enumerate(x) if xj != xi], axis=0)

def lagrange_interpolation(x, y, xi):

    return sum(yi * lagrange_basis(xi, xj) for xj, yi in zip(x, y))

