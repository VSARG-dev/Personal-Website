---
title: Alzheimer Helper
summary: An AI chatbot to help people suffering from Alzheimer's.
tags:
  - Chatbot
  - Flask
  - AIML
  - SQLite
date: '2020-11-29'

# Optional external URL for project (replaces project detail page).
external_link: ''

image:
  caption: Photo by rawpixel on Unsplash
  focal_point: Smart

links:
  - icon: github
    icon_pack: fab
    name: Code
    url: https://github.com/VSARG-dev/AlzheimerHelper
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

Alzheimer's disease has become more common nowadays, affecting atleast 10% of the population above the age of 65. Families of patients suffering from Alzheimer's have to undergo a lot of stress, having to constantly remind them of even the most essential things such as their name. This project aims to ease that burden, atleast a little, by allowing Alzheimer's patients to converse with a chatbot and ask questions about themselves to remind themselves of the things they have forgotten. \
\
The initial page allows the family members to register and add the personal details of the patient such as their name, address, phone no., dad name, mom name, emrgency contact no., guardian name and age. A POST request is sent to the kernel which sets all the values in AIML variables. All the data is then stored in a SQLite database. \
\
Once registered, along with a username and password, users can log in and start conversing with the AI chatbot. The patient can ask simple questions about themselves such as "What is my name?". This generates a GET request and the required details are extracted from the SQLite database following which a response is displayed from a pool of responses that have similar meaning. Finally the chats are stored in the SqLite database as well for future reference. \
\
Check out the code on Github for more details!
