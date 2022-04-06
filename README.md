# aiaru
from numpy import *
from sympy import *
matrice = random.randint(0, 10, (2, 4))
print(matrice)

t = shape(matrice)


def minor(matrice, row, col):
    minor = []
    for i in range(len(matrice)):
        if i != row:
            minor.append([])
            for j in range(len(matrice)):
                if j != col:
                    minor[-1].append(matrice[i][j])
    return minor


def determinant(matrice):
    if t[0] != t[1]:
        print("Error")
    if len(matrice) == 1:
        return matrice[0][0]
    if len(matrice) == 2:
        return matrice[0][0] * matrice[1][1] - matrice[0][1] * matrice[1][0]
    else:
        det = 0
        for i in range(len(matrice)):
            det += (-1) ** i * matrice[0][i] * \
                determinant(minor(matrice, 0, i))
        return det


print(determinant(matrice))

