1. Создать любую страничку на php.

" <?php
echo "Hello, World!";
?> "

    
2. Создать рабочий докер имадж для страницы с php.
     
    FROM php:7.4-apache
    COPY index.php /var/www/html/
    
3. Развернуть deployment с php в eks.
     
    apiVersion: apps/v1
kind: Deployment
metadata:
  name: php-deployment
spec:
  replicas: 3
  selector:
    matchLabels:
      app: php-app
  template:
    metadata:
      labels:
        app: php-app
    spec:
      containers:
      - name: php-deployment
        image: petrovichpower/php-page
        ports:
        - containerPort: 80

4. Сделать чтобы страничка с php была доступна извне. Использовать ingress.

  apiVersion: networking.k8s.io/v1
kind: Ingress
metadata:
  name: php-ingress
  annotations:
    kubernetes.io/ingress.class: nginx
spec:
  rules:
  - host: a99ba57f27b2a44ad918ba049a69dbd3-792ea84d66ae4546.elb.us-east-1.amazonaws.com
    http:
      paths:
      - path: /
        pathType: Prefix
        backend:
          service:
            name: php-service
            port:
              number: 80


      apiVersion: v1
kind: Service
metadata:
  name: php-service
spec:
  selector:
    app: php-app
  ports:
    - protocol: TCP
      port: 80
      targetPort: 80

  ![Image alt]([https://github.com/{username}/{repository}/raw/{branch}/{path}/image.png](https://github.com/petrovichpower/MyHomeWork/blob/main/Lesson%2320/%D0%A1%D0%BD%D0%B8%D0%BC%D0%BE%D0%BA%20%D1%8D%D0%BA%D1%80%D0%B0%D0%BD%D0%B0%202024-04-25%20021301.png))

  
5. Дать пользователю arn:aws:iam::097084951758:user/alex_b доступ в кластер.

  apiVersion: v1
kind: ConfigMap
metadata:
  name: aws-auth
  namespace: kube-system
data:
  mapRoles: |
    - rolearn: arn:aws:iam::097084951758:role/alex_b
      username: alex_b
      groups:
        - system:masters
