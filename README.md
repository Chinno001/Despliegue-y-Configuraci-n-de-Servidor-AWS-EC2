# Despliegue-y-Configuraci-n-de-Servidor-AWS-EC2
Guía y documentación paso a paso para el despliegue, configuración y conexión remota a una instancia AWS EC2 (Linux) con pila LAMP.
# ☁️ Despliegue y Configuración de Servidor AWS EC2

Este repositorio contiene la documentación paso a paso para la creación, configuración y conexión remota a una instancia de servidor **Amazon EC2** ejecutando Linux, diseñado como proyecto de laboratorio y portafolio técnico para **Sistemas Operativos** y **Cloud Computing**.

---

## 🚀 Características del Proyecto
- **Proveedor Cloud:** Amazon Web Services (AWS)
- **Servicio:** Amazon EC2 (Elastic Compute Cloud)
- **Sistema Operativo:** Ubuntu Server / Amazon Linux 2023
- **Métodos de Acceso:** - Conexión vía cliente Web (*EC2 Instance Connect / IP Pública*)
  - SSH mediante terminal local con clave privada (`.pem`)
- **Propósito:** Demostración de administración de servidores remotos, reglas de red (Security Groups) y asignación de direcciones IP.

---

## 🛠️ Requisitos Previos
- Cuenta activa en AWS (AWS Academy o AWS Free Tier).
- Par de claves (*Key Pair*) asignado para acceso SSH.
- Grupo de seguridad (*Security Group*) configurado con los puertos de entrada necesarios:
  - **SSH (Puerto 22)**
  - **HTTP (Puerto 80)** *(si se despliega servidor web)*

---

## 📡 Arquitectura y Conexión
[ Usuario / Navegador ]
│
├──► EC2 Instance Connect (Consola AWS) ──┐
│                                         ▼
└──► SSH via Terminal (Con Putty) (Puerto 22) ───► [ Instancia EC2 Linux ]
(IP Pública / Elastic IP)

Nota: El usuario varía según la distro (ec2-user para Amazon Linux, ubuntu para Ubuntu Server).
Solución de Problemas Frecuentes:
No aparece opción de IP Pública -->Se desactivó al crear la instancia -->Asignar una Elastic IP o recrear la instancia habilitando la asignación automática.
Timeout en la conexión SSH --> Regla de entrada bloqueada --> Verificar que el Security Group permita tráfico TCP en puerto 22 para tu IP.
Estado "Initializing" --> El SO aún se está ejecutando --> Esperar 1 o 2 minutos hasta ver 2/2 comprobaciones superadas.
