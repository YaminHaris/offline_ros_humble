# 1. Download the complete repository from GitHub on the internet PC
git clone https://github.com/YaminHaris/offline_ros_humble.git
cd offline_ros_humble

# 2. Reassemble the 20 split parts back into the single 1.8 GB tarball
cat ros2_offline_part_* > ros2_gazebo_harmonic_offline.tar.gz

# 3. Transfer this single file over your intranet/network to the offline computer
# [Perform the network copy here, then run the rest on the target offline machine]

# 4. Extract the offline bundle package on the target PC
tar -xvzf ros2_gazebo_harmonic_offline.tar.gz
cd ros2_offline_bundle

# 5. Fix the shebang typo in your install script if you haven't yet
sed -i 's|#!/bash/bin|#!/bin/bash|g' install_offline.sh

# 6. Run your plug-and-play installation script
./install_offline.sh

# 7. Permanently update your environment paths
echo "source /opt/ros/humble/setup.bash" >> ~/.bashrc
source ~/.bashrc
