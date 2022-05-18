## Robin
**Robin** is a school project aimed to use a machine learning algorithm to localize and move a [TurtleBot3]("[turtlebot.com](http://wiki.ros.org/turtlebot3)").
Robin stands for _Robin Orientation By Internet Network_. The name comes from the "robin" bird species, which are able to return home wherever they are.

### Hardware

TurtleBot3 is a new generation mobile robot that is modular, compact and customizable. It can be programmed using the open-source O.S. [**ROS**](https://www.ros.org/). It is based on the raspberry pi computer. 

[Image](https://github.com/ROBIN-Itis-Delpozzo/ROBIN-Itis-Delpozzo/tree/main/img/logo_turtlebot3.png)

In addiction to it we use a [**lidar**](https://en.wikipedia.org/wiki/Lidar) to read the surroundings and detect obstacles.

[Image](https://github.com/ROBIN-Itis-Delpozzo/ROBIN-Itis-Delpozzo/tree/main/img/turtlebot3.png)

### Software

#### - requirements
    - Python 3.0 or more
    - Libraries:
        - Pandas
        - Numpy
        - Scapy
        - Sklearn
        - Joblib
    - a network card
    
#### - create the database

The first thing we did was creating our own database to train the neural network. To accomplish this necessity we wrote a python program which detects all the important networks around him and store their signal strenght into a .csv file (_mydataset.csv_). The dataset has this structure:
  
  ```
  | location_name | wifi_1 | wifi_2 | wifi_3 | ... | wifi_n |
  ```
This script that make this is named _localize_wifi.py_.

#### - train the model

The second step was creating a machine learning model. We choose to write it using Jupyter notebook and the library [**scikit-learn**](https://scikit-learn.org/stable/index.html). 

We imported the dataset into a Pandas Dataframe and then we made some graphs to have a better understanding of the data quality.
The following one represent the distribution of the signals strenght (x axis) in a certain zone.

[Image](https://github.com/ROBIN-Itis-Delpozzo/ROBIN-Itis-Delpozzo/tree/main/img/graph1.png)

The next one represent the strenght of a given network in each zone.

[Image](https://github.com/ROBIN-Itis-Delpozzo/ROBIN-Itis-Delpozzo/tree/main/img/graph2.png)
