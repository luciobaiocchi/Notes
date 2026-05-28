# ML/DL 2024-25 — Comprehensive Exam Theory Answers

> Answers to all questions in `exam_theory_questions_comprehensive.md`.

---

## 1. Introduction to AI, Machine Learning & Probability

1. **Q:** List and briefly describe the three main ML paradigms.  
   **A:** **Supervised learning** learns mappings from labeled data, **unsupervised learning** discovers structure in unlabeled data, and **reinforcement learning** learns a policy by interacting with an environment to maximize reward.
2. **Q:** Describe the ML paradigm of supervised learning and give an example of a supervised learning algorithm presented during the course.  
   **A:** Supervised learning trains on input–output pairs to predict labels. Examples include linear regression, logistic regression, SVMs, or CNN classifiers.
3. **Q:** Describe the difference between supervised and unsupervised ML algorithms.  
   **A:** Supervised methods require labels and optimize prediction error; unsupervised methods have no labels and aim to uncover structure (clusters, density, representations).
4. **Q:** Describe the ML paradigm of unsupervised learning and give an example of an unsupervised learning algorithm presented during the course.  
   **A:** Unsupervised learning models the structure or distribution of data without labels. Examples: k-Means, GMM, PCA.
5. **Q:** Describe what a classification problem is, and make a simple binary classification example.  
   **A:** Classification assigns discrete labels to inputs. Binary example: classify emails as spam vs. not spam.
6. **Q:** Describe Bayes' Rule, its elements, and why it is useful. Name a classification algorithm whose formulation exploits Bayes' Rule.  
   **A:** Bayes' Rule: \(P(y|x)=\frac{P(x|y)P(y)}{P(x)}\). It combines likelihood and prior to compute posterior class probabilities. Naive Bayes uses it directly.
7. **Q:** Illustrate the Naive Bayes Classifier and its main assumption.  
   **A:** Naive Bayes assumes conditional independence of features given the class, so \(P(x|y)=\prod_i P(x_i|y)\). It predicts the class with maximum posterior.
8. **Q:** Explain the Bias/Variance Decomposition Theorem seen during the course. No proof required.  
   **A:** Expected error decomposes into **bias²** (systematic error), **variance** (sensitivity to data), and **noise**. High bias underfits; high variance overfits.

---

## 2. Labs Overview (Data Preprocessing, Pipeline, Cross-Validation)

1. **Q:** Describe the key stages involved in a typical deep learning project workflow, from initial problem understanding to having a usable model.  
   **A:** Problem definition → data collection/labeling → exploratory analysis → preprocessing/augmentation → train/val/test split → model selection → training → validation & tuning → final evaluation → deployment/monitoring.
2. **Q:** Before diving into data preprocessing, explain three critical characteristics or potential issues to investigate.  
   **A:** Dataset size/coverage, class imbalance, label quality/noise, missing values/outliers, duplicates/leakage, and distribution shifts.
3. **Q:** Explain why raw data requires preprocessing and give at least two preprocessing steps and one augmentation technique.  
   **A:** Preprocessing standardizes inputs and improves learning stability. Steps: resize/crop, normalize/standardize, encode labels. Augmentation: flips/rotations/color jitter to improve generalization.
4. **Q:** Explain the rationale behind splitting a dataset into training, validation, and test sets.  
   **A:** Training fits parameters, validation tunes hyperparameters/early stopping, and test provides an unbiased final estimate of generalization.
5. **Q:** Describe the iterative process of training a deep learning model. What is the ultimate aim of training?  
   **A:** Forward pass → compute loss → backpropagate gradients → update weights. Iterated over epochs to minimize loss and generalize to unseen data.
6. **Q:** What are hyperparameters? Provide and discuss three distinct examples.  
   **A:** Hyperparameters are set before training (not learned). Examples: learning rate, batch size, number of layers/units, weight decay, dropout rate.
7. **Q:** Explain the "iterative nature" of developing successful deep learning models.  
   **A:** You repeatedly experiment with data, architecture, and hyperparameters, evaluate on validation data, analyze errors, and refine the pipeline.
8. **Q:** Why is using the test set for hyperparameter tuning problematic? How can this issue be avoided?  
   **A:** It leaks information and overestimates performance. Use a validation set or cross-validation; keep the test set for final evaluation.

