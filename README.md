# Wildfire RGBD Camera Test
This repository contains a feasibility study evaluating RGBD cameras for UAV obstacle avoidance in wildfire monitoring applications.
## Overview
The project assesses whether depth cameras can serve as a viable alternative to LiDAR for real-time obstacle avoidance during autonomous wildfire suppression missions. The implementation uses Vector Field Histogram (VFH) for obstacle avoidance with depth-derived point clouds.
## Environment Setup
### Custom Unreal Engine Environment
A geographically representative simulation environment was created using the following workflow:

Terrain data extracted from OpenStreetMap (OSM)
Three-dimensional terrain geometry generated in Blender
Assets imported into Unreal Engine with UAV actor for MATLAB simulation interface

The resulting environment replicates operational conditions for realistic mission testing.
## MATLAB Simulation
### Sensor Configuration

RGBD Camera: Depth camera added to UAV model
Point Cloud Conversion: Depth output converted to point cloud format using MATLAB's pointCloudFromDepth function
Obstacle Avoidance: VFH algorithm processes point cloud data for real-time navigation

### VFH Controller Tuning
The VFH controller was tuned using weight parameters:

W₁: Target direction weight
W₂: Current heading weight
W₃: Previous heading weight

Tuning focused on balancing responsiveness and stability for safe obstacle avoidance while maintaining forward progress toward targets.
Testing Integration

Connected to QGroundControl for mission planning and monitoring
Test scripts evaluate VFH performance across multiple weight configurations
Mission divided into phases with varying obstacle densities

## Key Findings

Depth-camera-derived point clouds provide sufficiently reliable obstacle information for VFH-based avoidance
RGBD sensing demonstrated viability as an alternative to LiDAR for short-range obstacle avoidance
Optimal performance achieved with weight ratios W₁:(W₂+W₃) in the range 1.20–1.27

## Requirements

MATLAB with UAV Toolbox
Unreal Engine
Blender (for environment modifications)
QGroundControl
ArduPilot (optional)


Load the custom Unreal Engine environment
Run MATLAB simulation scripts with desired VFH parameters
Connect to QGroundControl for real-time mission visualisation
Analyse performance metrics across flight phases
