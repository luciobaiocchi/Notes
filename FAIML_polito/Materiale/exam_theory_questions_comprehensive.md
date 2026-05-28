# ML/DL 2024-25 — Comprehensive Exam Theory Questions

> Original questions from `ML_DL 2024_25 - Exam Theory Questions v1_250513_004448.pdf` plus new sections for the four topics not covered in the original: Self-Supervised Learning & Generative Models, Federated Learning, Semantic Segmentation, and Reinforcement Learning.

---

## 1. Introduction to AI, Machine Learning & Probability

- List and briefly describe the three main ML paradigms.
- Describe the ML paradigm of supervised learning and give an example of a supervised learning algorithm presented during the course.
- Describe the difference between supervised and unsupervised ML algorithms.
- Describe the ML paradigm of unsupervised learning and give an example of an unsupervised learning algorithm presented during the course.
- Describe what a classification problem is, and make a simple binary classification example.
- Describe Bayes' Rule, its elements, and why it is useful. Name a classification algorithm whose formulation exploits Bayes' Rule.
- Illustrate the Naïve Bayes Classifier and its main assumption.
- Explain the Bias/Variance Decomposition Theorem seen during the course. No proof required.

---

## 2. Labs Overview (Data Preprocessing, Pipeline, Cross-Validation)

- Describe the key stages involved in a typical deep learning project workflow, from initial problem understanding to having a usable model. For each stage, briefly explain its main purpose.
- Before diving into data preprocessing for a deep learning project, explain three critical characteristics or potential issues related to your dataset that you should investigate.
- Explain why raw data, particularly images, generally requires preprocessing before being used to train a deep learning model. Describe at least two distinct common preprocessing steps and one data augmentation technique, outlining the specific purpose or benefit of each.
- Explain the rationale behind splitting a dataset into training, validation, and test sets in a machine learning project. Describe the distinct role and purpose of each of these sets.
- Describe the iterative process of training a deep learning model. Explain what fundamentally occurs during this training phase. What is the ultimate aim of training?
- What are hyperparameters in the context of designing and training deep learning models? Provide and discuss three distinct examples of common hyperparameters.
- The process of developing a successful deep learning model is often described as highly iterative, involving continuous "improving through experimentation." Explain what this "iterative nature" means in the practical context of a deep learning project.
- Explain why it would be highly problematic to directly use the test set for hyperparameter tuning. How can this issue be avoided when building a ML pipeline?

---

## 3. Learning Theory & Unsupervised Learning

- What is a loss function and why is its choice crucial when tackling a Machine Learning problem?
- Explain the concepts of True Risk and Empirical Risk. What is the goal of a learning algorithm in relation to them?
- Describe the core idea behind Probably Approximately Correct (PAC) learning. What do the "Probably" and "Approximately Correct" aspects refer to, and how do the parameters epsilon (ε) and delta (δ) relate to these concepts?
- Describe the Vapnik-Chervonenkis (VC) dimension of a hypothesis class. Explain the concept of "shattering" a set of points and how it is used to determine the VC dimension.
- Describe the phenomena of overfitting and underfitting. What does it mean for a model to overfit the training data, and how does this typically affect its performance on previously unseen examples?
- Explain the K-fold Cross Validation procedure for model selection. For which data regime (i.e., training set size) can it be particularly useful?
- Illustrate the key principles and step-by-step functioning of the Linear Regression algorithm.
- Illustrate the key principles and step-by-step functioning of the k-Means clustering algorithm.
- Illustrate the key principles and step-by-step functioning of the Gaussian Mixture Model.
- Illustrate the key principles and step-by-step functioning of the Expectation-Maximization (EM) algorithm.
- Illustrate the key principles and step-by-step functioning of the k-Nearest Neighbors classification algorithm.
- Describe the main advantages and disadvantages of the k-Nearest Neighbors (k-NN) algorithm. Explain why it is considered a non-parametric method and discuss its sensitivity to the choice of 'k' and feature scaling.

---

## 4. k-NN, Perceptron, Kernels, SVM, MLP