---

## 3. Learning Theory & Unsupervised Learning

1. **Q:** What is a loss function and why is its choice crucial?  
   **A:** It quantifies prediction error and defines the optimization objective. The choice affects convergence, robustness, and alignment with task goals.
2. **Q:** Explain True Risk and Empirical Risk. What is the goal of a learning algorithm?  
   **A:** True risk is expected loss over the data distribution; empirical risk is average loss on training data. Learning aims to minimize true risk (often via empirical risk + regularization).
3. **Q:** Describe PAC learning and the role of ε and δ.  
   **A:** PAC guarantees that with probability ≥ \(1-δ\), the learned hypothesis has error ≤ \(ε\). \(ε\) is the error tolerance (approximation bound); \(δ\) is the failure probability, so \(1-δ\) is the confidence level.
4. **Q:** Describe VC dimension and the concept of shattering.  
   **A:** VC dimension is the largest number of points that can be labeled in all possible ways by a hypothesis class. Shattering those points indicates its capacity.
5. **Q:** Describe overfitting and underfitting.  
   **A:** Overfitting: low training error but high test error due to memorization. Underfitting: high errors on both due to an overly simple model.
6. **Q:** Explain K-fold Cross Validation and when it is useful.  
   **A:** Split data into k folds; train on k-1, validate on 1; average results. Especially useful for small datasets.
7. **Q:** Illustrate the Linear Regression algorithm.  
   **A:** Model \(y=w^T x+b\), minimize MSE, solve via normal equation \((X^T X)^{-1} X^T y\) or gradient descent.
8. **Q:** Illustrate the k-Means clustering algorithm.  
   **A:** Initialize centroids, assign each point to nearest centroid, recompute centroids as means, iterate to minimize within-cluster SSE.
9. **Q:** Illustrate the Gaussian Mixture Model.  
   **A:** Models data as a weighted sum of Gaussians; assigns soft probabilities to clusters; parameters estimated with EM.
10. **Q:** Illustrate the Expectation-Maximization (EM) algorithm.  
    **A:** E-step computes expected latent variables (responsibilities); M-step maximizes expected log-likelihood; repeat to increase likelihood.
11. **Q:** Illustrate the k-Nearest Neighbors classification algorithm.  
    **A:** Store data; for a new point compute distances, select k nearest neighbors, vote to predict the label.
12. **Q:** Describe main advantages/disadvantages of k-NN and its sensitivity to k and feature scaling.  
    **A:** Advantages: simple, flexible, non-parametric. Disadvantages: slow inference, memory heavy, sensitive to noise, k choice, and feature scaling.

---

## 4. k-NN, Perceptron, Kernels, SVM, MLP

1. **Q:** Explain the Perceptron learning algorithm.  
   **A:** Linear classifier \(y=\text{sign}(w\cdot x+b)\). On misclassification, update \(w \leftarrow w + \eta y x\), \(b \leftarrow b + \eta y\).
2. **Q:** What is the Kernel Trick and why is it useful?  
   **A:** Replace dot products with a kernel \(K(x,x')=\phi(x)\cdot\phi(x')\) to learn nonlinear decision boundaries without explicitly mapping to high dimensions.
3. **Q:** Describe the basic architecture of an MLP.  
   **A:** A feedforward network with input, hidden, and output layers. Nonlinear activations in hidden layers enable complex function approximation.
4. **Q:** Explain the core idea behind the hard-margin SVM.  
   **A:** Find a hyperplane that maximizes the margin to the closest points (support vectors), improving generalization.
5. **Q:** Why is the distance measure crucial for kNN? Give examples.  
   **A:** It defines neighborhood similarity. Common metrics: Euclidean, Manhattan, Minkowski, cosine, Mahalanobis, Hamming.
6. **Q:** What is an Artificial Neural Network?  
   **A:** A network of interconnected units with weighted edges and nonlinear activations that approximates functions.
7. **Q:** Describe the Gradient Descent algorithm and its use in ML.  
   **A:** Iteratively update parameters \(w \leftarrow w - \eta \nabla L(w)\) to minimize a loss; used to train most ML models.

---

## 5. Neural Networks, Backpropagation & Optimization

