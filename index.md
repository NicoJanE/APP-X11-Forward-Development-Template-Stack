---
layout: default_c
RefPages:
 - howto_create_a_dev_container
--- 

<small>
<br>
_This file is part of: **App-X11-Forward Development Template Stack**_
_Copyright (c) 2024 Nico Jan Eelhart_
_This source code is licensed under the MIT License found in the  'LICENSE.md' file in the root directory of this source tree._
</small>
<br><br>

# What
This is a Docker Linux (Ubuntu 24.04) template container with GUI output to an X11 server on a Windows host. The container is **designed** for use on a Windows Docker Desktop host, enabling the **development** of **GUI applications** within a **Docker container**. Additionally, the container can be used to run other Linux GUI applications.

This container consists of a **Base Container** and several **Sub Containers**. **The Base Container** is required for any **Sub Container** and provides the infrastructure for outputting GUI data from the Linux application to the X11 server on Windows. The **Sub Containers** contain development environments for GUI application running on Linux. 

**Available Sub Containers**
- A generic .NET container with a basic Command Application template.
- An Avalonia container with Avalonia GUI templates and a custom GUI application template tailored for this stack.

> **For the latest stable release, use the release/1.0 template branch**

## Quick Setup
There are no quick setup instructions for this image. First, you need to install the Base Container/Image, which takes about 20 minutes. After that, you can easily add Sub Containers. Please refer to the document [how to create a development container](./Howtos/howto_create_a_dev_container). which explains the installation of the **Base Container** and any available **Sub Containers**.