- Explain the Perceptron learning algorithm for binary classification. Describe its main components and the process of weights updating.
- What is the "Kernel Trick" in machine learning? Explain its purpose, particularly how it allows linear algorithms (like the Perceptron or SVM) to learn non-linear decision boundaries.
- Describe the basic architecture of a Multi-Layer Perceptron (MLP). Explain the role of hidden layers and non-linear activation functions in enabling MLPs to model complex relationships, overcoming the limitations of the single-layer Perceptron.
- Explain the core idea behind the Support Vector Machine (SVM) for linearly separable data (Hard Margin SVM). Describe what the "margin" is and why SVM aims to maximize it.
- Explain why the distance measure choice is crucial for the kNN algorithm. Make at least 3 examples of metrics.
- What is an Artificial Neural Network?
- Describe the Gradient Descent algorithm. How is it usually employed in Machine Learning?

---

## 5. Neural Networks, Backpropagation & Optimization

- What is the difference between the Gradient Descent and the Stochastic Gradient Descent algorithms?
- Describe the Stochastic Gradient Descent algorithm.
- Describe the backpropagation algorithm.
- Describe the concepts of batches, epochs, and learning rate within the context of optimization algorithms for ML.
- Explain and describe the concept of Momentum in the context of optimization methods for learning models.
- Describe the ADAM algorithm.
- Illustrate the key principles and step-by-step functioning of the Logistic Regression algorithm for binary classification.

---

## 6. Logistic Regression & Calibration

- Some classification methods also output a score that can be interpreted as a probability of predicted class membership. Define the property of a classifier being 'well-calibrated' with respect to its probabilistic outputs. Explain why this is an important property in certain domains and name a simple application example.
- A bank wants to predict whether a loan applicant is likely to default (Y=1) or not default (Y=0) on their loan. They have historical data including features like applicant income, credit score, loan amount, and employment duration, along with the actual outcome (defaulted or not). Explain which method between Logistic Regression or Linear Regression would be most suitable for this task and why.
- Explain the main problems or limitations of directly using standard Linear Regression for this binary classification task. How does Logistic Regression address these limitations, particularly concerning the range and interpretation of its output?
- Illustrate the Expected Calibration Error metric.
- Name and briefly describe one post-training classifier calibration method seen in class.

---

## 7. Introduction to Deep Learning (CNNs)

- What is a convolutional neural network? Describe the overall architecture and its main components, with a particular focus on convolutional layers.
- What is a convolutional neural network? Describe the overall architecture and its main components, with a particular focus on pooling layers.
- What is a convolutional neural network? Describe the overall architecture and its main components, with a particular focus on activation functions.
- What is a convolutional neural network? Describe the overall architecture and its main components; describe the training procedures and strategies with a particular focus on data preprocessing and weight initialization.
- What is a convolutional neural network? Describe the overall architecture and its main components; describe the training procedures and strategies with a particular focus on batch normalization.
- What is a convolutional neural network? Describe the overall architecture and its main components; describe the training procedures and strategies with a particular focus on transfer learning.
- What is a convolutional neural network? Describe the overall architecture and its main components; describe the training procedures and strategies with a particular focus on dropout regularization.

---

## 8. Deep Learning Architectures: AlexNet, VGG, ResNet, RNNs

- Describe the AlexNet architecture.
- Describe the VGG network architecture.
- Describe the Residual Network (ResNet) architecture.
- Describe the Recurrent Neural Network (RNN) architecture.
- Considering the AlexNet architecture, explain how the choice of the ReLU activation function and the use of dropout, combined with data augmentation, allowed to successfully train such a deep model on the large-scale ImageNet dataset. Which problems do these components address, and why were they particularly important for overcoming training difficulties?
- The VGG network demonstrated that significantly increasing network depth could lead to better performance on complex tasks like ImageNet classification. A key aspect of VGG was its highly uniform architecture, primarily relying on repeating stacks of small 3×3 convolutional filters and 2×2 pooling layers. What did the success of VGG suggest about the relationship between network depth and the ability to learn powerful visual representations?
- GoogLeNet (with its Inception modules) aimed to create deeper networks while being more computationally efficient. Explain the core idea behind the Inception module. Discuss the computational challenges this approach initially faced and how the use of 1×1 convolutions ("bottlenecks") helped manage this complexity and reduce the number of parameters.
- As networks got deeper post-VGG, researchers observed the "degradation" problem where simply stacking more layers hurt performance, even on the training set, indicating an optimization challenge rather than just overfitting. Explain this phenomenon. Describe the fundamental innovation introduced by ResNet and intuitively explain how this mechanism helps overcome the optimization difficulty and enables the training of much deeper networks more effectively.
- What is an LSTM?

