# activation-function
# Non-Saturating Activation Functions

## Overview

In deep learning, activation functions play a crucial role in introducing non-linearity to neural networks, enabling them to learn complex patterns. However, traditional activation functions like sigmoid and tanh suffer from the "vanishing gradient" problem, especially in deep networks. Non-saturating activation functions address this issue by maintaining a non-zero gradient, even for large input values.

This README provides an overview of non-saturating activation functions, their benefits, and common examples.

## Problem: Vanishing Gradients

* **Definition:** The vanishing gradient problem occurs when the gradients of the loss function with respect to the network's parameters become extremely small during backpropagation. This makes it difficult for the network to learn, especially in deep architectures.
* **Cause:** Saturating activation functions, such as sigmoid and tanh, have gradients that approach zero as the input values become very large or very small.

## Solution: Non-Saturating Activation Functions

Non-saturating activation functions are designed to mitigate the vanishing gradient problem by maintaining a non-zero gradient for a wide range of input values.

## Benefits

* **Improved Training:** Non-saturating activation functions facilitate more efficient training, especially in deep neural networks.
* **Faster Convergence:** They allow for faster convergence of the network's parameters during training.
* **Reduced Vanishing Gradients:** They significantly reduce the likelihood of vanishing gradients, enabling the network to learn complex relationships.
* **Enhanced Performance:** Overall, they contribute to improved performance and accuracy of deep learning models.

## Common Examples

* **ReLU (Rectified Linear Unit):**
    * Formula: `ReLU(x) = max(0, x)`
    * Description: Outputs the input directly if it is positive, and zero otherwise.
    * Advantages: Simple, computationally efficient, and effective in mitigating vanishing gradients for positive inputs.
    * Potential Issue: "Dying ReLU" problem (neurons can become inactive).
* **Leaky ReLU:**
    * Formula: `LeakyReLU(x) = max(αx, x)` (where α is a small constant, e.g., 0.01)
    * Description: Similar to ReLU, but introduces a small slope for negative inputs.
    * Advantages: Addresses the "dying ReLU" problem.
* **Parametric ReLU (PReLU):**
    * Description: Similar to Leaky ReLU, but α is a learnable parameter, allowing the network to adapt the slope.
* **ELU (Exponential Linear Unit):**
    * Formula: `ELU(x) = x if x > 0, and α(e^x - 1) if x ≤ 0` (where α is a constant)
    * Description: Combines the benefits of ReLU and addresses the "dying ReLU" problem.
    * Advantages: Can push mean activations closer to zero.
* **Swish:**
    * Formula: `Swish(x) = x * sigmoid(βx)` (where β is a constant or learnable parameter)
    * Description: A newer activation function that has shown promising results in some tasks.
* **Mish:**
    * Formula: `Mish(x) = x * tanh(softplus(x))`
    * Description: A newer activation function that has shown to outperform ReLU in many deep learning tasks.

## Conclusion

Non-saturating activation functions are essential tools in deep learning for building efficient and effective neural networks. By addressing the vanishing gradient problem, they enable the training of deeper and more complex models.


##!
1. Sigmoid (Logistic):

Formula: σ(x) = 1 / (1 + e^(-x))
Description:
Outputs values between 0 and 1, making it useful for binary classification (probability).
Historically popular, but suffers from vanishing gradients, especially in deep networks.
Not zero-centered.
2. Tanh (Hyperbolic Tangent):

Formula: tanh(x) = (e^x - e^(-x)) / (e^x + e^(-x))
Description:
Outputs values between -1 and 1.
Zero-centered, which can be beneficial in some cases.
Also susceptible to vanishing gradients, though less so than sigmoid.
3. ReLU (Rectified Linear Unit):

Formula: ReLU(x) = max(0, x)
Description:
Outputs x if x is positive, and 0 otherwise.
Very popular due to its simplicity and efficiency.
Helps alleviate vanishing gradients for positive inputs.
Suffers from the "dying ReLU" problem (neurons can become inactive).
4. Leaky ReLU:

Formula: LeakyReLU(x) = max(αx, x) (where α is a small constant, e.g., 0.01)
Description:
Addresses the "dying ReLU" problem by allowing a small, non-zero gradient for negative inputs.
Helps improve learning in some cases.
5. Parametric ReLU (PReLU):

Description:
Similar to Leaky ReLU, but α is a learnable parameter.
Allows the network to adapt the slope for negative inputs.
6. ELU (Exponential Linear Unit):

Formula: ELU(x) = x if x > 0, and α(e^x - 1) if x ≤ 0 (where α is a constant)
Description:
Combines the benefits of ReLU and addresses the "dying ReLU" problem.
Can produce negative outputs, which can push mean activations closer to zero.
Tends to be more computationally expensive than ReLU.
7. SELU (Scaled Exponential Linear Unit):

Description:
A self-normalizing activation function.
Designed to produce outputs with zero mean and unit variance, which can help stabilize training.
Requires specific weight initialization.
8. Softmax:

Description:
Used in the output layer of multi-class classification networks.
Converts a vector of numbers into a probability distribution, where each element represents the probability of a class.
The sum of all output values will equal 1.
9. Softplus:

Formula: Softplus(x) = ln(1 + e^x)
Description:
A smooth approximation of ReLU.
Outputs positive values.
Less used than ReLU because it is more computationally intensive.
10. Gaussian:

Formula: g(x) = exp(-x^2)
Description:
Outputs a gaussian shape.
Less used than the others, but has some niche applications.
11. Swish:

Formula: Swish(x) = x * sigmoid(βx) (where β is a constant or learnable parameter)
Description:
A relatively new activation function that has shown promising results in some tasks.
Can perform better than ReLU in deep networks.
12. Mish:

Formula: Mish(x) = x * tanh(softplus(x))
Description:
Like Swish, it is a newer activation function, that has shown to outperform ReLU in many deep learning tasks.
Computationally more expensive than ReLU.

