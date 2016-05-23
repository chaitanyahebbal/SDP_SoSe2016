## Travis usage

#### Configuration File

File [```.travis.yml```](.travis.yml) contains configuration for TRAVIS. This
file currently instructs Travis to:
* create a Ubuntu trusty VM on the [Travis CI](https://travis-ci.org/) server
* create a ROS workspace and symbolic link of the repository in the ```src```
folder
* install ROS and dependencies by running ```rosdep install``` on all the
```package.xml``` files
* limits build to only ```master``` branch

#### Convention Checking
* Launch files and package dependencies are checked through running ```roslaunch_add_file_check```, specified in ```CMakeLists.txt```.
* ```catkin run_tests``` will run ```roslaunch_add_file_check``` without returning an error like ```catkin test```, but shows message of the actual error. Look for ```FAILURE``` tag in the output message.
* ```roslint``` is evoked by adding ```--make-args roslint``` to ```catkin build```

#### Additional dependencies

Additional Git repositories can be included in the
[```dependencies.rosinstall```](travis/dependencies.rosinstall) file. Detailed
format instruction can be found [here](http://docs.ros.org/independent/api/rosinstall/html/rosinstall_file_format.html).
