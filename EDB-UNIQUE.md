---
layout: page
permalink: /projects/edb-unique/
title: EDB-UNIQUE
subtitle: Edge Detection Based Unsupervised Image Quality Estimation
---

{: .box-note}
**Download:** Get the paper in PDF from [here](/doc/EDB-UNIQUE.pdf)

## Abstract

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
In this paper, we estimate the perceived quality of images by sparse representations obtained from popular image processing databases with unsupervised learning method. Several operations are applied to the database images to enhance the learning result, including applying the edge detection filter to the intensity channel and attaching the result as a fourth channel to the original image in order. The pre-processed images are then fed to a linear decoder to obtain sparse representations, followed by suppression mechanisms for the visual system. Detailedly, the linear decoder is trained with 100,000 image patches of size 8s8$ randomly obtained from 1,000 images in the ImageNet 2013 \$${}^{2}$$ database. The proposed quality estimation method EDB-UNIQUE is tested on the LIVE${}^{\cite{ref:LIVE}}$ and Multiply Distorted LIVE${}^{\cite{ref:MULTI-LIVE}}$ databases and compared with the native database-enclosed SSIM quality estimator and the original UNIQUE quality estimator. Based on experimental results, the EDB-UNIQUE method provides better estimation in most categories compared to the original UNIQUE approach.

\$$()^(2)$$

$$
\begin{aligned}
  & \phi(x,y) = \phi \left(\sum_{i=1}^n x_ie_i, \sum_{j=1}^n y_je_j \right)
  = \sum_{i=1}^n \sum_{j=1}^n x_i y_j \phi(e_i, e_j) = \\
  & (x_1, \ldots, x_n) \left( \begin{array}{ccc}
      \phi(e_1, e_1) & \cdots & \phi(e_1, e_n) \\
      \vdots & \ddots & \vdots \\
      \phi(e_n, e_1) & \cdots & \phi(e_n, e_n)
    \end{array} \right)
  \left( \begin{array}{c}
      y_1 \\
      \vdots \\
      y_n
    \end{array} \right)
\end{aligned}
$$

<hr />

# INTRODUCTION

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
With the high-speed network emerging and spreading in recent years, online applications have grown rapidly. At such age that almost everyone serves as the content creator and thus provides an enormous amount of media information, evaluating the quality of images in bulk is absolutely necessary and critical. Also, with the trend of cellphone manufacturers pushing bigger image sensors and high-end camera modules to that digital device everyone always holds on hand or keeps in pocket these days, together with the faster WIFI and cellular network introduced recent years, high-quality images are fast populating. Hence, the need of a better method to assess images for objective scores closer to subjective impression definitely exists. While authors in \cite{ref:UNIQUE} have developed an unsupervised learning algorithm to mostly fulfill the need, improvements based on that could be made so as to let the objective results of such method be more approached to the subjective results.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
In this paper, we develop a new approach based on the original UNIQUE algorithm, to focus on more specific cases as well as to provide better results overall.

# METHODOLOGY

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
We transform RGB images into YCbCr images as UNIQUE. UNIQUE picks three channels Y, G and Cr channels as input for patch generation. Different from UNIQUE, we add an additional channel, the edge channel. The main reason for this pre-processing is we want this quality assessment method to pay more attention to edge distortions. In the demonstration of UNIQUE, we found that the sparse representation lost a lot of information in the texture area. Therefore, we want sparse representation to create more features describing edges. Since the number of input values for sparse representation increases, we increase the number of elements in sparse representation consequently.

![The Pipeline of EDB-UNIQUE](/img/projects/edb-unique/flowchart.png)

## Color Space Conversion

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
Like UNIQUE, we focus on luminance (Y channel) of the YCbCr color space, as the changes in intensity domain compared to those in chroma are more sensitive to human visual system.${}^{\cite{ref:VISION MODEL}}$ However in addition, we apply the edge detection filter to the intensity and use it as the fourth channel of our custom-defined color space, in order to preserve more edge features. Also, the green channel of the RGB color space is selected to represent the three RGB channels, since the green channel contains most information from R and B color channels. A paper${}^{\cite{ref:COLOR SPACES}}$ is already existing to prove such result by showing the cross-correlation between channels of RGB representations, the correlation $r_{RG}$ between R and G color channels is 0.98 and the cross-correlation $r_{GB}$ between G and B color channels is 0.94.