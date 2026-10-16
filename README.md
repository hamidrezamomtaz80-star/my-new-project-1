# -*- coding: utf-8 -*-
"""
My First AI Project: Cabin Price Predictor
Building AI Course Project

This script uses a simple linear regression model to predict the price of a cabin
based on features like size, sauna size, distance to a lake, etc.
The coefficients are based on the model learned during the Elements of AI course.
"""

def predict_cabin_price(size, sauna_size, distance_to_lake, toilets, distance_to_neighbor):
    """
    Predicts the price of a cabin using a linear equation.
    
    Formula: price = c0*size + c1*sauna + c2*lake + c3*toilets + c4*neighbor
    """
    # Coefficients learned from the training data in the course
    # [Size, Sauna size, Distance to lake, Toilets, Distance to neighbor]
    coefficients = [3000, 200, -50, 5000, 100]
    
    # Calculate the prediction
    prediction = (coefficients[0] * size + 
                  coefficients[1] * sauna_size + 
                  coefficients[2] * distance_to_lake + 
                  coefficients[3] * toilets + 
                  coefficients[4] * distance_to_neighbor)
    
    return prediction

def main():
    print("--- Cabin Price Predictor ---")
    
    # Example cabin details (from the exercise in the course)
    cabin_features = {
        "size": 85,               # m2
        "sauna_size": 10,         # m2
        "distance_to_lake": 15,   # meters
        "toilets": 1,             # count
        "distance_to_neighbor": 100 # meters
    }
    
    print(f"Input features: {cabin_features}")
    
    # Calculate the price
    predicted_price = predict_cabin_price(
        cabin_features["size"],
        cabin_features["sauna_size"],
        cabin_features["distance_to_lake"],
        cabin_features["toilets"],
        cabin_features["distance_to_neighbor"]
    )
    
    print(f"\nThe predicted price for this cabin is: {predicted_price:,.0f} EUR")

if __name__ == "__main__":
    main()
