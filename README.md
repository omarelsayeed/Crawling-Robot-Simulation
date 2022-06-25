#  Crawling-Robot-Simulation 

## Description

Teaching a Robot how to Crawl using a robotic arm that's two joints 

- My motivation was to learn pybullet which is a robotic simulation library that is easy to use.
- The Simulation is done to show the learning process , how the joints will move , and how the algorithm can be improved.
- i learnt alot about simulation and robotics from this project , things like inverse kinematics , physics engines , etc.




https://user-images.githubusercontent.com/64399795/175787058-372c5d12-8a08-4273-adcd-b6ecf53c768c.mp4





## Table of Contents 

- Installation
- ScreenShots
- TheMDP
- Q-Learning


## Installation

To Try this by yourself , just clone the repository and run the cells , should produce the same output.
If you want to Simulate in real-time replace the p.DIRECT to p.GUI in the robot initialization.
![image](https://user-images.githubusercontent.com/64399795/175570491-78cc1942-3213-4ef5-9b05-8098dcb1429b.png)
for More about the Pybullet engines , please refer to the documentation 
https://docs.google.com/document/d/10sXEhzFRSnvFcl3XxNGhnD4N2SedqwdAvK3dsihxVUA/edit#
The urdf and the meshes are present in the repository and free for use.

## ScreenShots

![image](https://user-images.githubusercontent.com/64399795/175571314-9950f3c3-7c63-4ae3-baca-44f9ac4801ea.png)
![image](https://user-images.githubusercontent.com/64399795/175571714-c5e5ebe7-7cb4-42f4-88b6-a27a671df1ca.png)
![image](https://user-images.githubusercontent.com/64399795/175571822-37689131-1e5f-49e2-87d7-567c8ad9b708.png)

## Results 
# Training Reward 
![image](https://user-images.githubusercontent.com/64399795/175574604-c5e0defc-92d1-4ff8-bfe3-d01304d8bce7.png)
![image](https://user-images.githubusercontent.com/64399795/175574718-c63f770b-ddf8-4736-977a-3905838578d3.png)

# Testing Reward 
![image](https://user-images.githubusercontent.com/64399795/175574635-e99844b4-0697-4ea2-87cb-aeedaf18fd8b.png)
![image](https://user-images.githubusercontent.com/64399795/175574690-850212fb-b55c-4a16-b1fd-3b0344d50d62.png)
# Comparison 
![image](https://user-images.githubusercontent.com/64399795/175609247-6a3c191f-bb79-49ae-8465-429ed14a64df.png)


## The Environment 

first of all , Pybullet allows you to load URDF and SDF and MJCF which are all used to describe robots.
after loading and starting the simulation you see that you only have the robot and a plane which is built in pybullet.
# States
The robot has 3 position for each servo which are 0 , 90 , 180 degrees , combining the two servos gives us an overall 
9 states.
# Actions
in each state you have 9 actions that gets you to all other states , so for example if you are at 0 degrees and 90 degrees
you can take an action that gets you to all other 8 states using the states to actions dictionary that works both ways.
![image](https://user-images.githubusercontent.com/64399795/175573351-5d3e1c32-2650-4aa8-b601-1c7f9b4a1ba6.png)
# Reward 
The reward in real life is calculated by a rotary encoder that senses movement but in the simulation we can
just check if the position is changed , so new_position-current_position is the reward.
# Q learning 
![image](https://user-images.githubusercontent.com/64399795/175574056-22dc49fd-6022-44c6-8b30-62f3a130bf4f.png)

# Future Work 
to test another algorithms like DQN , and to make it move backward and forward.

# References 
[Pybullet Documentation](https://docs.google.com/document/d/10sXEhzFRSnvFcl3XxNGhnD4N2SedqwdAvK3dsihxVUA/edit#)

[Pybullet Tutorial](https://www.youtube.com/watch?v=kZxPaGdoSJY&t=828s&ab_channel=DanielEid)

[Stanford Reinforcement Learning Lecture 1](https://www.youtube.com/watch?v=9g32v7bK3Co&t=3866s&ab_channel=StanfordOnline)

[Stanford Reinforcement Learning Lecture 2](https://www.youtube.com/watch?v=HpaHTfY52RQ&t=3989s&ab_channel=StanfordOnline)

