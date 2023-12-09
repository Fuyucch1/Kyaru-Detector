# Kyaru-Detector
Is Kyaru in this media ? An AI-driven character recognition

![Kyaru gif](https://media1.tenor.com/m/a-0lShMId-sAAAAC/karyl.gif)

This project, as of now, is more like a notebook listing my tests. I want it to list what I've tried, and what is yet to do.

# First approach

When I think of "character recognition", my mind goes towards "detection" first. If I want my project to be able to detect Kyaru, I need it to be able to detect characters first, and then to decide if the character is Kyaru or not.

The easiest way to do it is to use [nagadomi's lbpcascade_animeface](https://github.com/nagadomi/lbpcascade_animeface/tree/master). The cascade works pretty well and as intended : it extracts the face of characters.

However, while I truly respect nagadomi's works, I feel like I should do the cascade myself. Nagadomi's cascade was trained 9 years ago, maybe trying to do a new one could result in a better model.

As of the 10th of December, I am still trying to create a new one. Building a correct dataset to train the cascade on from scratch has been way time-consuming than I thought it would be.
