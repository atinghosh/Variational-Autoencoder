# Variational-Autoencoder
Contains code to learn variational autoencoder model on MNIST dataset using pytorch.

L = No. of monte carlo samples for gradient calculation

Gaussian loss is given by

![\Large \frac{1}{N}\sum_{i=1}^{N}\left[\frac{1}{L}\sum_{l=1}^{L}\left\{ \frac{1}{2}\sum_{j=1}^{784}\log(\sigma_{ij}^{(l)})^2 + \frac{1}{2}\sum_{j=1}^{784}\left(\frac{x_{ij}-\mu_{ij}^{(l)}}   {\sigma_{ij}^{(l)}}\right)^2 \right\} \right ]  - \frac{1}{N}\sum_{i=1}^{N}\left[ \sum_{j=1}^{J}\frac{1}{2}\left(1+\log(\sigma_j^{\prime(i)})^2-(\mu_j^{\prime(i)})^2 -(\sigma_j^{\prime(i)})^2\right )\right ]](https://latex.codecogs.com/svg.latex?%5Cfrac%7B1%7D%7BN%7D%5Csum_%7Bi%3D1%7D%5E%7BN%7D%5Cleft%5B%5Cfrac%7B1%7D%7BL%7D%5Csum_%7Bl%3D1%7D%5E%7BL%7D%5Cleft%5C%7B%20%5Cfrac%7B1%7D%7B2%7D%5Csum_%7Bj%3D1%7D%5E%7B784%7D%5Clog%28%5Csigma_%7Bij%7D%5E%7B%28l%29%7D%29%5E2%20&plus;%20%5Cfrac%7B1%7D%7B2%7D%5Csum_%7Bj%3D1%7D%5E%7B784%7D%5Cleft%28%5Cfrac%7Bx_%7Bij%7D-%5Cmu_%7Bij%7D%5E%7B%28l%29%7D%7D%20%7B%5Csigma_%7Bij%7D%5E%7B%28l%29%7D%7D%5Cright%29%5E2%20%5Cright%5C%7D%20%5Cright%20%5D%20-%20%5Cfrac%7B1%7D%7BN%7D%5Csum_%7Bi%3D1%7D%5E%7BN%7D%5Cleft%5B%20%5Csum_%7Bj%3D1%7D%5E%7BJ%7D%5Cfrac%7B1%7D%7B2%7D%5Cleft%281&plus;%5Clog%28%5Csigma_j%5E%7B%5Cprime%28i%29%7D%29%5E2-%28%5Cmu_j%5E%7B%5Cprime%28i%29%7D%29%5E2%20-%28%5Csigma_j%5E%7B%5Cprime%28i%29%7D%29%5E2%5Cright%20%29%5Cright%20%5D)


BCE loss is given by 

![\Large  \frac{1}{N}\sum_{i=1}^{N}\left[\frac{1}{L}\sum_{l=1}^{L}\left\{x_{ij}\log p_{ij}^{(l)} + (1-x_{ij})\log(1-\log p_{ij}^{(l)}) \right\} \right ]  - \frac{1}{N}\sum_{i=1}^{N}\left[ \sum_{j=1}^{J}\frac{1}{2}\left(1+\log(\sigma_j^{\prime(i)})^2-(\mu_j^{\prime(i)})^2 -(\sigma_j^{\prime(i)})^2\right )\right ]](https://latex.codecogs.com/svg.latex?%5Cfrac%7B1%7D%7BN%7D%5Csum_%7Bi%3D1%7D%5E%7BN%7D%5Cleft%5B%5Cfrac%7B1%7D%7BL%7D%5Csum_%7Bl%3D1%7D%5E%7BL%7D%5Cleft%5C%7Bx_%7Bij%7D%5Clog%20p_%7Bij%7D%5E%7B%28l%29%7D%20&plus;%20%281-x_%7Bij%7D%29%5Clog%281-%5Clog%20p_%7Bij%7D%5E%7B%28l%29%7D%29%20%5Cright%5C%7D%20%5Cright%20%5D%20-%20%5Cfrac%7B1%7D%7BN%7D%5Csum_%7Bi%3D1%7D%5E%7BN%7D%5Cleft%5B%20%5Csum_%7Bj%3D1%7D%5E%7BJ%7D%5Cfrac%7B1%7D%7B2%7D%5Cleft%281&plus;%5Clog%28%5Csigma_j%5E%7B%5Cprime%28i%29%7D%29%5E2-%28%5Cmu_j%5E%7B%5Cprime%28i%29%7D%29%5E2%20-%28%5Csigma_j%5E%7B%5Cprime%28i%29%7D%29%5E2%5Cright%20%29%5Cright%20%5D)
