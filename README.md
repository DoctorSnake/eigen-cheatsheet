# eigen-cheatsheet
A collection of useful things to know about eigen


Outline
- [Matrix Decompositions](#matrix-decompositions)
  - [SVD](#svd)
  - [QR](#qr)
  - [LU](#lu)
- [Least Square Problems](#least-square-problems)

## Matrix Decompositions

### SVD

```C++
Eigen::MatrixXd A(3, 2);
A << 4.2, 8.1,
     4.9, 11.3,
     2.1, 1.9;

Eigen::Vector3d B;
B << -4, -4, -4;

Eigen::BDCSVD<Eigen::MatrixXd> svd(A, Eigen::ComputeThinU | Eigen::ComputeThinV);
Eigen::MatrixXd U = svd.matrixU();
Eigen::MatrixXd V = svd.matrixV();
Eigen::MatrixXd S = svd.singularValues();

```

### QR

## Least Square Problems

```C++
// to solve the least square problem AX = B
Eigen::MatrixXd A(3, 2);
A << 4.2, 8.1,
     4.9, 11.3,
     2.1, 1.9;

Eigen::Vector3d B;
B << -4, -4, -4;

Eigen::BDCSVD<Eigen::MatrixXd> svd(A, Eigen::ComputeThinU | Eigen::ComputeThinV);
Eigen::Matrix2d X = svd.solve(B);

```
