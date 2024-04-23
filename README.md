# e-Merlin Provenance Generation
Scripts for the generation of e-merlin provenance

## Stand-alone Instructions

Install provenance generation software
'''
pip install praetor
'''

Provenance generation settings setup
'''
echo 'PRAETOR="/path/to/provenance/output/directory/"'
'''

Copy the [settings file](https://github.com/uksrc/e-merlin_provenance_generation/blob/main/praetor/praetor_settings_user.py) to /path/to/provenance/output/directory/ and alter as necessary. 

Run the following to execute the pipeline and generate the provenance for the casa6/python3 version:

'''
praetor_run.py python eMERLIN_CASA_pipeline/eMERLIN_CASA_pipeline.py -r calibration
'''

For casa5/python2
'''
praetor_run.py casa -c eMERLIN_CASA_pipeline/eMERLIN_CASA_pipeline.py -r calibration
'''

For further information on installing and running the e-merlin pipeline, please see (here)[https://github.com/e-merlin/eMERLIN_CASA_pipeline/tree/master]

## Testing the generation with Docker

Download, unzip and place the test data from [here](https://www.e-merlin.ac.uk/distribute/CY8/TS8004/TS8004_C_001_20190801/weblog/download.html) into your build directory. 

Build the container from the Dockerfile in this repo

'''
docker build . -t casa/conda
'''

Enable docker to access xterm, if necessary:

'''
xhost +local:docker
'''

Start the container with the run command provided:

'''
./docker_run_command.sh
'''

Run the pipeline with the generation software:

'''
cd /home/TS8004_C_001_20190801
praetor_ruu.py python ../eMERLIN_CASA_pipeline/eMERLIN_CASA_pipeline.py -r calibration
'''


