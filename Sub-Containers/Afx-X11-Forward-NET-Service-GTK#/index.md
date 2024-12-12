---
layout: default_c
RefPages:
 - howto_create_a_dev_container   
--- 


# What
Sub container for the ***'APP-X11-Forward-Development-Template-Stack'*** development stack. Containing a project template for **.NET Core 8.x** in combination with **GTK 4.0**

> For more information about setting up this stack and/or this sub-container , visit the [main documentation page](https://nicojane.github.io/APP-X11-Forward-Development-Template-Stack/). You can find other Docker Template Stack (DTS) containers  [here.](https://nicojane.github.io/Docker-Template-Stacks-Home/)
>
> <sub> &nbsp;&nbsp;&nbsp;&nbsp; *Is this a local repository project? If so, use this local link to access the [main page](./index) file. <sub>
> <br>


### Quick setup .NET Gtk sub container
If you have previously installed this (or a similar) AFX foreward sub container, you can use these 'quick setup steps'. Otherwise please first read the **main documentation page**.
1. **Create the WSLs**{: style="color:green; "} &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  <small>*(if not yet done*) </small>      
In case you don't have the **WSL** container, open CMD in the folder: ***'APP-X11-Forward-Development-Template-Stack\Base-Container\Afx-Base-Service\'*** and execute: 
<pre class="nje-cmd-one-line"> wsl --import Ubuntu-docker-App-X11-Win32Dev ./wsl2-distro  "install.tar.gz"  </pre>

> *Remark:*{: style="color: black;font-size:13px; "} <br>
> <small>By default the WSL image is created in the sub folder of the current directory (./wsl2-distro) you may choose to store this image more **central**, for example like in 'd:\wsl-data\afx-stacks', this way you can **reuse** this WSL distribution for different **AFX stacks**  <br></small>


2. **Create the base container**{: style="color:green; "} &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  <small>*(if not yet done*) </small> <br>
Create docker base container (in folder: 'Afx-Base-Service')
<pre class="nje-cmd-one-line">docker-compose -f  compose_app_forward_x11_base.yml up -d --build --force-recreate  --remove-orphans </pre><br>

3. ***Create the sub container***{: style="color:green; "} <br>
Create the .NET GTK Sub container (in folder: 'Afx-X11-Forward-NET-Service-GTK#'): 
<pre class="nje-cmd-one-line">docker-compose -f compose_net_x11_gtksharp_project.yml up -d --build --force-recreate --remove-orphans  </pre><br>
 
4. **Start the Docker sub container via the WSL**{: style="color:green; "} <small>*(optional*) </small> <br>
Execute the following commands: 
<pre class="nje-cmd-multi-line">wsl -d Ubuntu-docker-App-X11-Win32Dev 
docker exec -it afx-x11-forward-net-service-gtk-axf-dotnet-gtksharp-container-1 /bin/bash 
</pre>
> *Warning:*{: style="color: red;font-size:13px; "} <br>
> <small>When  the container cannot be found, restart the Docker app and ensure WSL integration is enabled in Docker settings! <br></small>


5. **Start the sub-container in Visual Studio Code**{: style="color:green; "}<br>
Install the following extension(s) in the container
<pre class="nje-cmd-multi-line">code --install-extension ms-dotnettools.csharp
code --install-extension ms-dotnettools.csdevkit
~~code --install-extensionms-dotnettools.vscode-dotnet-runtime~~
</pre>
<br><br>


<details closed>  
  <summary class="clickable-summary">
  <span  class="summary-icon"></span> 
  Side note: Preview Markdown Files(.md)
  </summary> 	<!-- On same line is failure, Don't indent the following Markdown lines!  -->

> <br>
> 
> ### Preview Markdown Files(.md)
>
>To preview the Markdown (.md) files in this project, one of the best solutions is to open these files in Visual Studio Code (VSC) and install the plugin: **Markdown Preview GitHub Styling** (Tested with version 2.04). Other plugins, or plugins for other programs, may not always work correctly with the file links in the documentation. I use the file link syntax supported by GitHub (Jekyll), which is also compatible with the above-mentioned plugin.
>
> To display the Preview screen in VSC: 
>- Ensure that you are **not** working in ***Restricted mode***.
>- Click on the "file.md" tab and choose: "Open preview." 
>- Alternatively, you can click the 'Open Preview to the Side' button at the top right. 
>
><br>
<a href="https://github.com/mjbvz/vscode-github-markdown-preview-style" target="_blank">Click here for more information on the Markdown Preview GitHub Styling plugin</a>
</details>


<br><br>
*Version: 1.0*{: style="color:gray;font-size:8px;"}