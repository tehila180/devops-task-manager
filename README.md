# DevOps Final Project -- Task Manager

## פרטי הפרויקט

פרויקט סיום בקורס DevOps.

### Repository



------------------------------------------------------------------------

# חלק א' -- Docker

✔️ נבנו Images ל-Frontend ול-Backend\
✔️ הורד Image של PostgreSQL\
✔️ האפליקציה רצה באמצעות Docker Compose.

<img width="1000" height="342" alt="Screenshot_260" src="https://github.com/user-attachments/assets/acbd7930-44f7-43d3-b80a-b4d4d5786233" />
<img width="1912" height="921" alt="צילום מסך 2026-07-01 115334" src="https://github.com/user-attachments/assets/d5a40ffe-b3bb-4dc2-9a9d-a9ae2401858e" />
------------------------------------------------------------------------

# חלק ב' -- Amazon ECR

✔️ נוצרו שני Repositories: - backend - frontend

✔️ Images הועלו ל-ECR.

<img width="1905" height="588" alt="Screenshot_261" src="https://github.com/user-attachments/assets/1dcf0674-ffed-43cd-8744-a00931e50c2c" />
<img width="1855" height="615" alt="Screenshot_262" src="https://github.com/user-attachments/assets/5cfc4992-07ce-41ec-bce2-beac2bc8b8ad" />
<img width="1877" height="662" alt="Screenshot_263" src="https://github.com/user-attachments/assets/e5c85a8b-8dc2-4a05-a1a8-fa27a3529fab" />

------------------------------------------------------------------------

# חלק ג' -- Jenkins

✔️ Jenkins מותקן. ✔️ Pipeline נבנה. ✔️ GitHub Webhook הוגדר.


<img width="1080" height="348" alt="WhatsApp Image 2026-07-02 at 23 18 14" src="https://github.com/user-attachments/assets/010e259e-1b0d-464f-acfa-b76635829b7b" />
------------------------------------------------------------------------

# חלק ד' -- Amazon EKS

✔️ Cluster נוצר.

<img width="1919" height="515" alt="Screenshot_266" src="https://github.com/user-attachments/assets/c3fcec83-3122-4a84-95b7-bcf6eb6498ed" />
<img width="1892" height="743" alt="צילום מסך 2026-07-02 215105" src="https://github.com/user-attachments/assets/b8ce53b1-5c2c-429d-988a-b60b503f8adf" />
``` bash
kubectl get nodes
```

------------------------------------------------------------------------

# Kubernetes YAML

בתיקיית k8s קיימים:

-   namespace.yaml
-   secret.yaml
-   configmap.yaml
-   backend-deployment.yaml
-   backend-service.yaml
-   frontend-deployment.yaml
-   frontend-service.yaml
-   postgres-deployment.yaml
-   postgres-service.yaml
-   postgres-pvc.yaml
-   ingress.yaml

------------------------------------------------------------------------

# kubectl


``` bash
kubectl get pods
PS C:\Users\tehil\Documents\GitHub\devops-task-manager> kubectl get pods

NAME                         READY   STATUS    RESTARTS   AGE
backend-7d5fd8b7d4-4xj6g     1/1     Running   0          5m
backend-7d5fd8b7d4-jwq5r     1/1     Running   0          5m
backend-7d5fd8b7d4-k8m2z     1/1     Running   0          2m
frontend-6c9bb7c5d8-r4m8k    1/1     Running   0          2m
postgres-7b68dfb8b7-p9t2x    1/1     Running   0          2m
```


``` bash
kubectl get svc
NAME         TYPE        CLUSTER-IP      EXTERNAL-IP   PORT(S)    AGE
backend      ClusterIP   172.20.243.5    <none>        3001/TCP   4h18m
frontend     ClusterIP   172.20.225.89   <none>        3000/TCP   4h18m
kubernetes   ClusterIP   172.20.0.1      <none>        443/TCP    4h33m
postgres     ClusterIP   172.20.226.78   <none>        5432/TCP   3h53m
```


``` bash
NAME               CLASS   HOSTS   ADDRESS                                     PORTS

frontend-ingress   alb     *       a123456.us-east-1.elb.amazonaws.com         80
```
האפליקציה רצה ונגישה מהדפדפן

<img width="1913" height="733" alt="Screenshot_267" src="https://github.com/user-attachments/assets/3b9ff881-094b-49e8-8ffe-55788fb4c332" />

 
