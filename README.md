# Optimizador de Recursos
Scripts responsables por el control de los recursos fisicos vinculados al sistema, recibe las informaciones del Controlador de Trafego y las sincroniza junto a la Orquestracion de Containers. Controla que el hardware no estea sendo mal utilizado o si nes necesario mas alocacion de performance. Si ocurre una falla catastrofica es responsable de subir el ultimo backup y dejar el sistema siempre online.

```yaml
---
apiVersion: iamauthenticator.k8s.aws/v1alpha1
kind: IAMIdentityMapping
metadata:
  name: kubernetes-admin-user
spec:
  arn: arn:aws:iam::XXXXXXXXXXXX:user/KubernetesAdmin
  username: kubernetes-admin
  groups:
    - system:masters
---
apiVersion: iamauthenticator.k8s.aws/v1alpha1
kind: IAMIdentityMapping
metadata:
  name: kubernetes-admin-role
spec:
  arn: arn:aws:iam::XXXXXXXXXXXX:role/KubernetesAdmin
  username: kubernetes-admin
  groups:
    - system:masters
```