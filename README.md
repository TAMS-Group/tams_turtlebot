# tams_turtlebot


- This repository provides the customized turtlebot setup of the tams laboratory. The turtlebots have an extra laser scanner under the top plate.

- All dependency packages are list in: https://github.com/TAMS-Group/rosinstalls/blob/master/noetic-turtlebot.rosinstall

---

## Usage bringup

To bring up the turtlebot including the mobile base, the kobuki auto docking and the sensors you can use:

```
roslaunch tams_turtlebot_bringup tams_turtlebot.launch
```

To bring up the same things with navigation including the tams map and optional x y z initial poses use:

```
roslaunch tams_turtlebot_bringup tams_turtlebot_navigation.launch
```

To start tams_turtlebot_navogation with multimaster and in the TURTLEBOT_NAME namespace use:

```
roslaunch tams_turtlebot_bringup tams_turtlebot_lab.launch
```

---

## Usage navigation

The following launch file starts the navigation, you have to set the map argument. map_navigation is an optional argument for a navigation map. Before you use this you should start the tams_turtlebot.launch file.

```
roslaunch tams_turtlebot_navigation navigation.launch map:=/path_to_map
```

To start the navigation with the tams map but also without tams_turtlebot.launch use: 

```
roslaunch tams_turtlebot_navigation navigation_tams_floor.launch
```

For the gmapping, to record a map, use the following file. This one starts the tams_turtlebot.launch, 
you don't have to start any other file:

```
roslaunch tams_turtlebot_navigation gmapping.launch
```

---

## Different laser scanner

We use two different laser scanner in our lab, the hokuyo 04lx and the hokuyo 30lx. To specify one of these you have to set the environment variable `TURTLEBOT_LASER` to `"hokuyo_04lx"` or `"hokuyo_30lx"` in `/etc/environment`.