---

## 9. From RNNs to Transformers

- What are the main differences between an RNN and a Transformer?
- Discuss the concept of attention and its implementation (general attention layer) in the context of RNNs and Transformers.
- Describe attention layers and self-attention layers, discussing similarities and differences.
- Describe self-attention layers and their masked and multi-head versions.
- Describe Transformers and their main components, with special focus on the encoder block.
- Describe Transformers and their main components, with special focus on the decoder block.

---

## 10. Self-Supervised Learning & Generative Models *(new — Lecture April 9)*

### Self-Supervised Learning

- What is self-supervised learning and how does it differ from supervised and unsupervised learning? Explain why it has become particularly important for training large-scale models.
- What is a "pretext task" in self-supervised learning? Describe at least two examples of pretext tasks used for visual representation learning and explain what invariances or structure each task forces the network to learn.
- Explain the concept of contrastive learning for self-supervised visual representation learning. What constitutes a "positive pair" and a "negative pair", and how does the contrastive loss encourage the model to learn useful representations?
- Describe the key idea behind CLIP (Contrastive Language-Image Pre-training). How does it leverage large-scale paired image-text data, and what downstream capabilities does the resulting model exhibit at test time?

### Generative Models — Overview

- What is a generative model? Explain the difference between an explicit density model and an implicit density model. Give one example of each type covered in the course.
- Describe the autoregressive approach to generative modelling (e.g., PixelCNN). Why is it classified as an explicit density model, and what is the main practical drawback of autoregressive generation?
- Compare and contrast Variational Autoencoders (VAE), Generative Adversarial Networks (GANs), and Diffusion Models as generative approaches. For each, indicate whether they use an explicit or implicit density, and summarise their main trade-offs in terms of sample quality, training stability, and inference cost.

### Variational Autoencoders (VAE)

- Describe the architecture of a Variational Autoencoder (VAE). How does it differ from a standard deterministic autoencoder, and what is the role of the stochastic latent variable z?
- Explain the Evidence Lower Bound (ELBO) used to train a VAE. Identify and explain the role of each term in the ELBO. Why is maximising the ELBO a principled objective for learning a generative model?
- Explain the reparameterization trick in VAEs. Why is it necessary for training with backpropagation, and how does it work?

### Generative Adversarial Networks (GANs)

- Describe the architecture of a Generative Adversarial Network (GAN). What are the roles of the generator and the discriminator, and how do they interact during training?
- Write and explain the minimax objective function of a GAN. What does the discriminator want to maximise, and what does the generator want to minimise? Describe what happens at the Nash equilibrium.
- Describe the practical training procedure for a GAN: explain why we alternate between gradient ascent on the discriminator and gradient ascent on the generator (the "non-saturating" variant), and what problem the non-saturating generator objective solves compared to the original minimax generator loss.
- What are the main pros and cons of GANs as generative models? Mention at least one active research direction used to improve GAN training stability (e.g., Wasserstein GAN, LSGAN).
- Explain the concept of a smooth latent space in GANs. What does it mean to interpolate between two latent vectors, and why is this considered evidence that the model has learned a meaningful representation?

### Diffusion Models

- Explain the core intuition behind diffusion (flow-based) generative models. What process is the model trained to invert, and what type of neural network is used to do so?
- Describe the Rectified Flow formulation for diffusion models. Write the training objective and describe the sampling procedure step-by-step.
- Explain what a Latent Diffusion Model (LDM) is. Why is it advantageous to perform the diffusion process in a compressed latent space rather than pixel space? How is the encoder/decoder pair trained, and why is a discriminator sometimes added?
- Describe Classifier-Free Guidance (CFG) for conditional generation with diffusion models. How is the model trained to function as both conditional and unconditional? How is the guidance weight w applied at inference time, and what is the computational cost of CFG?
- Why is the choice of noise schedule important in diffusion models? Explain why uniform sampling over noise levels is suboptimal and what solution is typically adopted (e.g., logit-normal sampling).
- Explain in what sense a diffusion model is a latent variable model, drawing an analogy to the VAE. What is the "score function" and how is it related to what a diffusion model implicitly learns?

