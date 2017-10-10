# Net2Plan-OLE Report
## Introduction
Net2Plan is a Java developed tool for the planning, optimization and evaluation of communication networks. It provides a GUI to create topologies  and it also allows users to develop their own algorithms and reports and deploy and test them in a simulated network. 
Among the examples provided by Net2Plan, there is a report for WDM line engineering networks that uses the calculations provided by OLE, based on the GNPY model developed by the Politecnico di Torino.

## Getting started
These instructions will get you a copy of the project up and running on your local machine for development and testing purposes.
### Prerequisites
* [JRE installed] (http://www.oracle.com/technetwork/pt/java/javase/downloads/jdk8-downloads-2133151.html)
* Python 3
	* For Windows users:
		* Download installer from [the Python website] (https://www.python.org/downloads/). Make sure that the options to install pip and add Python3 to the system path are marked.
		* Download numpy and scipy [wheels] (http://www.lfd.uci.edu/~gohlke/pythonlibs/). Select the proper wheel for your SO and Python. 
		`For example, for a Windows x64 and Python v3.6, should be
*numpy-1.13.3+mkl-cp36-cp36m-win_amd64.whl* and *scipy-1.0.0rc1-cp36-cp36m-win_amd64.whl*`
		* Install matplotlib from pip (note that the command could be 'python' or 'python3' depending on your system).
		`python3 -m pip install matplotlib`
	* For Unix:
	```
	sudo apt-get install python3 
	sudo apt-get install python3-pip
	sudo python3 -m pip install matplotlib
	sudo python3 -m pip install numpy
	sudo python3 -m pip install scipy
	```

### Installation instructions 
#### GNPY
* Download [GNPY from GitHub] (https://github.com/Telecominfraproject/gnpy/tree/feature_polito1).
* Unpack it in a folder
* Install it (note that the command could be 'python' or 'python3' depending on your system): 
`python3 -m pip install {path-to-GNPY}`
#### Net2Plan
* Download [Net2Plan from GitHub] (https://github.com/girtel/Net2Plan/releases)
* Unpack it in a folder
* To run it, click in Net2Plan.jar or, from console
`java -jar {Net2Plan-folder}/Net2Plan.jar` 
* On the upper menu, select Tools -> Offline network design & Online network simulation

## Brief users' guide to Net2Plan GUI
### Hello World: running TIP Report 
* Download example topology from github.
* Load it by using the "Load a network design" button.
* Download .jar report.
* On the network control window, go to the 'View reports' tab and load it.
* Change ole_GNPY_basePath input parameter to your {GNPY-path}.
* Change pythonCommand input parameter to 'python' or 'python3' depending on the Python3 command for your computer.
* Click on Show and wait a few seconds.
* Close plot windows.
* Click on 'View in navigator' to view the full report.

### Useful tips
* To load a network from a n2p file, click on ![picture alt](https://raw.githubusercontent.com/girtel/Net2Plan/develop/Net2Plan-GUI/Net2Plan-GUI-Plugins/Net2Plan-NetworkDesign/src/main/resources/resources/gui/icon_loadDesign.png "Load a network design")
* To create a new network, on the network control window go to the 'View/Edit network state' tab and then in the 'Layers' tab write 'WDM' (without quotes) in the Name field.
> if it is not shown, you can access the control window by clicking this icon ![picture alt](https://raw.githubusercontent.com/girtel/Net2Plan/develop/Net2Plan-GUI/Net2Plan-GUI-Plugins/Net2Plan-NetworkDesign/src/main/resources/resources/gui/showControl.png "Show control window")
* To add a node, right click on the drawing panel and select 'Add node here'.
* To add links, simply click on the origin node and drag to the destination.
* To edit link parameters, on the network control window, go to the 'View/Edit network state' tab and then the 'Links' tab. You can edit anything by double clicking its cell.
* To edit the attributes of more than one link, select the link rows that you want and then right click > 'Edit attributes from selected elements'. Specifications of the attribute syntaxis will be given in any algorithm or report provided.
* To run a algorithm, on the network control window, go to the 'Offline algorithms' tab and load the `.class` from your computer. Then edit the parameters as you wish and click Execute.
* To run a report, on the network control window, go to the 'View reports' tab and the `.class` from your computer. Then edit the parameters as you wish and click Show. You will see the results then, and you can access them from a browser by the 'View in navigator' button.
```
**For Report_WDM_lineEngineering_TIP**
The link attributes will be:
	* edfaPositions_km
	* edfaGains_dB
	* edfaNoiseFigures_dB
	* pcPositions_dB
	* pcLosses_dB
	* fiberTypes
Each one will have values separated by spaces. All values will be written in plain text, without quotation marks.
```
