---
title: First real-time active learning for optimising supernova follow-up
date: 2025-05-12
cardimage: exoplanet.png
---

*How do we choose which objects to use our precious telescope time for follow-up?*
<!--more-->

For Rubin we won’t have enough telescope time to obtain spectra - breaking light in its full range of colours or wavelengths - to classify all supernovae and transients. An alternative is photometric classification, which uses the evolution of luminosity in different broad-band wavelengths, light-curves- instead of spectroscopy to classify transients. Light-curves are exactly what Rubin LSST and ZTF provide to Fink!

But how do we train these photometric classifiers?  Like the snake biting its tail, we train them using the objects we know which type are from spectroscopy!

*So how do we use our limited amount of spectroscopic time to improve photometric classifiers?*
<!--more-->

The Fink team has been developing a new way of selecting follow-up targets, using Active Learning. Active Learning is a Machine Learning technique where the model selects the most useful data to learn from. It asks questions like, “Which objects would help me learn the most if I knew their labels?”. In this work, we show for the first time that an Active Learning strategy is the best way to select which objects to follow-up spectroscopically and, as consequence,  improve our photometric classifiers. A handful no?


*How does it work?*  
We take the photometric classifier of early type Ia supernovae vs. non early type Ia supernovae from ([Leoni et al. 2022](https://www.aanda.org/articles/aa/full_html/2022/07/aa42715-21/aa42715-21.html) & [Ishida et al. 2019](https://academic.oup.com/mnras/article/483/1/2/5162860?login=false)) and train it with 20 known light-curves from supernovae and other transients. We then apply this classifier to new data from the Zwicky Transient Facility. Instead of selecting those objects with high probability, we select those that the classifier is most unsure of (probability ~0.5). These objects, if they are bright enough, are sent to be followed-up by the ANU 2.3m spectrograph. We get the spectra, we obtain the type of supernova or transient it is and we put this new object in the training set. Retrain - apply to ZTF data - and do this all over again!


![AL_Loop](images/AL_Loop.png)

_Lightcurve for AT2021uey, or [ZTF18abktckv](https://fink-portal.org/ZTF18abktckv), around the main event in 2021. Data from alerts is shown with large colored circles, while small dots show data from ZTF Data Release. The rise of luminosity in July 2021 is due to the presence of the planet._

This event was difficult to describe because it was faint, and the signal from the exoplanet appeared before the main signal. With the launch of the LSST later this year, we expect to see many more events involving exoplanets. We are also working on improving our [microlensing classifier](https://github.com/Professor-G/MicroLIA), which will help us identify these events more accurately. This improvement will allow us to start follow-up observations sooner, helping us learn more about the characteristics of exoplanets.

This work was carried out by a large team of scientists and amateur astronomers from around the world, who conducted follow-up observations. The Fink team was led by P. Voloshyn, a student at IJCLab and the University of Paris-Saclay and Taras Shevchenko National University of Kyiv, Ukraine and Etienne Bachelet from IPAC, US. For more information, see https://arxiv.org/abs/2503.22331 (accepted for publication in Astronomy & Astrophysics).

Postscript: Interestingly, while we were analyzing this event, it also caught the attention of the SNAD team, who were scanning the ZTF Data Release 17 using an anomaly detection algorithm. This discovery is summarized in a [Research Note](https://iopscience.iop.org/article/10.3847/2515-5172/ace9dd/ampdf). It is encouraging for future detections that these rare events can be identified through anomaly detection techniques. We should consider combining traditional search methods with (active) anomaly detection algorithms to improve our ability to detect these events even earlier, and in bigger number.
