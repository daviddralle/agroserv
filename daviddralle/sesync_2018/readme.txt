
Run the following lines of code in terminal to download an Ubuntu Linux docker that can run the Python notebooks in this workspace folder. You can interact with the Docker through your web browser at the web address printed in the terminal after you run this command. It should open in workspace folder that you define in the "export" line. Make sure to edit the first line of the commands below to point the WORKSPACE variable to the actual location of the workspace folder on your machine. In the Mac example below, the folder is located on the Desktop of my machine. 

For Mac/Linux: 

export WORKSPACE=${HOME}/path/to/workspace
docker run -i -t -p 8888:8888 -v "$WORKSPACE:/workspace" daviddralle/sesync2018 /bin/bash -c "cd /workspace && pip install linearmodels && jupyter notebook --ip='*' --port=8888 --no-browser --allow-root"


For windows: 

set "HOME=%HOMEDRIVE%%HOMEPATH%"
set "WORKSPACE=%HOME%\path\to\workspace"
docker run -i -t -p 8888:8888 -v "%WORKSPACE%:/workspace" daviddralle/sesync2018 /bin/bash -c "cd /workspace && pip install linearmodels && jupyter notebook --ip='*' --port=8888 --no-browser --allow-root"