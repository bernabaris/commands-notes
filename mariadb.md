# Install MariaDB with Helm

This guide explains how to install MariaDB on Kubernetes using the Bitnami Helm chart.

---

## 1. Add Bitnami Helm Repository

Add the Bitnami Helm repository and update:

```bash
helm repo add bitnami https://charts.bitnami.com/bitnami
helm repo update
```

---

## 2. Create values.yaml File

Create a custom values file:

```bash
sudo vi mariadb-values.yaml
```

### Example values.yaml Configuration

```yaml
auth:
  rootPassword: root123
  database: story
  username: storyuser
  password: storypass

architecture: standalone

primary:
  persistence:
    enabled: true
    size: 2Gi
```

## 3. Install MariaDB

```bash
helm upgrade --install mariadb bitnami/mariadb -f mariadb-values.yaml
```

## 4. Verify Pod Status

Check if MariaDB pod is running:

```bash
kubectl get pods
```

## 5. Troubleshooting: Pod Status Pending

If the pod status is:

STATUS: Pending


Check detailed pod information:

```bash
kubectl describe pod mariadb-0
```

Example error:

Warning  FailedScheduling  default-scheduler
0/1 nodes are available: pod has unbound immediate PersistentVolumeClaims


This means Kubernetes cannot find a suitable PersistentVolume.


   

