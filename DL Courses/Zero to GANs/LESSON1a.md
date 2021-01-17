# Lesson 1 (part 1) - PyTorch Basics and Gradient Descent

**What we will learn:**  
⇒ Introductions to PyTorch tensors  
⇒ Tensor operations and gradients  
⇒ Interoperability between PyTorch and Numpy  
⇒ How to use the PyTorch documentation site  

---

**Table of Contents**
- Tensors
- Tensor Operations and Gradients
- Tensor Functions
- Interoperability with Numpy
- Further Reading

---

## Tensors

```python
# from [PyTorch website](https://pytorch.org/tutorials/beginner/nlp/pytorch_tutorial.html)

# Creates a vector
V = torch.tensor([1., 2., 3.])
print(V)

# Creates a matrix
M = torch.tensor([[1., 2., 3.], [4., 5., 6]])
print(M)

# Create a 3D tensor of size 2x2x2.
T = torch.tensor([[[1., 2.], [3., 4.]],
          [[5., 6.], [7., 8.]]])
print(T)
```

We can check the `dtype` attribute of any tensor.

We can inspect the length along each dimension using the `.shape` property of a tensor.
Note that it's not possible to create tensors with an improper shape (`ValueError`) . 

- Trick: start with the outer most bracket, then count the number of elements one bracket in etc

## Tensor Operations and Gradients

```python
# Create tensors.
x = torch.tensor(3.)
w = torch.tensor(4., requires_grad=True)
b = torch.tensor(5., requires_grad=True)
x, w, b

# Arithmetic operations
y = w * x + b
y
# OUTPUT: tensor(17., grad_fn=<AddBackward0>)
```

The `requires_grad` is a feature of PyTorch, called *autograd* (automatic gradients).

```python
# Compute derivatives
y.backward()

# Display gradients
print('dy/dx:', x.grad)
print('dy/dw:', w.grad)
print('dy/db:', b.grad)
"""
OUTPUT

dy/dx: None
dy/dw: tensor(3.)
dy/db: tensor(1.)
"""
```

Note: The "grad" in w.grad is short for *gradient*, which is another term for derivative. The term *gradient* is primarily used while dealing with vectors and matrices.

## Tensor Functions

```python
# Create a tensor with a fixed value for every element
t6 = torch.full((3, 2), 42)
t6
"""
tensor([[42, 42],
        [42, 42],
        [42, 42]])
"""

# Concatenate two tensors with compatible shapes
t7 = torch.cat((t3, t6))
t7
"""
tensor([[ 5.,  6.],
        [ 7.,  8.],
        [ 9., 10.],
        [42., 42.],
        [42., 42.],
        [42., 42.]])
"""

# Compute the sin of each element
t8 = torch.sin(t7)
t8
"""
tensor([[-0.9589, -0.2794],
        [ 0.6570,  0.9894],
        [ 0.4121, -0.5440],
        [-0.9165, -0.9165],
        [-0.9165, -0.9165],
        [-0.9165, -0.9165]])
"""

# Change the shape of a tensor
t9 = t8.reshape(3, 2, 2)
t9
"""
tensor([[[-0.9589, -0.2794],
         [ 0.6570,  0.9894]],

        [[ 0.4121, -0.5440],
         [-0.9165, -0.9165]],

        [[-0.9165, -0.9165],
         [-0.9165, -0.9165]]])
"""
```

You can learn more about tensor operations here: [https://pytorch.org/docs/stable/torch.html](https://pytorch.org/docs/stable/torch.html) .

## Interoperability with Numpy

<details>
  <summary>About Numpy</summary>
  
  It enables efficient operations on large multi-dimensional arrays and has a vast ecosystem of supporting libraries, including:

  - [Pandas](https://jovian.ai/outlink?url=https%3A%2F%2Fpandas.pydata.org%2F) for file I/O and data analysis
  - [Matplotlib](https://jovian.ai/outlink?url=https%3A%2F%2Fmatplotlib.org%2F) for plotting and visualization
  - [OpenCV](https://jovian.ai/outlink?url=https%3A%2F%2Fopencv.org%2F) for image and video processing
</details>

tutorial series: [https://jovian.ai/aakashns/python-numerical-computing-with-numpy](https://jovian.ai/aakashns/python-numerical-computing-with-numpy) 

```python
import numpy as np

x = np.array([[1, 2], [3, 4.]])
x

# Convert the numpy array to a torch tensor.
y = torch.from_numpy(x)
y

# Convert a torch tensor to a numpy array
z = y.numpy()
z
```

Torch Tensors and Numpy Arrays don't have the same data types (e.g. float64 are interpreted differently), but they are very similar.

There are two main reasons why we use PyTorch:

1. **Autograd**: The ability to automatically compute gradients for tensor operations is essential for training deep learning models.
2. **GPU support**: While working with massive datasets and large models, PyTorch tensor operations can be performed efficiently using a Graphics Processing Unit (GPU). Computations that might typically take hours can be completed within minutes using GPUs.

## Further Reading

[https://github.com/yunjey/pytorch-tutorial](https://github.com/yunjey/pytorch-tutorial)
