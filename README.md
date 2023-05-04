# azure-appservice-win-container
 Azure app service hosting .Net Framework web api in a Windows Core container
## Build
- Open net4-api/net-4api.sln in Visual Studio 2022.
- Right click on the solution and select Build Solution.
`
docker build -t net4api:0.1 -f Dockerfile.build .
docker run -it --rm -p 9999:80 --name manualnet4api net4api:0.1
`
## Publish to Docker hub
`
docker image ls

docker image tag net4api:dev andyvan27/net4api:0.1

docker image push andyvan27/net4api:0.1
`
## Create App Service
- Open Azure portal
- Create resource group
- In the resource group, create App Service for Containers
- In the creation wizard, select Docker container, Windows, and put in the docker image from Docker hub as: andyvan27/net4api:0.1
