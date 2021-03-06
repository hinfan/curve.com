---
title: AIC, Cp and estimators of loss for elliptically symmetric distributions
author: Curve
date: '2018-04-14'
slug: aic-cp-and-estimators-of-loss-for-elliptically-symmetric-distributions
categories:
  - read
tags:
  - Paper
---

这个是在查找 $C_p$ 统计量时，无意看到的一篇论文。虽然英文很渣，但是还是获益匪浅（未完...）

# AIC, Cp and estimators of loss for elliptically symmetric distributions

## Introduction 介绍					 

The problem of model selection has generated a lot of interest for many decades now and especially recently with the increased size of datasets. In such a context, it is important to model the observed data in a way that accounts for the sparsity of the  parameter space. The principle of parsimony helps to avoid classical issues such as overfitting or computational error. At the same time, the model should capture sufficient information in order to comply with some objectives of good prediction, good estimation or good selection and thus it should not be too sparse. This principle has been elucidated by many statisticians as a trade-off between goodness of fit to data and complexity of the model (see for instanceHastie, Tibshirani, and Friedman, 2008, Chapter 7). From the practitioner’s point of view, model selection is often implemented through cross-validation (see Arlot and Celisse, 2010,for a review on this topic) or the minimization of criteria whose theoretical justificationrelies on hypotheses made within a given framework. In this paper, we review two ofthe most commonly used criteria, namely Mallows’ Cp and Akaike’s AIC, together with the associated theory under Gaussian distributional assumptions, and then we propose a generalization to spherically and elliptically symmetric distributions. 

尤其是最近几十年，随着数据规模的增加，模型选择的问题已经引起了许多人的兴趣。在这种情况下，以考虑参数空间稀疏性的方式对观测数据进行建模非常重要。精简的原则有助于避免一些经典问题，如过度拟合或计算误差。与此同时，该模型应捕获足够的信息，以符合良好预测、良好估计或良好选择的目标，因此不应过于稀疏。许多统计学家已经阐明了这一原则，认为是数据拟合优度和模型复杂性之间的权衡(ESL, Chapter 7)。从实践者的观点看，模型选择通常是通过交叉验证实现或者最小化准则，其理论依据依赖于给定框架内的假设。在本论文中，我们回顾了两个最常用的准则，即 Mallow’Cp 和 AIC 准则，以及在高斯分布假设下的相关理论，我们提出了推广到球形和椭圆的对称分布(spherically and elliptically symmetric distributions)。

We will focus initially on the linear regression model

我们将首先关注线性回归模型:

$$
Y = X \beta + \sigma \varepsilon
$$

where $Y$ is a random vector in $\mathbb{R} ^ { n }$, $X$ is a fixed and known full rank design matrix containing p observed variables $x^j$ in $\mathbb{R} ^ { n }$,  $\beta$  is the unknown vector in $\mathbb{R} ^{ p }$of regression coefficients to be estimated, $\sigma$ is the noise level and $ \varepsilon $ is a random vector in $\mathbb{R} ^ { n }$ representing the model noise, with mean zero and covariance matrix proportional to the identity matrix (we assume the proportion coefficient to be equal to one when $ \varepsilon $ is Gaussian). One subproblem of model selection is the problem of variable selection: only a subset of the variables in $X$ gives sufficient and nonredundant information on $Y$ and we wish to recover this subset as well as correctly estimate the corresponding regression coefficients.

一个模型选择的子问题是变量的选择：在X中，只有变量的一个子集提供了关于 $Y$ 的充分和非冗余的信息，我们希望 recover 这个子集，并正确地估计相应的回归系数。

Early work treated the model selection problem from the hypothesis testing point of view. For instance the Forward Selection and Backward Elimination procedures were stopped using appropriate critical values. This practice changed with Mallows’ automated criterion known as Cp (Mallows, 1973). Mallows’ idea was to propose an unbiased estimator of the scaled expected prediction error $ \mathbb { E } _ { \beta } \left[ \| X \hat { \beta } _ { I } - X \beta \| ^ { 2} / \sigma ^ { 2} \right] $ where $ \hat { \beta } _ { I } $ is an estimator of $\beta$ based on the selected variables set $ I \subset \{ 1,\dots ,p \} $, $\mathbb{E}_\beta$ denotes the expectation with respect to the sampling distribution in model (1) and $ \| \cdot \| $ is the Euclidean norm on $ \mathbb { R } ^ { n } $. Assuming Gaussian $i.i.d.$ error terms, Mallows proposed the following criterion

