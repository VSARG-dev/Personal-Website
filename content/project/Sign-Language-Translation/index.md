---
title: Sign Language Translation
summary: A transformer model that takes in video sequences signed in German Sign Language and translates them into readable German text.
 
tags:
  - Deep Learning
  - Sequence Processing
  - Video Processing
  - Machine Translation
  - Natural Language Generation
date: '2022-04-20'

# Optional external URL for project (replaces project detail page).
external_link: ''

image:
  caption: 
  focal_point: Smart

links:
  - icon: github
    icon_pack: fab
    name: Code
    url: https://github.com/VSARG-dev/Sign-Language-Translation
  - icon: note-sticky
    icon_pack: fas
    name: Paper
    url: 'uploads/Sign_Language_Translation.pdf'
url_code: ''
url_pdf: ''
url_slides: ''
url_video: ''

# Slides (optional).
#   Associate this project with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
slides: 
---

As part of the Machine Learning course offered by our college, we decided to implement a Sign Language Translation model keeping the hearing and speech impaired community in mind in an effort to help bridge the gap between us and them. \
\
In the past, most Sign Language Translation models have dealt with static images, wherein the model takes in an image containing a gesture being signed and outputs the "message" being contained in it. While it is definitely a solid first step, this is not at all representative of real world scenarios. \
\
In practical usage, most gestures in sign language are dynamic, i.e, the meaning is conatained in movement. Thus in essence, the problem statement then becomes the non-trivial task of interpreting text sequences from video sequences. Moreover, like other translation problems, the input word order is usually not the same as the output word order either. Both of these reasons make this a **sequence2sequence** problem. \
\
We decided to start from the basics. Using [this](https://www.kaggle.com/datasets/grassknoted/asl-alphabet) kaggle dataset, which contains ASL images labelled with their corresponding alphabet, we fine-tuned the inception-v3 model with a simple classification task. This was fairly simple, and upon achieving satisfactory results we moved on to our main objective: video processing. \
\
We then proceeded with a transformer encoder-deocder architecture. Usually in the domain of Natural Language Processing, the models almost always have a word embedding layer that serves as a look-up table for fetching the appropriate embedding vector for each word in the input. These embeddings are what are then passed through deeper layer of the encoder blocks. In our case, however, there were no words in the input. We had to somehow "embed" frames of the videos. We couldn't use the same approach as in the case of word inputs since the image space is continuous whereas the lexicon space isn't. In other words, there are infinitely many frames that can exist in any given video.\
\
To resolve this issue, we chose the original inception-v3 as in our previous experiment, and took the output from the penultimate layer as the embeddings. Transformers also require something called position encodings so they can keep track of the temporal ordering of frames, so they were added before passing them in. As for the specific transformer architecture itself, we used the pre-trained T5-small (small, due to GPU constraints) so that we could leverage its existing German knowledge. \
\
We tried different configurations of hyperparameters and ran training for ~1.5 hours per config. The best configuration gave us a test BLEU score of `12.75`. While not the best, it isn't a very representative metric as the labelled examples had only one translation per video, and BLEU's representativity increases with more number of semantically equivalent labels. There's also reason to believe that with a bigger transformer model and more data, the results would be much better, as is always the case with transformers. For more technical details, check out our report! \
\
<!-- Credits: My teammate [Pranav Balaji](https://github.com/greenfish8090) -->
