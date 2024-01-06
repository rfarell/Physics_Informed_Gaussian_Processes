# Physics Informed Gaussian Processes (PIGP)

## Overview
Physics Informed Gaussian Processes (PIGP) represent a novel approach in machine learning, combining traditional Gaussian Processes (GPs) with physical knowledge. This project explores the integration of known functional forms into GP models, enhancing the prediction accuracy and generalizability in noisy data environments.

## Motivation
In scenarios with noisy observational data, standard Gaussian Process models may struggle with overfitting and calibration. By embedding known physical laws or functional forms into the GP framework, we aim to regularize the learning process. This approach not only aligns the posterior mean with the known functions but also addresses challenges in kernel expressiveness and overfitting.

## Methodology

### Gaussian Processes with Noisy Data
We begin by modeling the noisy observational data using Gaussian Processes. This standard approach forms the basis for our further enhancements.

### Incorporating Known Functional Forms
The core of our methodology lies in integrating explicit or implicit known functional forms into the GP model. This integration is achieved by adding an L2 loss term to the GP's mean, acting as a powerful regularizer. It ensures that the posterior mean aligns with the known functional form, leading to better calibrated models.

### Addressing Kernel Expressiveness and Overfitting
A critical challenge we face is ensuring that the kernel is expressive enough to match the underlying physics or true functional form. Our solution involves learning the mean function of the GP, rather than assuming it to be zero. This approach, detailed in our notebook "Physics_Informed_GP_2D_Burgers_PDE_with_NN_Mean", demonstrates the effectiveness of this strategy. However, it also revealed a tendency to overfit, resulting in an excessively tight posterior variance. To counter this, we introduced additional derivative loss terms into the loss function.

## Demonstrations and Results
Our methodology has been tested and demonstrated through various problems:
- 1D and 2D toy problems
- Burger's equation in one spatial and one temporal dimension

Each case study provided insights into the efficacy of our approach and the challenges encountered.

## Future Plans
Moving forward, we aim to:
1. Explore more expressive kernels to enhance model flexibility.
2. Develop advanced regularization techniques for the high-capacity mean function by incorporating additional derivative terms into the loss function.

## Colab Notebooks
To facilitate a practical understanding, we provide Colab notebooks for hands-on experience:
- [Derivative_Informed_GP_1D_Toy_Problem](https://colab.research.google.com/github/rfarell/Physics_Informed_Gaussian_Processes/blob/main/notebooks/Derivative_Informed_GP_1D_Toy_Problem.ipynb): Explore the application of PIGP in a 1D toy problem.
- [Derivative_Informed_GP_2D_Toy_Problem](https://colab.research.google.com/github/rfarell/Physics_Informed_Gaussian_Processes/blob/main/notebooks/Derivative_Informed_GP_2D_Toy_Problem.ipynb): A 2D toy problem demonstration.
- [Physics_Informed_GP_2D_Burgers_PDE](https://colab.research.google.com/github/rfarell/Physics_Informed_Gaussian_Processes/blob/main/notebooks/Physics_Informed_GP_2D_Burgers_PDE.ipynb): Application to the Burger's equation in a 2D setting.
- [Physics_Informed_GP_2D_Burgers_PDE_with_NN_Mean](https://colab.research.google.com/github/rfarell/Physics_Informed_Gaussian_Processes/blob/main/notebooks/Physics_Informed_GP_2D_Burgers_PDE_with_NN_Mean.ipynb): Advanced exploration with a neural network mean function in the context of the Burger's equation.
- [SSGP_Overview_Pendulum](https://colab.research.google.com/github/rfarell/Physics_Informed_Gaussian_Processes/blob/main/notebooks/SSGP_Overview_Pendulum.ipynb): Symplectic Spectrum Gaussian Processes from [this code](https://github.com/yusuk-e/SSGP).


## Conclusion
PIGP represents a significant step forward in combining machine learning with physical understanding. By embedding known physical laws into Gaussian Processes, we enhance the model's ability to handle noisy data, thereby opening new avenues in scientific modeling and prediction.


<!-- 
### Colab Reduced Order Modeling Tutorials
- 📔 [Derivative_Informed_GP_1D_Toy_Problem](https://colab.research.google.com/github/rfarell/Physics_Informed_Gaussian_Processes/blob/main/notebooks/Derivative_Informed_GP_1D_Toy_Problem.ipynb)
- 📔 [Derivative_Informed_GP_2D_Toy_Problem](https://colab.research.google.com/github/rfarell/Physics_Informed_Gaussian_Processes/blob/main/notebooks/Derivative_Informed_GP_2D_Toy_Problem.ipynb)
- 📔 [Physics_Informed_GP_2D_Burgers_PDE](https://colab.research.google.com/github/rfarell/Physics_Informed_Gaussian_Processes/blob/main/notebooks/Physics_Informed_GP_2D_Burgers_PDE.ipynb)
- 📔 [Physics_Informed_GP_2D_Burgers_PDE_with_NN_Mean](https://colab.research.google.com/github/rfarell/Physics_Informed_Gaussian_Processes/blob/main/notebooks/Physics_Informed_GP_2D_Burgers_PDE_with_NN_Mean.ipynb)


## Tasks
- Compare Matérn, Spectral, Squared Exponential, and RBF kernels
- Learn the mean function of the GP for better derivative matching. My hypothesis is that this is a better approach than using more expressive kernels. Compare the performance of the GP with and without the mean function.
- Use Stochastic Sparse Variational Gaussian Processes with Multiple Outputs.
 -->