1. **Q:** Difference between Gradient Descent and Stochastic Gradient Descent?  
   **A:** GD uses the full dataset per update; SGD uses one sample or mini-batch, making it faster and noisier but more scalable.
2. **Q:** Describe the SGD algorithm.  
   **A:** Shuffle data, sample mini-batches, compute gradients, update weights; repeat over epochs.
3. **Q:** Describe backpropagation.  
   **A:** Use chain rule to compute gradients of the loss with respect to each weight, propagating error from output to input.
4. **Q:** Explain batches, epochs, and learning rate.  
   **A:** Batch: samples per update; epoch: one full dataset pass; learning rate: step size for parameter updates.
5. **Q:** Explain Momentum.  
   **A:** Accumulates a velocity vector \(v\) as an exponential average of gradients to speed up convergence and reduce oscillations.
6. **Q:** Describe the ADAM algorithm.  
   **A:** Combines momentum and adaptive learning rates by tracking first and second moments of gradients with bias correction.
7. **Q:** Illustrate Logistic Regression for binary classification.  
   **A:** Model \(p(y=1|x)=\sigma(w\cdot x+b)\); train by maximizing log-likelihood or minimizing cross-entropy.

---

## 6. Logistic Regression & Calibration

1. **Q:** Define a well-calibrated classifier and why it matters.  
   **A:** For predictions with probability \(p\), accuracy should be ≈ \(p\). This is critical in risk-sensitive domains like medicine or finance.
2. **Q:** Logistic vs. Linear Regression for loan default prediction?  
   **A:** Logistic regression is appropriate because it models a binary outcome and outputs probabilities in \([0,1]\).
3. **Q:** Problems with Linear Regression for classification and how Logistic Regression fixes them.  
   **A:** Linear regression outputs unbounded values and assumes Gaussian errors; logistic regression uses a sigmoid and log-loss for Bernoulli data.
4. **Q:** Illustrate Expected Calibration Error (ECE).  
   **A:** Bin predictions by confidence, compute \(\sum_b \frac{|B_b|}{n}|\text{acc}(B_b)-\text{conf}(B_b)|\).
5. **Q:** Name one post-training calibration method.  
   **A:** Platt scaling (fit a sigmoid to logits), temperature scaling, or isotonic regression.

---

## 7. Introduction to Deep Learning (CNNs)

1. **Q:** CNN architecture with focus on convolutional layers.  
   **A:** Convolutional layers apply learnable filters to local receptive fields, producing feature maps with weight sharing and translation equivariance.
2. **Q:** CNN architecture with focus on pooling layers.  
   **A:** Pooling (max/avg) down-samples feature maps, reducing computation and adding local invariance.
3. **Q:** CNN architecture with focus on activation functions.  
   **A:** Nonlinearities like ReLU/Leaky ReLU follow convolutions to enable complex feature learning and mitigate vanishing gradients.
4. **Q:** CNN training with focus on preprocessing and weight initialization.  
   **A:** Normalize/standardize images, resize/crop, augment data; initialize weights with Xavier/He to stabilize gradient flow.
5. **Q:** CNN training with focus on batch normalization.  
   **A:** BatchNorm normalizes activations per batch and learns scale/shift, stabilizing training and enabling higher learning rates.
6. **Q:** CNN training with focus on transfer learning.  
   **A:** Use pretrained weights, freeze early layers, and fine-tune later layers for new tasks, especially with limited data.
7. **Q:** CNN training with focus on dropout regularization.  
   **A:** Randomly drop units during training to reduce co-adaptation and overfitting; use full network at inference with scaled activations.

---

## 8. Deep Learning Architectures: AlexNet, VGG, ResNet, RNNs

1. **Q:** Describe the AlexNet architecture.  
   **A:** 5 convolutional layers with ReLU and max-pooling followed by 3 fully connected layers with dropout and LRN; trained on GPUs.
2. **Q:** Describe the VGG network architecture.  
   **A:** Very deep (16/19) network using stacks of 3×3 convolutions and 2×2 max-pooling; uniform and simple design.
3. **Q:** Describe the Residual Network (ResNet) architecture.  
   **A:** Deep networks built from residual blocks with skip connections that add inputs to outputs, enabling very deep training.
