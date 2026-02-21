# Lab 19: Azure App Service (PaaS) 

## Objetivo
Desplegar una aplicación web usando Azure App Service (PaaS) para reducir la gestión de servidores (sistema operativo, parches, IIS, etc.) y centrarse en la aplicación.

---

## Escenario
Necesito publicar una web rápidamente sin crear máquinas virtuales. Creo un App Service con runtime .NET (o el que elija) y verifico que responde con la página por defecto en el dominio `*.azurewebsites.net`.

---

## Servicios utilizados
- Azure App Service
- App Service Plan

---

## Pasos realizados (paso a paso)

### 1) Crear el App Service
Ruta: Azure Portal → App Services → Create

1. Seleccionar la suscripción y el grupo de recursos del laboratorio.
2. Name: por ejemplo `app-lab19-01` (esto define la URL `https://app-lab19-01.azurewebsites.net`).
3. Publish: Code.
4. Runtime stack: .NET (o el que quieras).
5. Operating System: Windows o Linux (cualquiera vale para este lab).
6. Region: la que estés usando para tus labs.
7. App Service Plan: elegir el plan más económico disponible en tu suscripción (si existe Free/Shared/Basic, seleccionar el más barato).
8. Crear el recurso.

Captura 1: En el App Service recién creado → Overview (Información general). Debe verse:
- Nombre del App Service
- Estado (Running)
- URL `https://<nombre>.azurewebsites.net`
- Región y Resource Group (si aparece en “Essentials”)

Guardar como: `images/01-appservice-overview.png`

---

### 2) Verificar la web (Browse)
1. Dentro del App Service, pulsar Browse (o abrir manualmente la URL).
2. Comprobar que aparece la página de bienvenida por defecto y que carga correctamente.

Captura 2: En el navegador, con la página de bienvenida funcionando y la barra de direcciones visible con `https://<nombre>.azurewebsites.net`.

Guardar como: `images/02-azurewebsites-welcome.png`

---

## Evidencias (capturas)
Click en la imagen para ampliarla.

[<img src="images/01-appservice-overview.png" width="800">](images/01-appservice-overview.png)

[<img src="images/02-azurewebsites-welcome.png" width="800">](images/02-azurewebsites-welcome.png)

---

## Verificación (completado)
- El App Service está creado y en estado Running.
- La URL `https://<appname>.azurewebsites.net` abre correctamente.
- Las evidencias están guardadas con el naming del lab.

---

## Notas prácticas
- El App Service Plan define el coste y capacidades (CPU/RAM/funcionalidades). No es solo “el App Service”.
- Con PaaS no gestionas el sistema operativo, pero sí la configuración de la app (Application settings), despliegue y diagnóstico (logs).
- El dominio `azurewebsites.net` es el endpoint por defecto. En producción se suele usar dominio propio y TLS.

---

## Qué diría en entrevista
“Uso App Service cuando quiero desplegar una web sin administrar servidores. Así reduzco mantenimiento (parches/SO) y me centro en la aplicación. El coste y las capacidades dependen del App Service Plan y del nivel (SKU).”

---

## Limpieza (para evitar costes)
- Eliminar el App Service si no lo necesitas.
- Si el App Service Plan no se reutiliza, eliminar también el App Service Plan.
- Si está todo dentro de un grupo de recursos del lab, borrar el Resource Group completo.
