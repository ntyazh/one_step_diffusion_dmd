# one_step_diffusion_dmd
The final project of an university course "Generative models based on diffusions". It was a team assignment, I was responsible for implementation of the all loss functions and the training algorithm.
The task was to implement the [Distribution Matching Distillation paper](https://arxiv.org/abs/2311.18828) method. The point is that, as we know, a trained diffusion model generates a new image be solving ODE. As we can't find an exact solution of the ODE, we discretize it using various schemes (e.g. Euler scheme or Heun's method) with some number of discretization steps. The problem is that each of these steps requires the neural network inference that can be slow and computionally expensive. The paper suggests a procedure of diffusion model distillation into a one-step image generator with minimal impact on image quality.
We conducted all the experiments on the CIFAR-10 dataset and got the following FIDs (on 8700 samples):
Teacher model (500 generation steps, heun sampler) FID: 8.3
Student model (1 generation step) FID: 15
Considering computational resources limitations, that's not so bad result. However, you can find much more information about our results in dmd_report.