4. **Q:** Describe the Recurrent Neural Network (RNN) architecture.  
   **A:** Processes sequences with recurrent connections; maintains a hidden state \(h_t=f(h_{t-1},x_t)\).
5. **Q:** Explain why ReLU, dropout, and data augmentation were crucial for AlexNet.  
   **A:** ReLU speeds training and reduces vanishing gradients, dropout regularizes fully connected layers, and augmentation enlarges the dataset to curb overfitting.
6. **Q:** Explain what VGG’s success suggests about network depth.  
   **A:** Increasing depth with small filters improves representation power and accuracy, showing depth is a key driver of performance.
7. **Q:** Explain the Inception module and 1×1 bottlenecks.  
   **A:** Inception combines parallel 1×1, 3×3, 5×5 convolutions and pooling; 1×1 bottlenecks reduce channels, cutting computation and parameters.
8. **Q:** Explain the ResNet solution to degradation.  
   **A:** Residual connections allow identity mappings and better gradient flow, making deeper networks easier to optimize.
9. **Q:** What is an LSTM?  
   **A:** A gated RNN with cell state and input/forget/output gates that preserves long-term dependencies.

---

## 9. From RNNs to Transformers

1. **Q:** Main differences between an RNN and a Transformer?  
   **A:** RNNs process sequentially with recurrence; Transformers use self-attention with full parallelism and better long-range dependency modeling.
2. **Q:** Describe attention and its use in RNNs and Transformers.  
   **A:** Attention computes weighted sums of values based on query–key similarity. In RNNs it connects decoder queries to encoder states; in Transformers it is the core mechanism.
3. **Q:** Attention vs. self-attention.  
   **A:** Attention uses queries from one sequence and keys/values from another; self-attention uses the same sequence for Q, K, V.
4. **Q:** Describe masked and multi-head self-attention.  
   **A:** Masked self-attention blocks future positions for autoregressive decoding. Multi-head splits attention into parallel subspaces to capture diverse relations.
5. **Q:** Transformer encoder components.  
   **A:** Multi-head self-attention → feed-forward network, with residual connections, layer normalization, and positional encodings.
6. **Q:** Transformer decoder components.  
   **A:** Masked self-attention → encoder–decoder attention → feed-forward network, each with residuals and layer norms.

---

## 10. Self-Supervised Learning & Generative Models

### Self-Supervised Learning

1. **Q:** What is self-supervised learning and why important?  
   **A:** It creates supervision from the data itself (e.g., predicting masked parts). Unlike general unsupervised learning (often density estimation or clustering), self-supervised learning builds auxiliary supervised tasks from unlabeled data and scales well with abundant data.
2. **Q:** What is a pretext task? Give examples.  
   **A:** A pretext task is an artificial prediction task to learn representations. Examples: rotation prediction, jigsaw/patch order, colorization, masked patch prediction—forcing invariance to transformations and learning semantic structure.
3. **Q:** Explain contrastive learning.  
   **A:** Define positive pairs (two augmentations of same instance) and negatives (different instances). Contrastive loss (e.g., InfoNCE) pulls positives together and pushes negatives apart.
4. **Q:** Describe CLIP and its downstream capabilities.  
   **A:** CLIP trains image and text encoders on paired data with a contrastive loss, aligning modalities. It enables zero-shot classification and image–text retrieval.

### Generative Models — Overview

5. **Q:** What is a generative model? Explicit vs implicit density.  
   **A:** It models data distribution to sample or score data. Explicit density models (autoregressive, VAE, diffusion) define likelihood; implicit models (GANs) only sample without tractable likelihood.
6. **Q:** Describe the autoregressive approach and its drawback.  
   **A:** Factorize \(p(x)=\prod_i p(x_i|x_{<i})\); explicit likelihood but slow, sequential sampling.
7. **Q:** Compare VAE, GAN, and Diffusion Models.  
   **A:** **VAE:** explicit, stable training, fast sampling but blurrier outputs. **GAN:** implicit, sharp samples but unstable and mode collapse. **Diffusion:** explicit/score-based, stable and high quality but slow sampling.

### Variational Autoencoders (VAE)

