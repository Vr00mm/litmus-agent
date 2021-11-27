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
  --set "global.config.AGENT_NAME=helm-agent" \ 
  --set "global.config.AGENT_DESCRIPTION=My first agent deployed with helm !" \
  --set "global.secret.LITMUS_URL=https://chaos-center.domain.com" \ # FOR REMOTE AGENT (INGRESS)
  --set "global.secret.LITMUS_URL=http://litmusportal-frontend-service.litmus.svc.cluster.local:9091" \ # FOR SELF AGENT (SVC)
  --set "global.secret.LITMUS_BACKEND_URL=http://litmusportal-server-service.litmus.svc.cluster.local:9002" \ # FOR SELF AGENT (SVC)
  --set "global.secret.LITMUS_USERNAME=admin" \
  --set "global.secret.LITMUS_PASSWORD=litmus" \
  --set "global.secret.LITMUS_PROJECT_ID=69365cb3-0211-4262-8820-78056c8adb4c"
```
