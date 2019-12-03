ML model GKE Demo
======
Creating a GKE cluster, deploying the "ich" ML model on it and running the gRPC client


## Requirements

- python3  
- pip3  
- gcloud SDK

##Installation

-  Use the package manager pip to install the requirements from the file.  
`$ pip3 install -r requirements.txt`

##Usage

- Execute the file named create.sh to create a cluster
`$ bash create.sh`

- Execute the file named run.sh to perform the following operations
`$ bash run.sh`

- Connecting to the cluster  
- Installing NVIDIA GPU device drivers  
- Attaching Load balancer service to expose the ML model deployed

- waiting 60 seconds NVIDIA GPU device drivers to be installed before deploying pods  
- Configuring pods and health-check  
- To view the running pods  
- To view the load balancer IP  

###After the execution is completed, use the following commands###

- To get the status of pods after deploying them
`$ kubectl get pods`

- To get the status and IP (endpoint) of the load balancer
`$ kubectl get svc`

- To get the logs of a particular pod
`$ kubectl logs`

- To fetch details about pods such as configuration, status information about the container and Pod.
`$ kubectl describe pod`

- To run the gRPC client  
- move to inference folder  
```$ python3 client_inference.py --image <image_name>  --host <load_balancer_ip> --model <model_name>```

`image_name` = SS_6505-179_CT.nii.gz  
`load_balancer_ip` = IP of load balancer  
`model_name` = ich