8. **Q:** Describe VAE architecture.  
   **A:** Encoder outputs mean/variance for \(q(z|x)\); sample \(z\); decoder generates \(p(x|z)\). Stochastic latent enables generative modeling.
9. **Q:** Explain the ELBO and its terms.  
   **A:** \(\text{ELBO}=E_{q(z|x)}[\log p(x|z)]-KL(q(z|x)\|p(z))\). Reconstruction fits data; KL regularizes toward prior. Maximizing ELBO approximates log-likelihood.
10. **Q:** Explain the reparameterization trick.  
    **A:** Sample \(z=\mu+\sigma\odot\epsilon\), \(\epsilon\sim\mathcal{N}(0,1)\), to make sampling differentiable for backpropagation.

### Generative Adversarial Networks (GANs)

11. **Q:** Describe GAN architecture.  
    **A:** A generator maps noise to samples; a discriminator distinguishes real vs fake. They train adversarially.
12. **Q:** Write and explain the minimax objective.  
    **A:** \(\min_G\max_D E_{x}[\log D(x)] + E_{z}[\log(1-D(G(z)))]\). At equilibrium, \(G\) matches the data distribution and the optimal discriminator is \(D^*(x)=1/2\) for all \(x\).
13. **Q:** Describe the practical GAN training procedure.  
    **A:** Alternate discriminator and generator updates; use non-saturating generator loss (maximize \(\log D(G(z))\)) to avoid vanishing gradients.
14. **Q:** Main pros and cons of GANs.  
    **A:** Pros: high-quality sharp samples. Cons: unstable training, mode collapse, no explicit likelihood. Improvements: WGAN, LSGAN, spectral normalization.
15. **Q:** Explain smooth latent space in GANs.  
    **A:** Linear interpolation between latent vectors yields smooth semantic transitions, indicating learned manifold structure.

### Diffusion Models

16. **Q:** Core intuition behind diffusion models.  
    **A:** A forward process gradually adds noise; a neural network (often U-Net) learns to reverse the process by denoising/estimating the score.
17. **Q:** Describe Rectified Flow formulation.  
    **A:** Sample \(t\in[0,1]\), \(x_t=(1-t)x_0+t x_1\); train velocity \(v_\theta(x_t,t)\) to match \(x_1-x_0\) with MSE. Sampling integrates the ODE from noise to data.
18. **Q:** Explain Latent Diffusion Models (LDM).  
    **A:** LDMs first train an autoencoder to map images into a latent space, optionally using an adversarial loss with a discriminator. The diffusion model is then trained and sampled in that latent space with the autoencoder frozen. The discriminator, if used, is only part of the autoencoder pretraining and not part of the diffusion model itself.
19. **Q:** Describe Classifier-Free Guidance (CFG).  
    **A:** Train with conditional and unconditional data by dropping the condition. At inference, combine predictions: \(\hat{\epsilon}=(1+w)\epsilon_{\text{cond}}-w\epsilon_{\text{uncond}}\); requires two forward passes per step.
20. **Q:** Why is the noise schedule important?  
    **A:** It controls SNR across timesteps. Uniform sampling over noise levels overweights high-noise steps; cosine or logit-normal schedules balance learning.
21. **Q:** Why is a diffusion model a latent variable model?  
    **A:** It introduces latent variables \(x_{1:T}\) in a forward noise chain. Training maximizes a likelihood bound, and the model learns the score \(\nabla_x \log p(x_t)\).

---

## 11. Federated Learning

1. **Q:** What is Federated Learning and how does it differ from centralized training?  
   **A:** FL trains a shared model across many clients while keeping data local, sharing only model updates. Centralized training collects data in one server.
2. **Q:** Describe FedAvg step-by-step.  
   **A:** Server initializes model → sends to clients → each client trains locally for E epochs → clients send updates → server averages updates weighted by data size.
3. **Q:** What is data heterogeneity (non-IID) and why is it hard?  
   **A:** Client data distributions differ, causing biased local updates and slower/more unstable convergence.
4. **Q:** What is client drift and how can it be mitigated?  
   **A:** Local training moves models toward local optima; mitigations include FedProx, SCAFFOLD, or fewer local steps.
5. **Q:** Why is communication efficiency critical and how to improve it?  
   **A:** Many rounds are bandwidth-heavy. Use local SGD steps, gradient compression/quantization, or sparsification.