---

## 11. Federated Learning *(new — Lecture April 13)*

- What is Federated Learning (FL)? Describe the key motivating scenario and explain how it differs from standard centralised machine learning training.
- Describe the FedAvg algorithm step-by-step. What operations are performed by each client, and how does the central server aggregate the local updates?
- What is the "data heterogeneity" (non-IID) problem in Federated Learning? Explain why it arises in practice and why it makes convergence of FedAvg more difficult compared to standard distributed learning with IID data.
- What is "client drift" in Federated Learning, and how does it degrade convergence under non-IID data distributions? Name one algorithmic technique proposed to mitigate it.
- Explain why communication efficiency is a critical concern in Federated Learning. Describe at least two strategies (e.g., local SGD steps, gradient compression, quantisation) used to reduce the communication overhead between clients and server.
- Even when model updates rather than raw data are shared, privacy is not fully guaranteed. Explain the gradient-inversion attack and why it demonstrates that sharing gradients can still leak private training data.
- Describe Differential Privacy (DP) and explain how it is applied to gradient updates in Federated Learning. What is the fundamental privacy-utility trade-off it introduces, and what two operations are typically performed on the gradients?
- Explain Secure Aggregation in Federated Learning. What does it allow the server to compute, and what information is kept hidden from the server and from other clients?
- What is the difference between Horizontal Federated Learning and Vertical Federated Learning? Give a concrete example of a real-world scenario where each approach is applicable.
- List and briefly describe at least three practical challenges of deploying Federated Learning in real-world systems (beyond data heterogeneity), such as stragglers, adversarial clients, or system heterogeneity.

---

## 12. Semantic Segmentation *(new — Lecture April 16)*

- Define the semantic segmentation task. How does it differ from image classification and from object detection in terms of the output it produces?
- Explain why a standard classification CNN (ending with fully-connected layers and a global softmax) cannot be directly used for dense per-pixel prediction. What architectural change introduced by Fully Convolutional Networks (FCN) enables dense prediction?
- After encoding image features at a low spatial resolution, the segmentation network must recover full-resolution predictions. Describe at least two upsampling techniques used in semantic segmentation (e.g., bilinear interpolation, transpose convolution, max-unpooling) and explain the trade-offs of each.
- Explain the concept of dilated (atrous) convolutions. How do they increase the receptive field of a convolutional filter without increasing the number of parameters or reducing spatial resolution, and why is this especially valuable for semantic segmentation?
- Describe the encoder-decoder architecture with skip connections as used in semantic segmentation networks. Why are skip connections important, and what problem do they address compared to a simple encoder-decoder without them?
- Describe the U-Net architecture. What are its key structural features, for which task was it originally designed, and why has it been widely adopted beyond its original application domain?
- What is the difference between semantic segmentation and instance segmentation? What additional capability does instance segmentation provide and why is it harder?
- What is panoptic segmentation? How does it unify semantic and instance segmentation, and what is the distinction between "stuff" and "things" categories?
- Explain the Intersection over Union (IoU) metric and its mean version (mIoU). Why is mIoU preferred over simple pixel accuracy when evaluating segmentation models on datasets with class imbalance?
- Describe at least one technique used to handle the class imbalance problem in semantic segmentation (e.g., weighted loss, oversampling), and explain why class imbalance is particularly severe in this task.

---

## 13. Reinforcement Learning *(new — Lectures April 20 & April 23)*

### Fundamentals & MDP

