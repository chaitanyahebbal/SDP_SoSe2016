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

#### Additional dependencies

Additional Git repositories can be included in the
[```dependencies.rosinstall```](travis/dependencies.rosinstall) file. Detailed
format instruction can be found [here](http://docs.ros.org/independent/api/rosinstall/html/rosinstall_file_format.html).
