# BlendArMocap (Community Fork)

> **This is a community-maintained fork of the original BlendArMocap by Denys Hsu (cgtinker).**
>
> The original author discontinued the project, and we at [Eduwaka](https://github.com/Eduwaka) have forked it to ensure its powerful capabilities remain available and continue to evolve. Our goal is to maintain this tool for our internal animation pipeline and for the benefit of the entire Blender community.
>
> We recognize we may not be the only active home for this project. We are enthusiastic about collaborating with other developers and forks to merge improvements and bring this amazing tool to its full potential.
>
> [Original Repository Link](https://github.com/cgtinker/BlendArMocap)

BlendArMocap is a Blender addon that enables real-time, markerless motion capture using Google’s [MediaPipe](https://google.github.io/mediapipe/) framework. The primary goal of the addon is to efficiently capture human motion from a webcam or video file and transfer it to a character rig inside Blender.

For more detailed information, please refer to the original [documentation](https://cgtinker.github.io/BlendArMocap/), which we aim to update over time.

### Features
- Real-time pose, hand, and face tracking directly within Blender's viewport using MediaPipe.
- Calculation of bone rotations at runtime to drive character rigs.
- Import functionality for session data from the [Freemocap](https://freemocap.org) project.
- A flexible transfer system to map motion capture data to different character rigs.
- Official out-of-the-box support for Blender's standard [Rigify](https://docs.blender.org/manual/en/latest/addons/rigging/rigify/index.html) rigs.

---
### Getting Started

#### 1. Installation
Install the addon from the `.zip` file in Blender's preferences (`Edit > Preferences > Add-ons > Install`).

#### 2. Installing Dependencies
**Caution:** This addon requires external Python libraries (`mediapipe`, `opencv-python`, `numpy`).
- After enabling the addon, a panel will appear in its preferences.
- Click the `Install Dependencies` button to attempt an automatic installation.
- **This may require you to run Blender with administrator/elevated privileges.**
- If the automatic installation fails, you may need to install the dependencies manually into Blender's Python environment. This is often the first "Frankenstein" step in getting a complex tool like this integrated into your pipeline.

### How It Works

#### MediaPipe Detection
Run MediaPipe within Blender to detect pose, hand, and face landmarks from a webcam stream or a pre-recorded video. BlendArMocap generates a control rig of "Empty" objects in real-time that mirror the detected motion.

#### Freemocap Import
Import mocap data saved from a [Freemocap](https://freemocap.org) session. Simply point the addon to the session directory and click the import button.

#### Transfer to Your Rig
The power of this tool lies in its retargeting system. While it works with Rigify rigs by default, you can make it work with *any* rig (like our Edubot mascot!).
1.  The addon generates mapping objects (e.g., in a collection named `cgt_HANDS`).
2.  You use Blender's native **Constraints** (`Copy Location`, `Copy Rotation`) to link your own character rig's bones or IK targets to these mapping objects.
3.  You can save these new mappings as a reusable configuration for your character.

---
### Our Vision and How to Contribute
Our immediate goals are to ensure stability and maintain compatibility with modern versions of Blender. We encourage community contributions to help us:
- Fix bugs and improve performance.
- Create and share new rig configurations.
- Update documentation.

The best way to contribute is by opening an **Issue** to report a bug or suggest a feature, or by submitting a **Pull Request** with your proposed improvements.

### License and Original Author
**This project is, and will remain, under its original license: GNU General Public License v3.0.**

All credit for this incredible tool goes to its original creator, **Denys Hsu (cgtinker)**. We are building upon the foundation they generously provided to the open-source community.

The GPL-3.0 license means this program is free software: you can redistribute it and/or modify it. This program is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY.

You should have received a copy of the GNU General Public License along with this program. If not, see <http://www.gnu.org/licenses/>.

*Original Copyright (C) Denys Hsu - cgtinker, cgtinker.com*
