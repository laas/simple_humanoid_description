# Simple Humanoid Description

[![Pipeline status](https://gitlab.laas.fr/laas/simple_humanoid_description/badges/master/pipeline.svg)](https://gitlab.laas.fr/laas/simple_humanoid_description/commits/master)
[![Coverage report](https://gitlab.laas.fr/laas/simple_humanoid_description/badges/master/coverage.svg?job=doc-coverage)](https://gepettoweb.laas.fr/doc/laas/simple_humanoid_description/master/coverage/)
[![pre-commit.ci status](https://results.pre-commit.ci/badge/github/laas/simple_humanoid_description/master.svg)](https://results.pre-commit.ci/latest/github/laas/simple_humanoid_description)

`simple_humanoid_description` provides URDF, SRDF model information
for the simple_humnaoid robot.

## URDF

The URDF file is only available for the default model. It contains the
kinematic model of the robot.
No meshes are present inside this repository

## SRDF

The SRDF file is only available for the default model. It contains the
collision pairs which can be safely disabled and the default robot
configuration called "half_sitting".
It also contains adiditonnal information like the position of the ankle in the
foot frame and the size of the foot.

## Code API

This package does not provide API.
