# Kyaru-Detector
Is Kyaru in this media ? An AI-driven character recognition

![Kyaru gif](https://media1.tenor.com/m/a-0lShMId-sAAAAC/karyl.gif)

## Disclaimer

This project, as of now, is more like a notebook listing my tests. I want it to list what I've tried, and what is yet to do.
I am trying to do everything myself, and I will surely make mistakes. All those mistakes will be documented. Do not take this repository as a functioning solution for this problem. 

# Context

Recognizing a character is no simple feat. For example, let's say you have a model can can recognize the character when they look at you. What happens when the character looks elsewhere ? When the character moves, and the animation gets "distorted" ? Or when you only see their back ? Or only a part of the character, not including the entire face ? What if the artstyle gets very different ? Maybe a "fan-art" ? 

The answer's simple : the model won't recognize the character if it's been solely trained on detecting faces in a certain style.

In this project, we will try to build a complete pipeline which will recognize Kyaru. We will try to detect her not only thanks to her face, but using all the characteristics of her character design. We will even try to add voice recognition.

# First approach

When I think of "character recognition", my mind goes towards "detection" first. If I want my project to be able to detect Kyaru, I need it to be able to detect characters first, and then to decide if the character is Kyaru or not.

The easiest way to do it is to use [nagadomi's lbpcascade_animeface](https://github.com/nagadomi/lbpcascade_animeface/tree/master). The cascade works pretty well and as intended : it extracts the face of characters.

However, while I truly respect nagadomi's works, I feel like I should do the cascade myself. Nagadomi's cascade was trained 9 years ago, maybe trying to do a new one could result in a better model.

As of the 10th of December, I am still trying to create a new one. Building a correct dataset to train the cascade on from scratch has been way more time-consuming than I thought it would be.

19/12/2023 => I am upgrading my work env (AMD is definitely not cut for that kind of thing, so I'm trying to use a nvidia gpu)

# Second step

Even though the first approach is not finshed yet, it does not prevent me from taking a break and trying to think differently about the problem.

The cascade is great because it helps detecting **faces**. But what about everything else ? A character is not only a face, it is also a complex blend of attributes.

Here's an example of what defines Kyaru : 
- Green eyes
- Long grey hair
- Grey cat ears with white tips
- Characteristic outfit
- Voice Actress

One approach we might want to take is called a **Multi-Label Classification**. We can try to create a model which will describe what it sees, and then compare it with the set of attributes corresponding to Kyaru.


# Bibliography

[1] [nagadomi's lbpcascade_animeface blog post, 2011](https://ultraist.hatenablog.com/entry/20110718/1310965532)

[2] Z. Lan, K. Maeda, T. Ogawa and M. Haseyama, "[Hierarchical Multi-Label Attribute Classification With Graph Convolutional Networks on Anime Illustration](https://ieeexplore.ieee.org/document/10097719)," in IEEE Access, vol. 11, pp. 35447-35456, 2023, doi: 10.1109/ACCESS.2023.3265728.

