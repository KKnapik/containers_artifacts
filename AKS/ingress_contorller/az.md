# Create ingress controller
$Namespace = 'ingress-basic'

helm repo add ingress-nginx https://kubernetes.github.io/ingress-nginx
helm repo update

helm install ingress-nginx ingress-nginx/ingress-nginx `
  --create-namespace `
  --namespace $Namespace `
  --set controller.service.annotations."service\.beta\.kubernetes\.io/azure-load-balancer-health-probe-request-path"=/healthz

  # Add definition to YAML
  apiVersion: networking.k8s.io/v1
  kind: Ingress
  metadata:
    name: example
    namespace: foo
  spec:
    ingressClassName: nginx
    rules:
      - host: www.example.com
        http:
          paths:
            - pathType: Prefix
              backend:
                service:
                  name: exampleService
                  port:
                    number: 80
              path: /
    # This section is only required if TLS is to be enabled for the Ingress
    tls:
      - hosts:
        - www.example.com
        secretName: example-tls

# AKS Identity to access KV
az aks show -g [RG] -n [AKS name] --query addonProfiles.azureKeyvaultSecretsProvider.identity.clientId -o tsv

# in order to add volumes, define volumemount in spec/containers
        volumeMounts:
        - name: secrets-store01-inline
          mountPath: "/mnt/secrets-store"
          readOnly: true
# volume
      volumes:
      - name: secrets-store01-inline
        csi:
          driver: secrets-store.csi.k8s.io
          readOnly: true
          volumeAttributes:
            secretProviderClass: "api-kv-dbaccess"
# and CSI provider