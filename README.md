# Ubiquiti-Mfi-Controller
Ubiquiti-Mfi-Controller

Docker folder:
- contains the Docker file needed to build the image
- builds version 2.1.11 of the controller, if you need this changed you can change it inside the Dockerfile

docker build  -t mfi01 .

Kubernetes folder:
- contains the files needed to build a kubernetes deployment
- mongodb and unifi storages are stored on PV
- the initial build was done on an inhouse k8s deployment with storage on Glusterfs; if you are deploying outside Glusterfs please replace the PV yaml files with corect statements
- mfi service is been exposed via local ip feel free to replace the 10.20.0.11 with whatever makes sense in your deployment

After the initial start go to your persistent volume on the disk and locate system.properties. Add "is_default=true" so it triggers the initial wizzard; no need to change the value as the setup will replace true with false after the wizzard ends.
