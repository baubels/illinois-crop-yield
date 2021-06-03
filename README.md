# illinois-crop-yield

This is the submission made by my team 'We are Dense' for the 2021 ICDSS AI Hackathon. I am grateful for my teammates, for being great to bounce ideas off of, and for creating nice reports and introducing me to some interesting statistical techniques on model evaluation. The 'final_model' was made by me using Pytorch, and used cleaned tabular data from my teammates and other baseline models. The final report for reading can be seen in 'AI_Hack_Report'.

Our model lets farmers predict crop yield months in advance of harvesting, reducing logistical stress. We predicted using EVI and temperature data alone.
The video presentation can be found here: https://www.youtube.com/watch?v=XuMe_tfv1WY. Unfortunetaly, the data is too large to store on Github, so for that reason it can be found here: https://drive.google.com/drive/folders/1UyithOOXWEOQKmgPC5NLxOG6kaHW0UQO?usp=sharing.

The final model (final_model.ipynb) is an ensembled NN with random forest baseline. A decision tree and random forest was first used to prune the data and get rid of outliers and improve the data. Then this remaining data was used to train a new random forest, and was the data used for the neural network as well. An ensembling of the two models was used for robustness and valid predictions for data outside the range of what we trained our model on.

It turns out implicit correlations for crop yield are encoded mostly in temperature and soil moisture data. Using a combination of models to predict the outcome, and this was compared using a variety of metrics to try and minimise biases.

To make it better, using more resources and publicly available data would have been great. I do want to try turning the tabular data into image data and running a CNN through it, this could have made interesting predictions. However, as only a few parameters were meaninful for accurate predictions, I doubt it would have uncovered something particularly interesting not covered in simpler models. I also wanted to NN embeddings for geospatial data and more data analysis on final model.

If this were to be used by farmers in real life, perhaps quantization to a microcontroller that is remote in the field could be optimal. An example MCU could be the Nano BLE Sense, which has a temperature sensor on it, and can run ML inference tasks for months on a single battery.
