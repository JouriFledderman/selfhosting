# Self-hosting

Many of the self-hosted projects that I found in the wild lacked a basic setup and some form of example. While in some cases
the setup was fairly easy (from my perspective), in many cases the setup required some complex setup and lots of tinkering
in order to get it right. With this project I will try to create the examples that I lacked in my setup. Hopefully you will
find them useful and they will provide you the example that I sometimes desperately needed.  

# Situation

Currently, I have a `Synology ds1621` running on DSM 7.2.2+. I installed `Container manager` (from `Pacakge center`) and 
from this application I installed Portainer (image: `portainer/portainer-ce`). All the docker-compose files that you 
can find in the sub folders are stacks inside this Portainer instance.

# Project structure

All the sub folders are projects that I deploy(ed). They contain the docker-compose file that I use(d) to deploy the stack
in Portainer and a `README.md` with some explanation on how to run the example. 

# Gitea
This project is now published on GitHub, so I can share it with the world. But my personal self-hosting projects are docker-compose 
files added to a private (self-hosted) Gitea repository. The nice thing about this is that from Portainer, you can point to
docker-compose files within a Gitea repository. The stacks are updated automatically if the docker-compose file that it points
to gets updated.

# Renovate
I use Renovate to scan my repository to find project updates. Instead of running on a `latest` version and restart and 
pull the new images now and then, I weekly run Renovate to scan my repository for new versions of the components in my 
docker-compose files. Renovate creates pull-request for all the new versions it will find and I can merge these pull requests
when I think it is OK to update to this version. After merging, it will take up about 5 minutes to redeploy the stack. 
