# Twitter-Sentiment-Extraction

### How did I start?

Pull the Kaggle Python Docker image. For any details for the Docker installation see [this blog post](http://blog.kaggle.com/2016/02/05/how-to-get-started-with-data-science-in-containers/) or https://docs.docker.com.

```
$ docker pull kaggle/python  
```

The image is large and therefore it can take some time to download all layers. Once it’s downloaded, you can list the image including the size info: 
```
$ docker image ls kaggle/python
REPOSITORY          TAG                 IMAGE ID            CREATED             SIZE
kaggle/python       latest              09a349977ca7        2 weeks ago         12.5GB
```
You’re now at a point where you can run stuff in the container. Here’s an extra step that will make it super easy: put these lines in your .bashrc file (or the Windows equivalent)
```
kpython(){ docker run -v $PWD:/tmp/working -w=/tmp/working --rm -it kaggle/python python "$@" } ikpython() { docker run -v $PWD:/tmp/working -w=/tmp/working --rm -it kaggle/python ipython } kjupyter() { (sleep 3 && open "http://$(docker-machine ip docker2):8888")& docker run -v $PWD:/tmp/working -w=/tmp/working -p 8888:8888 --rm -it kaggle/python jupyter notebook --no-browser --ip="\*" --notebook-dir=/tmp/working }
```


