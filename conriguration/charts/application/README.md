# Chart para o deploy da infra da aplicação

### Alterando o ambiente que será executrado 

```bash
$ --set application.deployment.env.nodeEnv=dev,application.deployment.env.springProfile=dev,application.deployment.image.namespace=labs-dev
```

### Rodando o comando completo para gerar o template no padrão K8s
```bash
$ helm template --set application.deployment.env.nodeEnv=dev,application.deployment.env.springProfile=dev,application.deployment.image.namespace=labs-dev  application -f application/values.yaml 
```

### Aplicando o template no namespace "dentro do openshift"
```bash
$ helm template --set application.deployment.env.nodeEnv=dev,application.deployment.env.springProfile=dev,application.deployment.image.namespace=labs-dev  application -f application/values.yaml  | oc apply -n labs-dev -f-
```