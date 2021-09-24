<head>
    <script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>
    <script type="text/x-mathjax-config">
        MathJax.Hub.Config({
            tex2jax: {
            skipTags: ['script', 'noscript', 'style', 'textarea', 'pre'],
            inlineMath: [['$','$']]
            }
        });
    </script>
</head>

# 1. The Effect of Different Steps of IAM
![am_iam](https://raw.githubusercontent.com/neurips2021-ars-rebuttal/neurips2021-ars-rebuttal.github.io/master/figure/nips_am_iam.png)

Regarding AM and IAM, the step number setting is not sensitive to the final result. We randomly selected several convolutional kernels on layer 4 of the shallow CNN. Figure 1 shows their AM and IAM for the different number of iterations. we can find that (1) the IAM and AM of the convolution kernels have big differences but are partly very similar. (2) When the number of iterations reaches a sufficient number, both IAM and AM no longer have significant changes. Therefore, when the number of iterations is insufficient, the generated IAM cannot be used to measure the importance of the representations. When the number of iterations is sufficient, the change of step number does not affect the final experimental results. In the experiment, we set the iterations to 1500. Figure 1 shows that this number of iterations is sufficient for the model to get a good visual representation.


# 2. Experimental Results on CIFAR-100
![cifar100](https://raw.githubusercontent.com/neurips2021-ars-rebuttal/neurips2021-ars-rebuttal.github.io/master/figure/nips_cifar100.png)

We also validated our metric on the CIFAR-100 dataset, and the experimental results are consistent with the paper's findings. Models with low MG have high OA on the test set. The MG evaluation method is consistent with the accuracy of the models. The experimental results are shown in Table 1. We used the same shallow CNN model and training settings as in Experiments 3.5 in the paper. For the bad performance of the models, we only adjusted the learning rate during training. For the models with low OA, their MGs are relatively high. The representations of many convolutional kernels for these models are not important, and they have poor generalization.




# 3. OOD setting, Experimental Results on the corrupted CIFAR-10
![cifar10c](https://raw.githubusercontent.com/neurips2021-ars-rebuttal/neurips2021-ars-rebuttal.github.io/master/figure/nips_cifar10c.png)

In the out-of-distribution (OOD) setting, our proposed metric can still select the best-performing models. We choose the four best and worst-performing models on corrupted CIFAR-10 among the models trained on CIFAR-10. Their average ARS, MG, and OA for each layer are shown in Table 2. The experimental results show that the models with lower MG have higher OA. ARS and MG are still valid in the cross-domain scenario, and they can be used to measure the generalizability of the models.
# 4. OOD setting, Experimental Results on the CIFAR-5m
![cifar5m](https://raw.githubusercontent.com/neurips2021-ars-rebuttal/neurips2021-ars-rebuttal.github.io/master/figure/nips_cifar5m.png)

In another set of OOD settings, our proposed metric is still successful in evaluating the generalization performance of the models. We used the same model selection strategy as corrupted CIFAR-10 to find the best and worst-performing on the CIFAR-5m dataset. The results of their experiments are shown in Table 3. MG and OA still show consistency. The high MG, i.e., the model with many insignificant representations, performs worse in generalization. All these experiments show that ARS and MG can be successfully applied to measure the generalizability of models in cross-domain scenarios.