- Define the Reinforcement Learning (RL) problem. Describe the key components: agent, environment, state, action, reward, and policy. Explain the exploration vs. exploitation trade-off.
- What is a Markov Decision Process (MDP)? Define its formal components (S, A, P, R, γ) and explain the Markov property. Why is the MDP a natural framework for RL?
- Define the policy π(a|s) and distinguish between a deterministic and a stochastic policy. What does it mean for a policy to be "optimal"?
- Define the state-value function V^π(s) and the action-value function Q^π(s,a). Explain what each measures and how they are related to each other.
- Write and explain the Bellman Expectation Equation for V^π(s). How does it recursively relate the value of a state to the values of successor states?
- Define the optimal value function V*(s) and the optimal action-value function Q*(s,a). How can the optimal deterministic policy be recovered directly from Q*?
- Distinguish between model-based and model-free reinforcement learning. What does it mean to "have a model" of the environment, and give an example algorithm for each paradigm.

### Value-Based Methods & Deep Q-Networks

- Describe the Q-learning algorithm. Write the TD update rule, identify each component of the TD error (δ), and explain why Q-learning is considered an off-policy algorithm.
- Describe the SARSA algorithm. How does its update rule differ from Q-learning, and why is SARSA considered an on-policy algorithm?
- Describe the Deep Q-Network (DQN). What scalability limitation of tabular Q-learning motivated the use of a neural network? Describe the two key technical contributions of DQN — experience replay and target network — and explain the specific training instabilities that each one addresses.
- Explain experience replay in DQN. What transitions are stored in the replay buffer, why does uniform random sampling from the buffer improve stability, and what learning efficiency benefit does it provide?
- Explain the target network used in DQN. Why is using a separate, periodically frozen network to compute TD targets more stable than using the online network directly?
- Explain the difference between Monte Carlo (MC) and Temporal Difference (TD) methods for policy evaluation. Compare them in terms of bias, variance, data requirements (complete vs. partial episodes), and bootstrapping.

### Policy Gradient Methods

- What is a policy gradient method? Explain how it differs from value-based RL, and describe one advantage of directly optimising the policy parameters θ (e.g., natural handling of continuous or stochastic action spaces).
- Describe the REINFORCE algorithm (Monte Carlo policy gradient). Write the policy gradient estimate, explain the role of each term (∇_θ log π_θ(s,a) and the return G_t), and identify the main practical limitation of the algorithm.
- Explain why the policy gradient estimator has high variance. What practical techniques — such as subtracting a baseline or using larger batches — can reduce variance, and why does a baseline not introduce bias?
- Describe the Actor-Critic architecture. What are the separate roles of the actor and the critic, and how does the critic reduce the variance of the policy gradient compared to REINFORCE?
- Define the advantage function A^π(s,a) = Q^π(s,a) − V^π(s). Why is weighting the policy gradient by the advantage rather than Q alone a variance-reduction technique?
- List the main equivalent forms of the policy gradient (REINFORCE, Q Actor-Critic, Advantage Actor-Critic, TD Actor-Critic, TD(λ) Actor-Critic, Natural Actor-Critic). For each, briefly state what quantity is used as the gradient weight and describe the bias-variance trade-off compared to REINFORCE.
- Explain the key practical characteristics of policy gradient methods: why is it on-policy by default (and how can an off-policy variant be achieved via importance sampling)? Why do gradients tend to be noisy, and what optimisation considerations does this imply?

### Advanced Policy Optimisation (TRPO & PPO)

- What problem motivates Trust Region Policy Optimization (TRPO)? Explain what a "trust region" is in this context and describe the KL-divergence constraint that TRPO imposes on the policy update.
- Write the surrogate objective and the KL constraint used in TRPO. Describe the optimisation algorithm used to solve the constrained problem and explain why naive gradient ascent without a trust region can cause catastrophic performance collapse.
- Describe Proximal Policy Optimization (PPO). How does it approximate the TRPO constraint in a simpler, computationally cheaper way using a clipped surrogate objective J^CLIP? What is the role of the clipping parameter ε, and what is the key difference from TRPO in terms of implementation?
- Compare TRPO and PPO: which provides stronger theoretical guarantees, and which is more widely used in practice? Explain the trade-off.

### RL in the Real World

- Describe the sim-to-real transfer problem in robotics RL. Why is training exclusively in simulation appealing, and what is the key challenge when deploying a simulation-trained policy on real hardware? What is domain randomisation and how does it help?
- Explain "reward specification" as a fundamental challenge in real-world RL. Why is it difficult to define a reward function for complex tasks, and what can go wrong when the reward is mis-specified (reward hacking)?
