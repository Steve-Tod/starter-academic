---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: 'Synergies Between Affordance and Geometry: 6-DoF Grasp Detection via Implicit
  Representations'
subtitle: ''
summary: ''
authors:
- admin
- Yifeng Zhu
- Maxwell Svetlik
- Kuan Fang
- Yuke Zhu
tags: []
categories: []
date: '2021-05-10'
lastmod: 2021-08-05T16:57:10-05:00
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
publishDate: '2021-08-05T21:57:10.002873Z'
publication_types:
- 1
abstract: 'Grasp detection in clutter requires the robot to reason about the 3D scene from incomplete and noisy perception. In this work, we draw insight that 3D reconstruction and grasp learning are two intimately connected tasks, both of which require a fine-grained understanding of local geometry details. We thus propose to utilize the synergies between grasp affordance and 3D reconstruction through multi-task learning of a shared representation. Our model takes advantage of deep implicit functions, a continuous and memory-efficient representation, to enable differentiable training of both tasks. We train the model on self-supervised grasp trials data in simulation. Evaluation is conducted on a clutter removal task, where the robot clears cluttered objects by grasping them one at a time. The experimental results in simulation and on the real robot have demonstrated that the use of implicit neural representations and joint learning of grasp affordance and 3D reconstruction have led to state-of-the-art grasping results. Our method outperforms baselines by over 10% in terms of grasp success rate.'
publication: '*Robotics: Science and Systems*'

url_pdf: https://arxiv.org/pdf/2104.01542
url_code: https://github.com/UT-Austin-RPL/GIGA
url_project: https://sites.google.com/view/rpl-giga2021
---
