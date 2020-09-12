---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: 'DeformSyncNet: Deformation Transfer via Synchronized Shape Deformation Spaces'
subtitle: ''
summary: ''
authors:
- Minhyuk Sung
- admin
- Panos Achlioptas
- Niloy J. Mitra
- Leonidas J. Guibas
author_notes:
- "Equal contribution"
- "Equal contribution"
tags: []
categories: []
date: '2020-11-17'
lastmod: 2020-09-12T14:51:31+08:00
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
publishDate: '2020-09-12T06:51:31.330719Z'
publication_types:
- 2
abstract: 'Shape deformation is an important component in any geometry processing toolbox. The goal is to enable intuitive deformations of single or multiple shapes or to transfer example deformations to new shapes while preserving the plausibility of the deformed shape(s). Existing approaches assume access to point-level or part-level correspondence or establish them in a preprocessing phase, thus limiting the scope and generality of such approaches. We propose DeformSyncNet, a new approach that allows consistent and synchronized shape deformations without requiring explicit correspondence information. Technically, we achieve this by encoding deformations into a class-specific idealized latent space while decoding them into an individual, model-specific linear deformation action space, operating directly in 3D. The underlying encoding and decoding are performed by specialized (jointly trained) neural networks. By design, the inductive bias of our networks results in a deformation space with several desirable properties, such as path invariance across different deformation pathways, which are then also approximately preserved in real space. We qualitatively and quantitatively evaluate our framework against multiple alternative approaches and demonstrate improved performance.'
publication: '*ACM Transactions on Graphics (Proc. of SIGGRAPH Asia)*'

url_pdf: https://arxiv.org/pdf/2009.01456
url_code: https://github.com/Steve-Tod/DeformSyncNet
url_project: https://mhsung.github.io/deform-sync-net.html
---
