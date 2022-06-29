# Marine-aerial_TII

This repository provides marine and aerial resources from TII experiments.

## Start Guide

1. Install [MRS_Singularity]([./install/install_singularity.sh](https://github.com/ctu-mrs/mrs_singularity).
* 1. (**Warning**) In Step 3 you must to choose a recipe, at this moment you need to:
  * 1. copy and paste the recipe inside this package to /mrs_singularity/recipes
  * 2. ```chmod +x ./build.sh``` inside the folder of recipe 07
  * now you can continues follow the steps by MRS
3. Once MRS Singularity are full installed, let's put marine packges using:
* 1. add an ssh key to your account 
* 2. Clone and its definition (both in the marine-aerial branch):
```
cd /mrs_singularity/user_ros_workspace/src
git clone --branch marine-aerial git@bitbucket.org:autonomouscv/marine_dev.git
``` 
* 3. Let's proceed with the installation:
```
cd /mrs_singularity/user_ros_workspace/src
vcs import < marine_dev/docker_workspace/robots/dev.yml
vcs import < marine_dev/docker_workspace/robots/nukhada.yml
```
* 4. Get in MRS_Singularity, as you did in installation tutorial and do:
  * 1. Build the catkin workspace:
```
cd user_ros_workspace
catkin config --cmake-args -DCMAKE_BUILD_TYPE=Release
catkin build
```

* Important: the plugin for simulating the buoyancy only works when built in release mode, so after you built the workspace do:
```
catkin build asv_wave_sim --cmake-args -DCMAKE_BUILD_TYPE=RelWithDebInfo
```

**ALL DONE, YOU'RE READY TO GO**

## Reccomendations
Recommendations
It is highly recommended that you take a look at the [MRS wiki](https://ctu-mrs.github.io/), to use the MRS uavs, Also learn how the TII marine uuv works.
