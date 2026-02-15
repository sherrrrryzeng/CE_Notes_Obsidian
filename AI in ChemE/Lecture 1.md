---
date: 2026-02-11
Prof: Artur M. Schweidmann
aliases:
  - Machine Learning Overview
  - Classical regression
---
# Intro of AI, ML, DL
## Definition
- AI
	The theory and development of computer systems able to perform tasks normally requiring human intelligence, such as visual perception, speech recognition, decision-making, and translation between languages. 

- Machine Learning
	ML provides computer systems the ability to learn with data without being explicitly programmed.
	
	A computer program is said to learn from experience E with respect to some task T and some performance measure P if its performance on T, as measured by P, **improves with experience** E.

- Deep Learning
	The adjective “deep” refers to the use of multiple layers in the neural network.


Relation:![[15ba1ce333ddffef01e1e8dd72ae677a2519aaf159e343d71b28d92cd83b2079.png]]


## History of AI
![[644fe588b664333d0bfebf8c49ea269d32d535b8619d4617cef95fac00634038.png]]
![[7c91c9413ee2bfa2daa2ab05e8fd7f1af19186555b16e855d338c04e669be05c.png]]

> [!QUIZ 0]
> What recent advancements have contributed to the resurgence of interest in AI in the 21st century?
-> ML & DL


## Categories and Concepts of ML
![[5f2bcf0b778702ab232797a5eebd1aa22e8c8da1daca17786e1f100b0cf12b0a.png]]

### Supervised Learning
Learning based on given input-output pairs

![[63788a68f8800243c8468ac287cf785703ea106e57f7c12f8900963ab9885115.png]]
![[6a7f072c24cd47b1455bbe98e849269d78f47baa007be44874058b941f1e4642.png]]


### Unsupervised Learning
Find patterns in unstructured data

![[443de95f875ecf75eb2a209099d781e5831d64b74a42f79b4c0a73cde36144bb.png]]


### Reinforcement Learning

![[acb87b76a311ba9fd3516df4fdcde2683740a261dcc9c96165697b72dd6e8eae.png]]



> [!QUIZ 1] 
> You want to predict the concentration of pollutants in the effluent of a wastewater treatment plant based on historical data and environmental factors. What type of ML problem is this?
> 
> -> Supervised learning - Regression

> [!QUIZ 2] 
> How would you classify the task of obtaining the reaction kinetic parameters (k value) for a chemical reactor operating in a pilot plant?
> 
> -> Supervised learning - Regression 
> 	*(if we have algorithm)*
> -> No machine learning, just curve fitting

> [!QUIZ 3] 
> You want to recognize a potential fault in your production based on time series data from your sensor measurements? What type of ML problem is this?
> 
> -> Unsupervised learning
> *(The fault is unknown and not in the output)*

> [!QUIZ 4] 
> What kind of machine learning approach was used in the development of ChatGPT?
> 
> -> Supervised learning - Classification
> 	*(with masking, ChatGPT learns to predict sentences)*
> -> Unsupervised learning
> -> Reinforcement learning

-> Generative Artificial Intelligence (GenAI)
![[13bf39966a5b527928b87ac32ece5afbb59883a5a818fcba37a6888716f774e8.png]]


# Polynomial Regression
## Basics of Regression

![[Pass/CP/Q2/Lecture 6#Linear Regression|Lecture 6]]

![[35dd66056385f2a90d16b1c5ead2cede74311ceed855761bf527d685fff089f1.png]]


## Overfitting and Underfitting

![[Pass/CP/Q2/Lecture 6#Polynomial Regression|Lecture 6]]


![[fbad01c8e3f704d6b40d34fee5853b76335191b7433c009e17a1ef7d7696f50b.png]]
- Use 70% data to train the model
- Use 15% data to check the validation 
  -> Tune complexity
- Use 15% data to do final performance evaluation


![[74c0c7b66c0a76419c5d8c8df35de71edccc383918ffa7363c6fa0a6c2ed0c20.png]]
Normalizing all features using scaling: $$z=\frac{x-\mu_{train}}{\sigma_{train}}$$Average and RMS(root mean square): $$\mu_{train}=\frac{\sum_{i=1}^{N_{train}}x_i}{N_{train}}\,\,\,\,\,\,\,\,\,\,\,\,\,\,\sigma_{train}=\sqrt{\frac{\sum_{i=1}^{N_{train}}(x_i-\mu_{train})^2}{N_{train}}}$$

# Pandas

- Head and Tail:
	`data.head()` : display first five elements
	`data.tail(3)` : display last three elements

- To numpy array:
	`data.to_numpy()` / `np.asarray(data)`


