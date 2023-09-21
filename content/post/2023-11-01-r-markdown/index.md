---
title: 'Reproduction of adversarial attack algorithm for image description model'
author: ''
date: '2023-11-01'
slug: ''
categories:
  - Research Projects
tags:
  - Image Caption
  - Multi-modal
  - Adversarial Attack
---
## 1. Training Process

This training is based on the paper "Attacking Visual Language Grounding with Adversarial Examples: A Case Study on Neural Image Captioning" and related algorithms. Among them, the tasks I completed were reading the paper, configuring the environment, running the code and analyzing the results.

Learned how to connect and use the server, gained the initial understanding about deep learning and repetition of attack algorithms.

## 2. Code Reproduction

**Show-and-Fool** provides two attack methods, namely target heading method and target keyword method. In the actual run, running the code using the target header method as an example, I convert examples/image1 to a header description for examples/image2. First output the description of the target image and the opponent image respectively:



<center>
    <img style="border-radius: 0.3125em;
    box-shadow: 0 2px 4px 0 rgba(34,36,38,.12),0 2px 10px 0 rgba(34,36,38,.08);" 
    src="https://user-images.githubusercontent.com/116294184/269292812-d0feda59-e77a-4028-b08f-fe0f754be43f.png" width = "80%" alt=""/>
    <br>
    <div style="color:orange; border-bottom: 1px solid #d9d9d9;
    display: inline-block;
    color: #999;
    padding: 2px;">
      Product Rendering
  	</div>
</center>

It means converting the title of a specified image to the title of another target image.


<center>
    <img style="border-radius: 0.3125em;
    box-shadow: 0 2px 4px 0 rgba(34,36,38,.12),0 2px 10px 0 rgba(34,36,38,.08);" 
    src="https://user-images.githubusercontent.com/116294184/269292825-e9c63acb-e611-4c41-8067-a2a14cbdda39.png" width = "80%" alt=""/>
    <br>
    <div style="color:orange; border-bottom: 1px solid #d9d9d9;
    display: inline-block;
    color: #999;
    padding: 2px;">
      Product Rendering
  	</div>
</center>
<div><table frame=void>
	<tr>
        <td><div><center>
        	<img src="https://user-images.githubusercontent.com/116294184/269292840-a5efbe50-ea15-4c24-b63f-838fa90da65f.png"
                 height="300"/>
        	<br>
        	Original Image
        </center></div></td>    
     	<td><div><center>
    		<img src="https://user-images.githubusercontent.com/116294184/269292855-081f957a-bbb2-408a-be45-bd726e3013ca.png"
                 height="300"/>
    		<br>
    		After Attack
        </center></div></td>
	</tr>	
</table></div>


Added attack noise:

<center>
    <img style="border-radius: 0.3125em;
    box-shadow: 0 2px 4px 0 rgba(34,36,38,.12),0 2px 10px 0 rgba(34,36,38,.08);" 
    src="https://user-images.githubusercontent.com/116294184/269292873-3cef443a-7c51-416c-9f12-cb96b69f1e55.png" width = "20%" alt=""/>
    <br>
    <div style="color:orange; border-bottom: 1px solid #d9d9d9;
    display: inline-block;
    color: #999;
    padding: 2px;">
      Noise
  	</div>
</center>


## 3. Analysis

As can be seen from the code running results, the image after the attack and the original image can not be seen any difference in the recognition range of the human eye. After the attack, however, the image description changed to that of the original opponent: the image recognition model identified the man with a tennis racket as a pair of giraffes.
The core of the image adversarial attack algorithm is that the input image description model and the output image description keyword will change after adding a tiny disturbance that cannot be recognized by human eyes to the original image.
Since humans cannot understand the basis of image classification in a computer convolutional neural network, this algorithm can be used to make an image classifier error, and then be trained to improve the classification accuracy. For example, image recognition technology is used in automatic driving. If a deep neural network receives an image and misclassifies it, there can be serious consequences. Using adversarial attack algorithm to train image description model can improve its security.