# distracted-driver
Project for a hack event at UMass Amherst

Overview:
Distracted driving kills around 9 people and injures over 1000 people per day in the US (CDC). How do we prevent drivers from being distracted while driving?

Problem:
Code for detecting when a driver is sleeping (deemed as the user closing his/her eyes for more than 3 seconds consecutively) already exists. This is openCV code from pyimagesearch.com that uses facial detection to crop the user's eyes out and see if his/her eyes are closed, and then blares an alarm when detection occurs.

The problem with this code is that it only works after the user sleeping for 3 seconds, which puts other cars on the road at risk for that exact amount of time. Our solution to distracted driving is to prevent the user from sleeping in the first place. 

We do this by determining when the user is tired. Linear regression models from online tell us that if the user blinks more than the normal blinking rate (3 times every 9 seconds), the user is tired.
Thus, we implemented ONE method in the given openCV code to detect when the user blinks more than 3 times in 9 seconds to tell that the user is tired, or "drowsy". 

Techincal Explanation:
A blink is registered when the distance between the user's upper and lower eyelid decreases significantly. When your eye is open, the distance is higher. When it closes, it decreases. Everytime a blink is registered, our count that we created increases. Once this count exceeds 3 per our frame (9 seconds), we warn the user.
