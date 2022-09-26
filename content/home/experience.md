---
# An instance of the Experience widget.
# Documentation: https://wowchemy.com/docs/page-builder/
widget: experience

# This file represents a page section.
headless: true

# Order that this section appears on the page.
weight: 40

title: Work Experience
subtitle:

# Date format for experience
#   Refer to https://wowchemy.com/docs/customization/#date-format
date_format: Jan 2006

# Experiences.
#   Add/remove as many `experience` items below as you like.
#   Required fields are `title`, `company`, and `date_start`.
#   Leave `date_end` empty if it's your current employer.
#   Begin multi-line descriptions with YAML's `|2-` multi-line prefix.
experience:
  - title: ML Intern
    company: North Eastern Space Applications Centre
    company_url: 'https://nesac.gov.in'
    company_logo: isro-nesac
    location: India
    date_start: '2021-05-06'
    date_end: '2021-07-28'
    description: |2-
        Worked on development of DL pipeline for 3D semantic segmentation task performed on drone and satellite generated images. Pipeline deployed as an API using an Inference server to use this service in an application or web app for visualization of results. The project involved:
      
        
        * Choosing an Inference Server that could handle multiple frameworks, was scalable, could run multiple models simultaneously, had readily available documentation and was easy to work with while being fully open source. The ones tested were MLflow, BentoML, Triton and Cortex. Triton Inference Server turned out to be the most optimal for our requirements.
        * Using Tensorflow and Nvidia CUDA to work with Deeplab for object detection and YOLO for semantic segmentation. Used Nvidia Container Toolkit to utilize Triton GPU.
        * Hosting pre-trained models using Inference serving. Postman client API was used for testing the inference server.
        * Working on an image classification model using CNNs.
        * Building a hosted website. It involved:
          1. React.js based frontend where users could uplaod images.
          2. Node.js based backend where the models could run on the uploaded images and send back the output in the form of a JSON based response.
          3. Cloud based deployment of web service using AWS.


design:
  columns: '2'
---
