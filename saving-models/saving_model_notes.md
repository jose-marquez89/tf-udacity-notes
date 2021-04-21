# Saving models
- we can save models and avoid retraining models that have already been trained
- tensorflow has a saved model feature
- you can serve via tensorflow serving
- tensorflow has bindings for C
- has the advantage of allowing you to use later for deployment on different platforms
- makes the model portable

### Keras file format
- trained models are saved as HDF5
- this is a format specific to keras
- it's generally good practice to save models with a timestamp using the time module in python

### General
- `.summary()` gives you a summary of the model's layers, neurons and such
- you can continue to further train a saved model
- I will refer to the individual repeatedly interviewed in the course as 'the guy' henceforth
    - the guy mentions his belief that in the near future, everything may have an IP address
    - down to the food you eat? Yes he actually says this is a possibility (I later found this was a stretch and the guy's name is Sebastian)