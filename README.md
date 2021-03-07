# RoboND-MapMyWorld

---

### Dependencies

- ROS Kinetic
- CMake 2.8
- unzip


### Installing ROS dependencies

```bash
$ cd <repo root>/catkin_ws
$ sudo apt update
$ rosdep install --from-paths ./src --ignore-packages-from-source -y
```

### Compiling the Program

```bash
$ cd <repo root>/catkin_ws
$ catkin_make
```

### Running `RTAB-Map` mapping

- To create the map file from scatch.

    ```bash
    $ cd <repo root>/catkin_ws/src
    $ sh rtab-mapping.sh
    ```

- In the `teleop_twist_keyboard` terminal, drive the robot according the path illustrated below:

    ![alt text](images/MappingPath.png)

### Load the pre-created `RTAB-Map` map

- To load the pre-created `RTAB-Map` map file

    ```bash
    $ cd <repo root>/catkin_ws/src/my_robot/rtabmap
    $ unzip rtabmap.db.zip
    ```

-  To view the outcome of `RTAB-Map` 

    ```bash
    $ cd <repo root>/catkin_ws/src/my_robot/rtabmap
    $ rtabmap-databaseViewer rtabmap.db
    ```
- Following image shows the number of global loop closure is `11`.

    ![alt text](images/NumberOfGlobalLoopClosure.png)

- Following image shows the two scenes (`102` and `274`) with **loop closure**. This is shown by `Type`= `1 (Loop closure)` in the `Constraints View` window.

    ![alt text](images/TwoScenesWithLoopClosure.png)

- Following image shows the two scenes (`102` and `279`)  with **no loop closure**. This is shown in `Type`= `99 (Undefined)` in the `Constraints View` window.

    ![alt text](images/TwoScenesWithNoLoopClosure.png)



### Running `RTAB-Map` localization

- Unzip the pre-created `RTAB-Map` map file

    ```bash
    $ cd <repo root>/catkin_ws/src/my_robot/rtabmap
    $ unzip rtabmap.db.zip
    ```

- Run the `rtab-localization` bash file

    ```bash
    $ cd <repo root>/catkin_ws/src
    $ sh rtab-localization.sh
    ```

- In the `teleop_twist_keyboard` terminal, drive the robot according the path illustrated below:

    ![alt text](images/LocalizationPath.png)

- The video demo below shows that the robot started off at the wrong location but managed to localize itself towards the end of path:

    ![alt text](images/demo.gif)