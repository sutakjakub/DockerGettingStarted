# DockerGettingStarted
Getting started with docker.

## Prereq
> netcore 3.1 sdk (windows): https://dotnet.microsoft.com/download/dotnet-core/3.1

## Sample1_netcore_console

_Tutorial from: https://docs.microsoft.com/cs-cz/dotnet/core/docker/build-container?tabs=windows_

#### 1. Creates new console app called NetCore.Docker:
  
`dotnet new console -o App -n NetCore.Docker`

#### 2. Creates image from Dockerfile:
  
`docker build -t counter-image -f Dockerfile .`

#### 3. Show docker images: 
  
`docker images`

#### 4. Creates container: 
  
`docker create --name core-counter counter-image`

#### 5. Attach container: 
  
`docker attach --sig-proxy=false core-counter`

#### 6. Show attached containers: 
  
`docker ps`

#### 7. Starts container: 
  
`docker start core-counter`

#### 8. Stops container: 
  
`docker stop core-counter`

#### 9. Removes container: 
  
`docker core-counter`

#### 10. Starts container without attaching with parameter. After stop container will be deleted. 
  
`docker run -it --rm counter-image 3`

## Sample2_aspnetcore_from_repo

_Tutorial from: https://docs.microsoft.com/cs-cz/dotnet/core/docker/build-container?tabs=windows_

If command `docker exec aspnetcore_sample ipconfig` is not working for you (_OCI runtime exec failed: exec failed: container_linux.go:295: starting container process caused "exec: \"ipconfig\": executable file not found in $PATH": unknown_) then be sure that you have set "switching to Windows container". You do this in the docker settings that run in windows as service.