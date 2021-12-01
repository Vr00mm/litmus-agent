# litmus-agent

This is a PoC

## This is helm chart for litmus chaos agent

### clone repo
```bash
git clone https://github.com/Vr00mm/litmus-helm-agent
cd litmus-helm-agent
```

### Install chart helm
```bash
helm upgrade --install \
  litmus-agent helm/litmus-agent \
  --namespace litmus --create-namespace \
  --set "AGENT_NAME=helm-agent" \ 
  --set "AGENT_DESCRIPTION=My first agent deployed with helm !" \
  --set "LITMUS_URL=https://chaos-center.domain.com" \ # FOR REMOTE AGENT (INGRESS)
  --set "LITMUS_URL=http://litmusportal-frontend-service.litmus.svc.cluster.local:9091" \ # FOR SELF AGENT (SVC)
  --set "LITMUS_BACKEND_URL=http://litmusportal-server-service.litmus.svc.cluster.local:9002" \ # FOR SELF AGENT (SVC)
  --set "LITMUS_USERNAME=admin" \
  --set "LITMUS_PASSWORD=litmus" \
  --set "LITMUS_PROJECT_ID=69365cb3-0211-4262-8820-78056c8adb4c"
```

## Next to come

 - Use hooks instead init-container.<br>
   It will permit to precreate agent into limuts before install and delete it before uninstall.

 - Base helm resource from https://github.com/litmuschaos/litmus/tree/master/litmus-portal/graphql-server/manifests,<br>
   It will permit to deal with cluster/namespace mode.