6. **Q:** Explain gradient-inversion attacks.  
   **A:** Attackers reconstruct training data from shared gradients, showing privacy leakage even without raw data.
7. **Q:** Describe Differential Privacy in FL.  
   **A:** Clip gradients and add noise before aggregation to bound individual contribution; trade-off between privacy and accuracy.
8. **Q:** Explain Secure Aggregation.  
   **A:** Cryptographic protocols allow the server to see only the aggregate update, not individual client updates.
9. **Q:** Horizontal vs Vertical FL with examples.  
   **A:** Horizontal: same features, different users (e.g., hospitals). Vertical: same users, different features (e.g., bank + retailer).
10. **Q:** List practical challenges of deploying FL.  
    **A:** Stragglers, system heterogeneity, unreliable connectivity, adversarial clients/poisoning, privacy/legal constraints.

---

## 12. Semantic Segmentation

1. **Q:** Define semantic segmentation and compare to classification and detection.  
   **A:** Semantic segmentation labels every pixel. Classification labels the whole image, detection outputs bounding boxes.
2. **Q:** Why can’t a standard classification CNN be used directly?  
   **A:** Fully connected layers remove spatial resolution. FCNs replace them with convolutional layers and upsample to dense predictions.
3. **Q:** Describe upsampling techniques and trade-offs.  
   **A:** Bilinear interpolation is fast but not learnable; transpose convolution is learnable but can cause artifacts; max-unpooling uses pooling indices.
4. **Q:** Explain dilated convolutions.  
   **A:** Insert gaps to increase receptive field without extra parameters or downsampling, preserving resolution for dense prediction.
5. **Q:** Describe encoder-decoder with skip connections.  
   **A:** Encoder captures semantics; decoder upsamples. Skip connections fuse high-resolution features to improve localization.
6. **Q:** Describe the U-Net architecture.  
   **A:** Symmetric encoder-decoder with skip connections, originally for biomedical segmentation; works well with limited data.
7. **Q:** Semantic vs instance segmentation.  
   **A:** Semantic assigns class per pixel; instance also separates individual objects of the same class.
8. **Q:** What is panoptic segmentation?  
   **A:** Unifies semantic and instance segmentation, labeling each pixel with class and instance ID; “stuff” vs “things”.
9. **Q:** Explain IoU and mIoU.  
   **A:** IoU = intersection/union per class; mIoU averages across classes, reducing bias from class imbalance.
10. **Q:** Techniques for class imbalance.  
    **A:** Weighted or focal losses, oversampling rare classes, or patch sampling; imbalance is severe because background dominates.

---

## 13. Reinforcement Learning

### Fundamentals & MDP

1. **Q:** Define the RL problem and key components.  
   **A:** An agent interacts with an environment, observing states, taking actions, and receiving rewards; it learns a policy to maximize expected return while balancing exploration and exploitation.
2. **Q:** What is an MDP?  
   **A:** A Markov Decision Process is \((S,A,P,R,\gamma)\) with the Markov property: next state depends only on current state and action.
3. **Q:** Define policy \(\pi(a|s)\) and deterministic vs stochastic.  
   **A:** A policy maps states to actions; deterministic outputs a single action, stochastic outputs a distribution.
4. **Q:** Define \(V^\pi(s)\) and \(Q^\pi(s,a)\).  
   **A:** \(V^\pi(s)\) is expected return from state \(s\); \(Q^\pi(s,a)\) is expected return from taking action \(a\) in state \(s\).
5. **Q:** Bellman Expectation Equation for \(V^\pi(s)\).  
   **A:** \(V^\pi(s)=\mathbb{E}_{a\sim\pi,s'\sim P}[R(s,a)+\gamma V^\pi(s')]\).
6. **Q:** Define \(V^*(s)\) and \(Q^*(s,a)\).  
   **A:** \(V^*(s)=\max_\pi V^\pi(s)\) and \(Q^*(s,a)=\max_\pi Q^\pi(s,a)\), satisfying the Bellman optimality equations.
7. **Q:** Model-based vs model-free RL.  
   **A:** Model-based learns/uses \(P\) and \(R\) for planning (e.g., Dyna, Value Iteration). Model-free learns values/policies directly (e.g., Q-learning, SARSA, DQN).

