# 🩺 Prueba Técnica DevOps – HL7 → FHIR (Mirth, PostgreSQL, HAPI FHIR, Docker)

Este repositorio contiene la implementación completa de una **POC de integración sanitaria**, basada en **mensajería HL7**, transformación a **FHIR Patient**, y persistencia en **PostgreSQL**, utilizando **Mirth Connect**, **HAPI FHIR Server** y **Docker Compose**, desplegado en un **VPS Amazon EC2**.

---

## 🚀 Tecnologías utilizadas

- **Mirth Connect 4.3.0**
- **PostgreSQL**
- **HAPI FHIR JPA Server**
- **Docker & Docker Compose**
- **AWS EC2 (Ubuntu Linux)**
- **Portainer**
- **DBeaver (cliente SQL)**

---

## 🌐 Accesos al entorno desplegado

El entorno está desplegado en la IP pública:

### **http://56.126.11.211**

| Servicio | Puerto | URL |
|----------|--------|------|
| Portainer | 9000 | http://56.126.11.211:9000 |
| Mirth Connect | 8443 | https://56.126.11.211:8443 |
| HAPI FHIR | 8081 | http://56.126.11.211:8081 |
| PostgreSQL | 5432 | (interno / accesible vía DBeaver) |

---

## 🔐 Credenciales

### **Portainer**
- **Usuario:** admin  
- **Password:** LeandroArganaraz  
- **URL:** http://56.126.11.211:9000

### **Mirth Connect**
- **Usuario:** admin  
- **Password:** LeandroArganaraz 
- **URL:** https://56.126.11.211:8443

### **PostgreSQL**
- **Host interno:** postgres-hl7  
- **Host externo:** 56.126.11.211  
- **Usuario:** hl7user  
- **Password:** hl7pass  
- **Base:** hl7db  
- **Puerto:** 5432

### **HAPI FHIR Server**
- Consola: http://56.126.11.211:8081  
- FHIR Root: http://56.126.11.211:8081/fhir/  
- Endpoint Patient: http://56.126.11.211:8081/fhir/Patient  
- Lista de pacientes: http://56.126.11.211:8081/fhir/Patient?_pretty=true

---

## 🧱 Arquitectura

HL7 Source → Mirth Connect → PostgreSQL
↓
Transformación JS (HL7 → FHIR)
↓
HTTP Sender → HAPI FHIR Server