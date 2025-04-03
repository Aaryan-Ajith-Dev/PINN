# Physics-Informed Neural Networks (PINNs) Results  

## Overview  
This repository contains the results of two experiments conducted using Physics-Informed Neural Networks (PINNs):  
1. **With Data** (Residual Connections)  
2. **Without Data** (IDPINN)  

The experiments were implemented in a Colab notebook, and this README provides details about the methodology, results, and observations.

---

## Methodology  
### 1. With Data (Residual Connections)  
- The model used is a simple neural network with 4 hidden layers of constant size
- A skip connection was used in the last layer to help reduce vanishing gradients
- The loss function is a weighted sum of the physics loss, data loss and the initial condition loss (initial position and velocity)

### 2. Without Data (IDPINN)  
- Attempts were made with a single neural network but it would struggle against local optimas, hence preventing any furthur updates. To combat this, the time domain of the system was divided into a bunch of disjoint intervals and a weak learner (smaller PINN) was trained on each one of these intervals. The initial constriaint loss of the current PINN was obtained by the prediction results of the previous PINN (if it was the first, then we would use the given conditions.)
- Here the loss function is a weighted sum of the physics loss and the initial conditions loss.
---

## Results  
### Visualizations  
#### With Data (Residual Connections)  
![Insert Image Here](WithData/e=0.1)
![Insert Image Here](WithData/e=0.2)

#### Without Data (IDPINN)  
![Insert Image Here](WithoutData/e=0.2)  

---

## Observations  
- [Discuss key takeaways from the results.]  
- [Mention which method performed better and why.]  
- [Highlight any challenges faced during training.]  

---

## Reproducibility  
- The full implementation is available in [Colab Notebook](https://colab.research.google.com/drive/1XXCkKBiteo_5oYnH2E0-zTPanlBAvOTn?usp=sharing).  
- To reproduce the results, follow these steps:  
  1. Open the Colab notebook.  
  2. Run all cells sequentially.  
  3. Modify hyperparameters as needed for experimentation.  