### Value-Based Methods & Deep Q-Networks

8. **Q:** Describe Q-learning and its TD update.  
   **A:** \(Q\leftarrow Q+\alpha[r+\gamma\max_{a'}Q(s',a')-Q(s,a)]\); off-policy due to greedy max.
9. **Q:** Describe SARSA and how it differs from Q-learning.  
   **A:** SARSA uses the action actually taken: \(Q\leftarrow Q+\alpha[r+\gamma Q(s',a')-Q(s,a)]\); it is on-policy.
10. **Q:** Describe DQN and its two key contributions.  
    **A:** DQN uses a neural network to approximate \(Q\), with **experience replay** and a **target network** to stabilize training.
11. **Q:** Explain experience replay.  
    **A:** Store transitions \((s,a,r,s',done)\) and sample mini-batches randomly to break correlation and improve data efficiency.
12. **Q:** Explain the target network.  
    **A:** A periodically updated frozen copy used to compute TD targets, reducing instability from a moving target.
13. **Q:** Difference between MC and TD methods.  
    **A:** MC uses full episode returns (unbiased, high variance); TD bootstraps from next value (biased, lower variance, online).

### Policy Gradient Methods

14. **Q:** What is a policy gradient method and its advantage?  
    **A:** It directly optimizes policy parameters via gradient of expected return, naturally handling continuous or stochastic action spaces.
15. **Q:** Describe REINFORCE.  
    **A:** \(\nabla J\approx\sum_t \nabla_\theta \log \pi_\theta(a_t|s_t) G_t\); high variance due to Monte Carlo returns.
16. **Q:** Why is policy gradient variance high and how to reduce it?  
    **A:** Returns are noisy; use baselines/advantages, larger batches, or normalization. Baselines don’t bias because \(E[\nabla \log \pi]=0\).
17. **Q:** Describe Actor-Critic.  
    **A:** Actor updates the policy; critic estimates value/advantage to reduce variance compared to REINFORCE.
18. **Q:** Define advantage function and its role.  
    **A:** \(A^\pi(s,a)=Q^\pi(s,a)-V^\pi(s)\); subtracting the baseline reduces variance without changing expectation.
19. **Q:** List main equivalent forms of the policy gradient.  
    **A:** Forms include:
    - REINFORCE (returns)
    - Q Actor-Critic (Q)
    - Advantage Actor-Critic (A)
    - TD Actor-Critic (TD error)
    - TD(λ) Actor-Critic (eligibility traces)
    - Natural Actor-Critic (natural gradient)  
    More bootstrapping typically increases bias while reducing variance.
20. **Q:** Practical characteristics of policy gradients.  
    **A:** On-policy by default; off-policy via importance sampling. Gradients are noisy, so small steps, entropy regularization, and careful tuning are needed.

### Advanced Policy Optimisation (TRPO & PPO)

21. **Q:** What motivates TRPO?  
    **A:** Large policy updates can collapse performance. TRPO enforces a trust region via a KL-divergence constraint.
22. **Q:** TRPO surrogate objective and KL constraint.  
    **A:** Maximize \(E[\frac{\pi_\theta}{\pi_{\text{old}}}A_{\text{old}}]\) s.t. \(E[KL(\pi_{\text{old}}\|\pi_\theta)]\le\delta\); solved with conjugate gradient and line search.
23. **Q:** Describe PPO and its clipped objective.  
    **A:** PPO uses \(J^{CLIP}=E[\min(r_tA_t,\text{clip}(r_t,1-\epsilon,1+\epsilon)A_t)]\), providing a cheap trust-region approximation.
24. **Q:** Compare TRPO and PPO.  
    **A:** TRPO has stronger theoretical guarantees; PPO is simpler and more widely used in practice.

### RL in the Real World

25. **Q:** Describe sim-to-real transfer and domain randomisation.  
    **A:** Simulation is cheap but differs from reality, causing deployment failures. Domain randomisation varies simulation parameters to improve robustness.
26. **Q:** Explain reward specification and reward hacking.  
    **A:** Defining a correct reward is hard; mis-specified rewards can lead agents to exploit loopholes instead of achieving the intended goal.
