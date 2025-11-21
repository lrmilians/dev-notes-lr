## 🧩 Microservices Architecture: Herramientas y Tecnologías Clave (Explicado Visual)

Una arquitectura de microservicios no se trata solo de dividir un monolito…
se trata de elegir las herramientas correctas para que cada servicio sea independiente, escalable y fácil de desplegar 🚀

La imagen de arriba resume los pilares esenciales.
Aquí te los explico en formato simple y directo 👇👇

# 1️⃣ Bases de Datos — El corazón del sistema ❤️

En microservicios no existe una sola base universal.
Cada servicio usa la que mejor resuelve su caso (Database per Service).

🔹 SQL: MySQL, PostgreSQL  
🔹 NoSQL: MongoDB, Cassandra, DynamoDB, HBase  

👉 Elección clave según consistencia, velocidad y tipo de datos.

# 2️⃣ Message Brokers — El pegamento entre servicios 🔗

Aquí vive la comunicación asíncrona:

✔ Kafka  
✔ RabbitMQ  
✔ Amazon SQS  

👉 Reducen acoplamiento, mejoran resiliencia y evitan cascadas de fallos.

# 3️⃣ Lenguajes — Microservicios multiculturales 👨‍💻

Un microservicio = un lenguaje si lo necesitas.

✔ Java  
✔ .NET  
✔ NodeJS  
✔ Go  
✔ Python  

👉 Microservicios permiten usar el lenguaje adecuado para cada necesidad.

# 4️⃣ Seguridad — Lo primero, siempre 🔐

Nada entra ni sale sin seguridad:

✔ JWT  
✔ OAuth 2.0  
✔ Autorización de APIs  
✔ TLS  

👉 Sin esto, tu arquitectura no es de producción.

# 5️⃣ Orquestación — Donde tus servicios realmente viven ☁️

Para ejecutar contenedores a escala:

✔ Kubernetes  
✔ ECS (AWS)  
✔ OpenShift  
✔ Hashicorp Nomad  

👉 Aquí se maneja autoscaling, health checks y resiliencia real.

# 6️⃣ Contenedores — El formato moderno de ejecución 📦

Los microservicios corren aquí:

✔ Docker  
✔ Podman  

👉 Empaquetan tu app con todo su entorno.

# 7️⃣ CI/CD — Entrega continua de verdad ⚙️

Tu pipeline debe ser automático y confiable:

✔ GitHub Actions  
✔ Jenkins  
✔ TeamCity  
✔ GitLab CI  
✔ CircleCI  

👉 Sin CI/CD, escalar microservicios es imposible.

# 8️⃣ Monitoring — Tu sistema está vivo, debes observarlo 👀

Para saber qué pasa adentro:

✔ Prometheus  
✔ Grafana  
✔ Kibana  

👉 Métricas + logs + alertas = Sistemas sanos.

# 9️⃣ Cloud Providers — El hogar de tus microservicios ☁️

Eliges según precios, ecosistema y herramientas:

✔ AWS  
✔ Azure  
✔ GCP  
✔ Linode  
✔ DigitalOcean  

👉 El proveedor influye en tu stack, costos y escalabilidad.

❓ MINI-QUIZ

¿Qué herramienta se usa para la comunicación asíncrona entre microservicios?

a) GitHub Actions  
b) Docker  
c) Kafka  
d) PostgreSQL  

✅ Respuesta correcta: c) Kafka

![microservices](../../img/microservices/architecture-01.gif)