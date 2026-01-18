---
{"publish":true,"created":"2026-01-18T18:08:57.851+05:45","modified":"2026-01-18T18:28:48.770+05:45","cssclasses":""}
---


****Try the project first**** https://huggingface.co/spaces/trishuli/burn-detection

What to image? On medical field specifically?? and does that make the world better place by discovering cancer before it discovers you or does it fill the world with more slop?  I found some fancy stuff like 
- radiology (xray, ct-scan, MRIs)
- pathology (you can look at tissues and do some interesting stuff) 
	- Definitely picking up "Cancer vs normal" tissue detection next time
- eye retinas  
- Skins

So i proceeded with skin imaging. Mainly because i have this weird keloid type patch i developed out of nowhere. When i googled for the first time once i noticed it, the mighty google said something about melanoma cancer.  It was not cancer....
Other reasons:
- camera no fancy machine required like mri, pathology, eye stuff
- Datasets lured me (ISIC, HAM10000, Fitzpatrick17k). But they lied. A lot of i can't get easy access to.
- It's transfer learning friendly. YoloV11 is trending.

I built a **burn detector**. With mAP of 74% it's shitty but it works. 
****Live Demo:**** https://huggingface.co/spaces/trishuli/burn-detection

## Why? Because I got a burn Dataset 

I used this ****Kaggle Burn Dataset**** (~1,357 images across 3 classes) created by some undergrad in india and it's full of watermarked images . 

##### The Degree of burn 
- 1st: normal go home
- 2nd: eats up epidermis, dermis. Heals but is painful
- 3rd: bye bye nerves. I wonder how grafting works. why would body accept it? unless it's part of the same body

Other limitations if you ask me
- Small size (deep learning typically wants 10k+ images)
- Class imbalance (543 first-degree, 488 second-degree, 200 third-degree)
- Images are full-frame classifications, not localized bounding boxes. Why provide annotations? Like they wanted to show their professors how cool roboflow is.
- Variable image quality and lighting conditions

****Other datasets to explore:****

- ****HAM10000****: 10,015 dermatoscopic images (skin lesions, not burns)
- ****ISIC Archive****: 70k+ skin lesion images
- ****Fitzpatrick17k****: Skin conditions across skin tones
- ****DermNet****: 23k images across 600+ skin conditions
- ****SD-198****: 198 skin disease categories

For burn-specific work, clinical partnerships remain the best path to quality data. This is sad 


## What was Tested
  

### 1. YOLOv8m (Object Detection)
- ****Architecture****: CNN-based, anchor-free detection
- ****Result****: 64.7% mAP

### 2. DINOv2 (Vision Transformer)
- ****Architecture****: Self-supervised transformer (Meta AI)
- ****Result****: 74% F1 score 
- ****Confusion matrix insight****: 2nd degree burns most confused (overlaps visually with 1st and 3rd)

  
### Training Infrastructure Attempted:

- Local Mac Studio M2 Ultra (MPS) - crashed on YOLO11
- Remote Fedora box with RTX 3050 Ti - Secure Boot blocked NVIDIA drivers. Fuck you secure boot. 
- Google Colab T4 - worked reliably



****Future directions:****

- Ensemble YOLO + DINOv2 (detect then classify).
- Segment Anything Model (SAM) for precise wound boundaries
- Multi-task learning (classify burn degree + estimate affected area)
- Synthetic data augmentation with diffusion models

  


****Try it yourself:**** https://huggingface.co/spaces/trishuli/burn-detection


This is a proof-of-concept, not a diagnostic tool.

  

*_For educational purposes only. Well you can't kill but you can misdirect people at your own conscience _*