# state_cpp_msg

## example code
```c
#include "state_cpp_msg/MissionPlannerAction.h"

MissionNode::MissionNode()
    : as_(nh_, "action_name", boost::bind(&MissionNode::actionCallback, this, _1), false)
{
    nh_ = ros::NodeHandle("~");

	as_.start();
}

void MissionNode::actionCallback(const state_cpp_msg::MissionPlannerGoalConstPtr& goal)
{
    state_cpp_msg::MissionPlannerResult result;
	as_.setSucceeded(result);
}
```

