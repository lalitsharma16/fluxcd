This folder consists file to install Fluxcd.
Pre-requisite:
1. Setup a k8s cluster and Set some env variable before: GITURL, GITBRANCH, GITPATH, GHUSER.
2. Install fluxctl on the server.
3. Create "flux" namespace and secret "image-reg-access" for private registry to pull images.
4. kubectl apply -f fluxcd-implementation.yaml
5. Run command "fluxctl identity --k8s-fwd-ns flux" to get the ssh key.
6. Set this ssh key in Repository to access.
7. Change the known_hosts in configmap , kubectl -n flux edit cm flux-ssh-config
8. Run command "fluxctl sync --k8s-fwd-ns flux" to sync the cluster with the repository.
9. Now commit changes in the repo and check if its updated in kubenetes.
