# ROS_tutorial_sample_code

```
alias eb='nano ~/.bashrc'
alias sb='source ~/.bashrc'
alias gs='git status'
alias gp='git pull'
alias cw='cd ~/catkin_ws'
alias cs='cd ~/catkin_ws/src'
alias cm='cd ~/catkin_ws && catkin_make'
source /opt/ros/noetic/setup.bash
source ~/catkin_ws/devel/setup.bash
export TURTLEBOT3_MODEL=burger

# Check and clean ROS log files if they exceed a certain size (e.g., 1GB)
LOG_LIMIT=3000000 # Set the size limit (in KB) for logs, e.g., 1GB = 1,000,000 KB
if [ -d ~/.ros/log ]; then  # 確保 log 目錄存在
    LOG_SIZE=$(du -sk ~/.ros/log | awk '{print $1}')
    if [ "$LOG_SIZE" -ge "$LOG_LIMIT" ]; then
        echo "ROS log directory exceeds $LOG_LIMIT KB. Running rosclean..."
        rosclean purge -y
    fi
fi

export ROBOT_MODEL=turtlebot3
#export ROBOT_MODEL=minibot
export ROS_MASTER_URI=http://10.0.0.2:11311
export ROS_HOSTNAME=10.0.0.2
#export ROS_MASTER_URI=http://localhost:11311
#export ROS_HOSTNAME=localhost
```
