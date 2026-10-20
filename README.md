# 🏎️ NFS: Most Wanted (2005) - Radmin VPN Lag & Desync Fix

Solución definitiva para corregir desincronización, teletransportación de autos (*rubberbanding*), latencia artificial y problemas de conectividad LAN al jugar **Need for Speed: Most Wanted (2005)** a través de redes virtuales de **Radmin VPN**.

---

## 📋 Problema Conocido

El código de red original de NFSMW (2005) fue diseñado para redes locales (LAN) tradicionales con tiempos de respuesta casi instantáneos (sub-5ms) y sin adaptadores de red virtuales. Al pasar por Radmin VPN suelen presentarse:

- Métricas de ping inestables debido a saltos de prioridad de red en Windows.
- Pérdida de paquetes en el buffer de sockets UDP.
- Tasa de refresco del tickrate de física bloqueada a valores inconsistentes en salas multijugador.

---

## ⚡ Características del Fix

- **Priorización de Interfaz:** Enrutamiento directo del tráfico del juego sobre la métrica de red de Radmin VPN.
- **Buffer Flush:** Ajuste del buffer UDP para evitar retrasos acumulativos en partidas con más de 2 jugadores.
- **Compatibilidad Total:** Funciona junto a mods populares (Widescreen Fix, Extra Options, HD Reflections).

---

## 📦 Descarga

Puedes descargar la versión más reciente lista para usar desde la sección de entregas:

👉 **[Descargar Última Versión (Releases)](https://github.com/TU_USUARIO/TU_REPOSITORIO/releases/latest)**

---

## 🛠️ Requisitos Previos

1. **Need for Speed: Most Wanted (2005)** actualizado a la versión oficial **v1.3**.
2. **Radmin VPN** instalado y con conexión activa en la misma sala virtual que los demás jugadores.
3. Privilegios de Administrador en Windows.

---

## 🚀 Guía de Instalación y Configuración

### Método 1: Instalación Rápida (Archivos del Juego)

1. Ve a la carpeta raíz de instalación de tu juego (donde se encuentra `speed.exe`).
   > *Ruta típica:* `C:\Program Files (x86)\EA GAMES\Need for Speed Most Wanted`
2. Descarga el archivo `.zip` desde la sección de **Releases**.
3. Extrae el contenido directamente en la carpeta raíz del juego.
4. Si el sistema te pregunta si deseas reemplazar archivos existentes, selecciona **Reemplazar**.

---

### Método 2: Ajuste de Métrica de Red en Windows (Paso Clave para Radmin)

Para que el juego no intente comunicarse primero por tu Wi-Fi o Ethernet habitual en lugar de Radmin:

1. Presiona `Windows + R`, escribe `ncpa.cpl` y presiona **Enter**.
2. Haz clic derecho sobre el adaptador **Radmin VPN** y selecciona **Propiedades**.
3. Selecciona **Protocolo de Internet versión 4 (TCP/IPv4)** y pulsa **Propiedades**.
4. Haz clic en el botón **Opciones avanzadas...** (abajo a la derecha).
5. En la pestaña *Configuración de IP*, desmarca la casilla **Métrica automática**.
6. En el campo **Métrica de la interfaz**, escribe `1` o `5` (un número bajo le da prioridad máxima).
7. Acepta todos los cuadros de diálogo y reinicia tu cliente de Radmin VPN.

---

## 🎮 Instrucciones para Crear y Unirse a Salas

### Para el Anfitrión (Host):
1. Inicia Radmin VPN y asegúrate de que todos los competidores estén en tu red con luz verde (ping estable).
2. Abre el juego mediante `speed.exe` (como Administrador).
3. Ve a **Modo LAN / Red Local**.
4. Crea la sala y espera a que los jugadores ingresen.

### Para los Jugadores (Guests):
1. Confirma que tienes conexión directa con el Host en Radmin (haz clic derecho sobre el nombre del Host en Radmin y selecciona **Hacer ping**).
2. Inicia el juego como Administrador.
3. Entra a **Modo LAN** y busca la sala creada.

---

## ⚙️ Solución de Problemas Frecuentes

| Problema | Causa Probable | Solución |
| :--- | :--- | :--- |
| **No se ve la sala en LAN** | Bloqueo de Firewall de Windows | Añadir `speed.exe` a las excepciones del Firewall público y privado. |
| **Luz azul / retransmisión en Radmin** | Restricción NAT o puertos | Reiniciar el servicio de Radmin o verificar la configuración del router. |
| **El juego se congela al entrar a LAN** | Conflicto con adaptadores inactivos | Deshabilitar adaptadores de red no utilizados (VirtualBox, VMware, Hamachi). |

---

## 📄 Licencia y Créditos

Este proyecto se distribuye bajo la licencia **MIT**. Consulta el archivo `LICENSE` para más información.

*Need for Speed es una marca registrada de Electronic Arts Inc. Este proyecto no está afiliado, respaldado ni asociado con Electronic Arts.*
