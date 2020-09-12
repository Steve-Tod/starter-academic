---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: Deep Face Super-Resolution with Iterative Collaboration between Attentive Recovery
  and Landmark Estimation
subtitle: ''
summary: ''
authors:
- Cheng Ma
- admin
- Yongming Rao
- Jiwen Lu
- Jie Zhou
tags: []
categories: []
date: '2020-06-14'
lastmod: 2020-09-12T14:51:03+08:00
featured: false
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ''
  focal_point: ''
  preview_only: false

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["internal-project"]` references `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects: []
publishDate: '2020-09-12T06:51:03.059942Z'
publication_types:
- 1
abstract: "Recent works based on deep learning and facial priors have succeeded in super-resolving severely degraded facial images. However, the prior knowledge is not fully exploited in existing methods, since facial priors such as landmark and component maps are always estimated by low-resolution or coarsely super-resolved images, which may be inaccurate and thus affect the recovery performance. In this paper, we propose a deep face super-resolution (FSR) method with iterative collaboration between two recurrent networks which focus on facial image recovery and landmark estimation respectively. In each recurrent step, the recovery branch utilizes the prior knowledge of landmarks to yield higher-quality images which facilitate more accurate landmark estimation in turn. Therefore, the iterative information interaction between two processes boosts the performance of each other progressively. Moreover, a new attentive fusion module is designed to strengthen the guidance of landmark maps, where facial components are generated individually and aggregated attentively for better restoration. Quantitative and qualitative experimental results show the proposed method significantly outperforms state-of-the-art FSR methods in recovering high-quality face images."
publication: '*Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern
  Recognition*'
publication_short: '*CVPR*'

url_pdf: https://arxiv.org/pdf/2003.13063.pdf
url_code: https://github.com/Maclory/Deep-Iterative-Collaboration
---
