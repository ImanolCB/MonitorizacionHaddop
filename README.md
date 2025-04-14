# 🚀 Monitoreo de Hadoop en AWS con Prometheus + Grafana

Este proyecto presenta una arquitectura simple y eficaz para monitorear un clúster de Hadoop desplegado en Amazon EC2 y EMR, utilizando **Prometheus** para la recolección de métricas y **Grafana** para la visualización interactiva en tiempo real.

---

## 📊 ¿Qué hace este sistema?

- Supervisa el estado del **Namenode** y **Datanodes** de Hadoop.
- Visualiza métricas clave del **HDFS** como uso de disco, latencia y operaciones de lectura/escritura.
- Permite el acceso remoto a dashboards desde fuera de la VPC.
- Se adapta tanto a clústeres Hadoop en **EC2** como en **EMR**.

---

## 🧱 Arquitectura general

- Hadoop desplegado en **EC2** y/o **EMR** dentro de una **VPC**.
- **JMX Exporter** expone métricas de los nodos Hadoop.
- **Prometheus** scrapéa periódicamente las métricas.
- **Grafana** se conecta a Prometheus y muestra dashboards en tiempo real.
- Posibilidad de tener **Grafana/Prometheus externos** para monitoreo remoto.

---

## 🚧 Componentes principales

| Componente  | Rol |
|-------------|-----|
| EC2 / EMR   | Ejecuta el clúster Hadoop |
| JMX Exporter | Expone métricas desde Hadoop |
| Prometheus  | Recolecta y almacena métricas |
| Grafana     | Visualiza métricas con dashboards personalizados |

---

## ⚙️ Requisitos (mínimos)

- Clúster Hadoop funcionando en EC2 o EMR
- Prometheus configurado con targets JMX Exporter
- Grafana con datasource apuntando a Prometheus
- Acceso a la VPC desde donde esté alojado Grafana (o configuración pública segura)

---
