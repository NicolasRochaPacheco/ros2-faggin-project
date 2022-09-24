# ROS2: Faggin Project
This project consists of testing if it is worth to pack ROS2 applications using `apt` and `snap`. The test will consist of four nodes that are programmed using Python and C++. The idea is to test how much overhead is obtained when using a packaged application against a typical ROS2 environment. The metrics to evaluate are:

- Latency between nodes. This will be measured by logging the time when messages are sent and received.
- Computer usage. The average CPU usage for the nodes will be reported.
- Memory usage. The average memory usage for the nodes will be reported.

Additional qualitative measurements will be taken into account.

## Nodes
The comparison will make use of the following four nodes.
- Random start, goal and obstacles in a matrix. (2, C++)
- Path planning. (4, C++)
- Webcam/video feed. (1, Python)
- Object recognition. (3, Python)


## Naming
Named in honor of Federico Faggin, main designer of the Intel 4004.


## Development Steps
This is a personal checklist to keep myself organized during development. 
- [ ] **Setup the repositories:** Have the Faggin project as the main repo. You will need the main project repo and four additional repos for each of the nodes.
- [ ] **Devcontainer:** have a dev-container to develop the nodes. You will develop the nodes under a typical ROS2 development environment.
- [ ] **Nodes:** develop the nodes for them to work fine to prevent inducing biases into the comparison.
- [ ] **Packaging pipelines:** there should be an easy way to package the nodes into each of the managers. You should document the process as a qualitative result.
- [ ] **Production environment:** have an environment that would emulate the basics to install the application.
- [ ] **Acquire the metrics:** and do the comparison between them. This should be a nice start for a discussion with you fruity fellows.