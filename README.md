# gcp_test_ai2thor
This project is going to test AI2-THOR running speed in a Compute Engine on Google Clound Platform. The configured Compute Engine has 16x vCores and 2x Nvidia K80  GPUs.

# Test script
The test script can be used to start multiple AI2THOR instances. Following parameters controll how to run this instances.

```
'--multi-processes','-mp': instances are started in separate processes
'--num-envs' : how many instances will be started, default 1
'--gpus' : how many GPUs are used, default 1
'--steps': how many steps AI2THOR environment run random step, default 1000.
```

# Preparation
Please install AI2THOR environment by 
```
pip install ai2thor
```

More details please refer to AI2THOR project [https://github.com/allenai/ai2thor]
In case for multiple GPUs, please run multiple X-Server for each GPU card. I wrote a blog [https://medium.com/@etendue2013/how-to-run-ai2-thor-simulation-fast-with-google-cloud-platform-gcp-c9fcde213a4a] to describe necessary steps. 

# Test examples
## run multiple instance e.g. 4 in separate processes
```
python test.py -mp --num-envs 4
```

## run multiple instance e.g. 4 in separate processes on multiple GPUs, e.g. 2
```
python test.py -mp --num-envs 4 --gpus 2
```

## run multiple instance e.g. 4 in 1 process
```
python test.py --num-envs 4
```

Please see bench result in my blog.
