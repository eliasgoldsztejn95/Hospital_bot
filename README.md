# Hospital_bot
Hospital simulator with pedestrians and robot

This repository includes files and commands used for the creation of a hospital simulator with pedestrians and a robot.

# Hospital world
<img src="https://user-images.githubusercontent.com/75029654/166143327-e4caf24c-6b8a-4629-9f03-982de54fe37e.png" width="300" height="300">

The simulator of the hospital was taken from: https://github.com/aws-robotics/aws-robomaker-hospital-world.
which is amazon's representation of a hospital. It is very rich in the sense of quantity and quality of objects simulated, and it represents 
realistically a hospital.

### Notes
The models have to be downloaded manually from: https://app.ignitionrobotics.org/fuel/models into local models folder.

# Pedestrain simulator
<img src="https://user-images.githubusercontent.com/75029654/166143081-f978b80b-680e-4c15-87a3-a95c89352896.png" width="500" height="250">

The pedestrian simulation is acquired using pedsim_ros package. The package is based on: https://arxiv.org/pdf/cond-mat/9805244.pdf social force model.
This package allows to choose the quantity and type of pedestrians, and motion patterns. THe package was taken from: https://github.com/srl-freiburg/pedsim_ros.

### Notes
The hospital world of amazon has to be moved to pedsim_gazebo_plugin/worlds folder. Notice that the line: plugin name="ActorPosesPlugin" filename="libActorPosesPlugin.so"
has to be added at the end of the file to allow pedestrian movement.
  
Notice that the pedestrian simulator has to account for obstacles in the world. This should be described in <scenario>.xml found in pedsim_simulator/secnarios.
  
  
### Commands
To launch the hospital world:
> roslaunch pedsim_gazebo_plugin hospital.launch

To launch the pedestrian simulator:
> roslaunch pedsim_simulator simple_pedestrians.launch

# Robot
<figure>
  <img src="https://user-images.githubusercontent.com/75029654/166143949-f4bf762d-8f0a-431f-b968-629d54b9963e.png" width="250" height="250"title="Optional title">
  <figcaption>Blattoidea</figcaption>
</figure>

<figure>
  <img src="https://user-images.githubusercontent.com/75029654/166143515-1d70e6c3-9b27-472e-b0d3-05d21cc4456b.png" width="250" height="250"/>
  <figcaption>Armadillo</figcaption>
</figure>

The robot used is a simple version of the armadillo robot by RobotiCan (https://robotican.net/armadillo/), that includes its base, lidar and kinetic sensors.
It was taken from: https://github.com/TalFeiner/robot_description.

### Commands
To launch the blattoidea robot launch:
> roslaunch blattoidea blattoidea.launch