早期我的的工作从假设检验的角度处理模型选择问题。例如，使用适当的临界值停止前向选择和后向消除过程。这种做法随着Mallows的自动化标准Cp而改变。Mallow 的想法是提出一个 scaled 预测误差期望的无偏估计。
$$
C _ { p } = \frac { \| Y - X \hat { \beta } _ { I } \| ^ { 2} } { \hat { \sigma } ^ { 2} } + 2\hat { d f } - n
$$
Where $\hat{\sigma}^2$ is an estimator of variance $\sigma^2$ based on the full linear model fitted with the least-squares estimator $\hat{\beta}^{LS}$ , that is, $ \hat { \sigma } ^ { 2} = \| Y - X \hat { \beta } ^ { L S } \| ^ { 2} / ( n - p ) $ , and $\hat{df}$ is an estimator of df, the degrees of freedom, also called the effective dimension of model. For the least squares estimator, $df$ is the number $k$ of variables in the selected subset $I$ . Mallow's $C_p$ relies on the assumption that, if for some subset $I$ of explanatory variables the expected prediction error is low, then those variables to be relevant for predicting $Y$. In practice, the rule for selecting the "best" candidate is the minimization of $C_p$. However , Mallows argues that this rule should not be applied in all cases, and that it is better to look at the shape of the $C_p$-plot instead, especially when some explanatory variables are highly correlated.

Mallow's $C_p$ 依赖于假设，如果对于一些介绍变量的子集，预测误差期望很小，则这些变量与预测变量 $Y$ 相关。事实上，关于最优选择的准则是最小化 $C_p$。马洛斯认为，这个规则不应该适用于所有情况，而是最好看一看￼图的形状，特别是当一些解释变量高度相关时。

In 1974, Akaike proposed different automatic criteria that would not need a subjective calibration of the significance level as in hypothesis testing based approaches. His proposal was more general with application to many problems such as variable selection, factor analysis, analysis of variance, or order selection in autoregressive models (Akaike, 1974). Akaike’s motivation however was different from Mallows. Akaike considered the problem of estimating the density f(·|β) of an outcome variable Y, where f is parameterized by $ \beta \in \mathbb { R } ^ { p } $. His aim was to generalize the principle of maximum likelihood enabling a selection between several maximum likelihood estimators $\hat{\beta}_I$. Akaike  showed that all the information for discriminating the estimator $ f \left( \cdot | \hat { \beta } _ { I } \right) $ from true $ f ( \cdot | \beta ) $ could be summed up by the Kullback-Leibler divergence $ D _ { K L } \left( \hat { \beta } _ { I } ,\beta \right) = \mathbb { E } \left[ \log f \left( Y _ { \text{ new } } | \beta \right) \right] - \mathbb { E } \left[ \log f \left( Y _ { \text{new} } | \hat { \beta } _ { I } \right) \right] $ where the expectations is taken over new observations. An accurate quadratic approximation to the divergence is possible when $\hat{\beta}_I$ is sufficiently close to $\beta$, which actually corredponds to the distance $ \| \hat { \beta } _ { I } - \beta \| _ { \mathcal { I } } ^ { 2} / 2 $ where $ \mathcal { I } = - \mathbb { E } \left[ \left( \partial ^ { 2} \log f / \partial \beta _ { i } \partial \beta _ { j } \right) _ { i ,j = 1} ^ { p } \right] $ is the Fisher-infomation matrix and for a vector $ Z $, its weighted norm $ \| \mathbf { Z } \| _ { \mathcal { I } } $ is defined by $ \left( \mathbf { Z } ^ { t } \mathcal { Z } \mathbf { Z } \right) ^ { 1/ 2} $ By means of asymptotic analysis and by considering the expectation of DKL Akaike arrived at the following criterion

$$
\text{AIC} = - 2\sum _ { i = 1} ^ { n } \log f \left( y _ { i } | \hat { \beta } _ { I } \right) + 2k
$$

where k is the number of parameters of βˆI. In the special case of a Gaussian distribution, AIC and Cp are equivalent up to a constant for model (1) Hence Akaike described his AIC as a generalization of Cp to a more general class of models. Unlike Mallows, Akaike explicitly recommends the rule of minimization of AIC to identify the best model from data. Note that Ye (1998) proposed to extend AIC to more complex settings by replacing k by the estimated degrees of freedom df.	