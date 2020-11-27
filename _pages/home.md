---
layout: splash
permalink: /
header:
  overlay_image: /assets/images/splash-cloud.png
  overlay_color: #FFF
  overlay_filter: 0.5
  caption: "Photo credit: [**Wikimedia**](https://commons.wikimedia.org/wiki/File:Between-two-cloud-layers.jpg)"
excerpt: "Welcome on my personnal website were you can find explanation on the demos I use during my trainings, usefull links, question and answers."
intro: 
  - excerpt: 'Select your provider or subject to start your journey.'
feature_aws:
  - image_path: /assets/images/logo-aws.png
    alt: "AWS"
    title: "AWS Related Content"
    excerpt: "A couple of demos to support AWS trainings, QnA and usefull links."
    url: "/demos/aws-00/"
    btn_class: "btn--info"
    btn_label: "Learn more"
feature_azure:
  - image_path: /assets/images/logo-azure.png
    alt: "Azure"
    title: "Azure Related Content"
    excerpt: "A couple of demos to support Azure trainings, QnA and usefull links."
    url: "/demos/az-00/"
    btn_class: "btn--info"
    btn_label: "Learn more"  
---
{% include feature_row id="intro" type="center" %}

{% include feature_row %}

{% include feature_row id="feature_aws" type="left" %}

{% include feature_row id="feature_azure" type="right" %}