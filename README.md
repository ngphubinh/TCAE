---
title: 'Noise-invariant Embedding with Triplet Centroid Autoencoder for Recognition of Japanese Corporate Seals'
author: Binh P. Nguyen, Thanh M. Tran, Anh D. Le, Thai Q. Ha, Trung B. Nguyen, and Quang H. Nguyen
output: html_document
---



## Background

Recognition of seals on documents such as bills and letters provides information on the issuing organisations, which is particularly useful in document classification. Applying computer vision techniques on automatic seal recognition is challenging due to noise and lacking of samples in each class. This results in limited research on this task. In this study, we collected and published the first public dataset of Japanese corporate seals. We also propose a deep learning method, termed triplet centroid autoencoder (TCAE), for seal recognition. Our method employs the triplet-loss model to transform seal images into an embedding space. The embedding space is additionally guided to ignore noisy information and gather closer to their centroids by a centroid autoencoder. Additionally, we propose a similarity method to detect unseen samples. Experiments on the Japanese seal dataset demonstrate that the TCAE can significantly compress clusters of seals while keeping better distances among them in the embedding domain compared to the triplet-loss model. The quality improvement of the embedding space also yields higher accuracies in both tasks of seal recognition and detecting unseen seals: $99.99\%$ and $99.95\%$ on the public test set without and with unseen seals, respectively.

## Data Collection

There has been no public dataset of seal images, possibly due to security risks. The availability of this data is also limited. Hence, data collection for seal recognition is a challenging task. Our search for seal samples from the Internet results in an insufficient amount of data because companies and organisations usually do not provide prototype images of their seals. Still, training models with triplet loss requires numerous data under miscellaneous conditions, such as varying seal edge quality and background. Therefore, we applied augmentation algorithms to diversify our collected data.

To create a dataset for our study, we first collected from the Internet seal prototypes of Japanese companies. Prototypes are the original seals designed uniquely for business organizations. As the number of prototypes from the Internet is insufficient, we also gathered some Japanese business letters and then processed them to extract the prototypes. The number of Japanese characters in a seal ranges from $4$ to $16$ words. They are in the form of vertical writing arranged in either a square or sometimes a circle with one of the following patterns: $2 \times 2$, $3 \times 3$, or $4 \times 4$ words.

We diversified the conditions of seal samples from prototypes using augmentation techniques because the collected prototypes were not in as poor conditions as real samples. At first, we collected multiple invoice templates, each of which could be the background of a real seal sample. Prototypes were pasted on those invoices and then extracted to generate seal samples. However, such artificial samples were not analogous to real samples since, in fact, real samples may be blurred, even lose some edges, have varied hue, and so on. Thus, we applied several augmentation techniques to make the synthesised samples more realistic. This process randomly removed or blurred edges, rotated randomly in the range of 0 to 5 degrees, and changed the hue of each synthesised sample. 

All collected and artificially created samples were divided into three sets: training, validation, and public test sets. In addition to being used for selecting the best model, the result in the validation set can also determine the similarity threshold. We amplified the difficulty of the samples in the public test set by removing more edges and blurring the seals more than those in the training and validation sets.

We further collected from business invoices a set of $110$ samples corresponding to $21$ seals of Japanese companies. This set was used as the second test set, called private test set, which was the test on real samples with noise. We also prepared an additional set of $101$ unregistered seal samples, called ``Unknown Set''. This set is used to evaluate whether the model can recognise samples of unregistered seals, which have not been trained.

Our dataset can be downloaded via this link: https://drive.google.com/drive/folders/1Lxg_VXSeazIWHXUC1CuIvK6spgIrVIoD

## Contact

[Go to contact information](http://homepages.ecs.vuw.ac.nz/~nguyenb5/contact.html)

