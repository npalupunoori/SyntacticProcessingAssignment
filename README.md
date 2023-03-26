# Template Repository name

Description

## Tensorflow-docker-template
This is a template for starting a tensorflow docker, with local host directory linked as volume.
This mounting of volume helps us to share Jupyter notebooks via GIT with out sharing the full docker.

Before starting please make sure steps mentioned in  [tensorflow docker](https://www.tensorflow.org/install/docker) are followed.


[docker-compose.yml](docker-compose.yml) file is set to use latest release of [tensorflow docker](https://hub.docker.com/r/tensorflow/tensorflow/).  


## Starting a docker
Check out this repo. In windows powershell change directory to checkout folder.

```
docker compose up
```

```console
PS Tensorflow-Docker-template> docker compose up

[+] Running 2/2
 - Network tensorflow-docker-template_jupyter  Created                                                             0.0s
 - Container tensorflow-gpu-template           Created                                                             0.1s
Attaching to tensorflow-gpu-template
tensorflow-gpu-template  | [I 15:26:15.747 NotebookApp] Writing notebook server cookie secret to /root/.local/share/jupyter/runtime/notebook_cookie_secret
tensorflow-gpu-template  | [I 15:26:15.932 NotebookApp] Serving notebooks from local directory: /tf
tensorflow-gpu-template  | [I 15:26:15.933 NotebookApp] Jupyter Notebook 6.5.2 is running at:
tensorflow-gpu-template  | [I 15:26:15.933 NotebookApp] http://34bb3b625909:8888/?token=78921878efa98c221bf563e52e7c3a72bf8b081748a5a227
tensorflow-gpu-template  | [I 15:26:15.933 NotebookApp]  or http://127.0.0.1:8888/?token=78921878efa98c221bf563e52e7c3a72bf8b081748a5a227
tensorflow-gpu-template  | [I 15:26:15.933 NotebookApp] Use Control-C to stop this server and shut down all kernels (twice to skip confirmation).
tensorflow-gpu-template  | [C 15:26:15.962 NotebookApp]
tensorflow-gpu-template  |
tensorflow-gpu-template  |     To access the notebook, open this file in a browser:
tensorflow-gpu-template  |         file:///root/.local/share/jupyter/runtime/nbserver-1-open.html
tensorflow-gpu-template  |     Or copy and paste one of these URLs:
tensorflow-gpu-template  |         http://34bb3b625909:8888/?token=78921878efa98c221bf563e52e7c3a72bf8b081748a5a227
tensorflow-gpu-template  |      or http://127.0.0.1:8888/?token=78921878efa98c221bf563e52e7c3a72bf8b081748a5a227
```
Copy the http link from the above link to a web browser to start Jupyter notebook.

Once in Jupyter notebook there will be a folder called `host_folder` which has all the contents of current folder 
```
C:.
│   docker-compose.yml
├───data
│       date.md
└───notebooks
        problemStatement.md
        TestGPU.ipynb
```

* This will start a docker in the foreground, Disadvantage of this is if terminal is closed, docker is closed. 

### Start docker in background

To run docker in the background

```
docker compose up -d
```

```console
PS Tensorflow-Docker-template> docker compose up -d

[+] Running 2/2
 - Network tensorflow-docker-template_jupyter  Created                                                             0.0s
 - Container tensorflow-gpu-template           Started
 >
```
This will start the docker in background. To get the http link open docker desktop as in option 1 run follwong command
```
docker compose logs
```

```console
PS Tensorflow-Docker-template> docker compose logs

tensorflow-gpu-template  | [I 15:35:59.479 NotebookApp] Writing notebook server cookie secret to /root/.local/share/jupyter/runtime/notebook_cookie_secret
tensorflow-gpu-template  | [I 15:35:59.668 NotebookApp] Serving notebooks from local directory: /tf
tensorflow-gpu-template  | [I 15:35:59.668 NotebookApp] Jupyter Notebook 6.5.2 is running at:
tensorflow-gpu-template  | [I 15:35:59.668 NotebookApp] http://ed6a8be59161:8888/?token=e7c42c611a3d30692153aacd998508217dda72f1d0821c75
tensorflow-gpu-template  | [I 15:35:59.668 NotebookApp]  or http://127.0.0.1:8888/?token=e7c42c611a3d30692153aacd998508217dda72f1d0821c75
tensorflow-gpu-template  | [I 15:35:59.668 NotebookApp] Use Control-C to stop this server and shut down all kernels (twice to skip confirmation).
tensorflow-gpu-template  | [C 15:35:59.695 NotebookApp]
tensorflow-gpu-template  |
tensorflow-gpu-template  |     To access the notebook, open this file in a browser:
tensorflow-gpu-template  |         file:///root/.local/share/jupyter/runtime/nbserver-1-open.html
tensorflow-gpu-template  |     Or copy and paste one of these URLs:
tensorflow-gpu-template  |         http://ed6a8be59161:8888/?token=e7c42c611a3d30692153aacd998508217dda72f1d0821c75
tensorflow-gpu-template  |      or http://127.0.0.1:8888/?token=e7c42c611a3d30692153aacd998508217dda72f1d0821c75
>
```
