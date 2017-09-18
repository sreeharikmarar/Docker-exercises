### Exercise - 1

* Create a docker container with git installed
* Initialize empty git repository on your local directory using git container


$: docker build -f Dockerfile.git -t sreehari/git .    
$: docker run -v /Users/sreeharikm/test:/test sreehari/git git init    

### Exercise - 2

* Run nginx with custom index html file 

$: docker build -f Dockerfile.nginx -t sreehari/nginx .    
$: docker run -p 80:80 sreehari/nginx    


### Exercise - 3:1

* Create an Image which can run npm install. Create a package.json and copy it inside the image. Run this image and note if the dependencies are installed every time. Why?    
* Change the Image to install the dependencies in the Image itself.    
* Share the node_modules folder when running the container so that npm runs inside the container but the dependencies get installed outside.    

$: docker build Dockerfile.npm -t sreehari/npm .     
$: docker run sreehari/npm npm install              // installs dependencies every time     
$: docker run -v /Users/sreeharikm/Docker/node_modules:/app/node_modules sreehari/npm npm install // uses packages from local node_modules. doesnt installs each time    


### Exercise - 3:2

* Take the source at https://github.com/steotia/sample-nodejs and dockerize it to run on port 3000.    

$: docker build Dockerfile.nodeapp -t sreehari/nodeapp .    
$: docker run -p 3000:3000 sreehari/nodeapp    
