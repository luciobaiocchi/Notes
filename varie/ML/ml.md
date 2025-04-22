# Machine Learning Model

The term, `Machine Learning`, often mystifies its nature of computer science, as its name might suggest that the machine is learning as human does, or even better. 

Despite the hope that one day we could have machines that think and learn the way that humans do, machine learning nowadays does not go beyond a computer program that performs the predefined procedures. What distinguishes a machine learning algorithm from a non-machine-learning algorithm, such as a program that controls traffic lights, is its ability to `adapt` its behaviors to new input. And this adaptation, which seems to have no human intervention, occasionally leads to the impression that the machine is actually `learning`. However, the machine learning model, this adaptation of behaviors is as rigid as every bit of machine instructions that are programmed by humans. 

**So what is a machine learning model ?**

>A machine learning algorithm is the process that uncovers the underlying relationship within the data. 
>
>The outcome of a machine learning algorithm is called machine learning model, which can be considered as a `function` $F$, which outputs certain results, when given the input. 
>
>Rather than a predefined and fixed function, a machine learning model is derived from historical data. Therefore, when fed with different data, the output of machine learning algorithm changes, i.e. the machine learning model changes.

For example, in the scenario of image recognition, one might train a machine learning model to recognize the object in the photos. In one case, one might feed thousands of images with and without cats to a machine learning algorithm, in order to obtain a model that is capable to tell whether there is a cat in a photo. As a result, the input of the generated model would be a digital photo, and the output is a boolean value indicating the existence of a cat on the photo.


The machine learning model in the above case is a function that maps multiple dimensional pixel values to a binary value. Assume that we have a photo of 3 pixels, and the value of each pixel range from 0 to 255. Then the mapping space between the input and the output would be 
$(256×256×256)×2$, which is around 33 million. We can convince ourselves that it must be a daunting task to learn this mapping (machine learning model) in a real-world case where a normal photo accounts for millions of pixels and each pixel is composed of three colors (RGB) instead of a single grey color.

>The task of machine learning, is to **learn** the function, from the vast mapping space.

The process of discovering the latent mapping relationship between millions of pixels and a Yes/No answer, is what we call machine learning, in this case. Most of the time, what we learn at the end, is an approximation to this underlying relationship. Due to its nature of approximation, one should not be disappointed to find that the results of a machine learning model is often not 100% accurate. Before the wide application of deep learning in 2012, the best machine learning model can only achieve around 
75% accuracy in the [ImageNet visual](https://www.image-net.org/) recognition challenge. Till nowadays, still, no machine learning model can claim 100% accuracy, although there are models that make fewer errors (<5%) than humans in this task. 

##  Supervised VS. Unsupervised

Given a machine learning problem, first of all, one can determine whether it is a `supervised` or `unsupervised` problem.

For any machine learning problem, we start from a data set, which consists of a group of `samples`. Each sample can be represented as a tuple of `attributes`. 

For example, there is a famous classic data set called [Iris](https://archive.ics.uci.edu/dataset/53/iris), which is first published in the paper of "The use of multiple measurements in taxonomic problems" - Ronald. A. Fisher (1936) [1]. The Iris data set consists of measurement for 150 samples of iris flower. Each sample contains the measurement for the length and the width of its petal and sepal, and a class attribute that indicates the category of iris flower, namely setosa, versicolor and virginica. Here are a few samples of the Iris data set.

### Supervised Learning

In a **supervised** learning task, the data sample would contain a target attribute $y$, also known as **ground truth**. And the task is to learn a function F, that takes the non-target attributes X and output a value that approximates the target attribute, i.e. $F(X)≈y$. The target attribute $y$ serves as a teacher to guide the learning task, since it provides a benchmark on the results of learning. Hence, the task is called supervised learning. 

In the Iris data set, the class attribute (category of iris flower) can serve as a target attribute. The data with a target attribute is often called "**labeled**" data. Based on the above definition, for the task of predicting the category of iris flower with the labeled data, one can tell that it is a supervised learning task. 

### Unsupervised Learning

In contrary to the supervised learning task, we do not have the ground truth in an unsupervised learning task. One is expected to learn the underlying patterns or rules from the data, without having the predefined ground truth as the benchmark.

One might wonder, without the supervision of the ground truth, can we still learn anything? The answer is yes. Here are a few examples of the unsupervised learning tasks:

- **Clustering**: given a data set, one can cluster the samples into groups, based on the similarities among the samples within the data set. For instance, a sample could be a customer profile, with attributes such as the number of items that the customer bought, the time that the customer spent on the shopping site etc. One can cluster the customer profiles into groups, based on the similarities of the attributes. With the clustered groups, one could devise specific commercial campaigns targeting each group, which might help attract and retain customers. 

- **Association**:  given a data set, the association task is to uncover the hidden association patterns among the attributes of a sample. For instance,  a sample could be a shopping cart of a customer, where each attribute of the sample is a merchandise. By looking into the shopping carts, one might discover that customers who bought beers often bought diapers as well, i.e. there is a strong association between the beer and the diaper in the shopping cart. With this learned insight, the supermarket could rearrange those strongly associated merchandise into the nearby corners, in order to promote the sales of one or another.

### Semi-supervised Learning

In a scenario where the data set is massive but the labeled sample are few, one might find the application of both supervised and unsupervised learning. We can call this task as semi-supervised learning.

In many scenarios, it is prohibitively time-consuming and expensive to collect a large amount of labeled data, which often involves manual efforts. It takes two and a half years for a research team from Stanford to curate the famous ImageNet which contains millions of images with thousands of manually labeled categories. As a result, it is often the case that one has a large amount of data, yet few of them are accurately "labeled", e.g. videos without category or even a title.

>

