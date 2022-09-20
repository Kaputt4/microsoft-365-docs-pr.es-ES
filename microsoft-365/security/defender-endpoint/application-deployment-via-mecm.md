---
title: Migrar servidores desde Microsoft Monitoring Agent a la solución unificada
description: Obtenga información sobre cómo migrar servidores de nivel inferior de Microsoft Monitoring Agent a la nueva solución unificada paso a paso de este artículo.
keywords: migrate server, server, 2012r2, 2016, server migration onboard Microsoft Defender para punto de conexión servers, MECM, Microsoft Monitoring Agent, MMA, downlevel server, unified solution, UA
search.appverid: met150
ms.mktglfcycl: deploy
ms.sitesec: library
ms.service: microsoft-365-security
ms.subservice: mde
ms.pagetype: security
author: alekyaj
ms.author: macapara
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: feac94002669ae3e5fa1ddf58b8f191dc507f1c4
ms.sourcegitcommit: 078149c9645ce220911ccd6ce54f984a4c92ce53
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2022
ms.locfileid: "67810832"
---
# <a name="migrating-servers-from-microsoft-monitoring-agent-to-the-unified-solution"></a>Migrar servidores desde Microsoft Monitoring Agent a la solución unificada

**Se aplica a:**

- Windows Server 2012 R2
- Windows Server 2016

Este artículo le guía en la migración de servidores de nivel inferior de Microsoft Monitoring Agent (MMA) a la solución unificada.

## <a name="prerequisites"></a>Requisitos previos

- Microsoft Endpoint Configuration Manager (MECM) anterior a 2207.
- Dispositivos de sistema operativo de nivel inferior en su entorno incorporados con Microsoft Monitoring Agent. Para confirmarlo, compruebe que `MsSenseS.exe` se está ejecutando en el Administrador de tareas.
- Presencia del agente mma. Para comprobarlo, compruebe si el identificador de área de trabajo correcto está presente en la Panel de control> Microsoft Monitoring Agent.
- Portal de Microsoft 365 Defender activo con dispositivos incorporados.
- Se configura una **colección de** dispositivos que contiene servidores de nivel inferior, como Windows Server 2012 R2 o Windows Server 2016 mediante el agente MMA, en la instancia de MECM.

Para obtener más información sobre cómo instalar los requisitos previos enumerados, consulte la sección [temas relacionados](#related-topics) .

## <a name="gather-required-files"></a>Recopilación de archivos necesarios

Copie el paquete de solución unificado, el script de incorporación y el script de migración en el mismo origen de contenido que implemente otras aplicaciones con MECM.

1. Descargue el script de incorporación y la solución unificada desde [Microsoft 365 Defender página de configuración](https://sip.security.microsoft.com/preferences2/onboarding).
   :::image type="content" source="images/onboarding-script.png" alt-text="Captura de pantalla de la descarga del script de incorporación y la solución unificada" lightbox="images/onboarding-script.png":::
   > [!Note]
   > Debe seleccionar el directiva de grupo en la lista desplegable Método de implementación para obtener el archivo .cmd.
2. Descargue el script de migración del documento: [Escenarios de migración del servidor de la solución de Microsoft Defender para punto de conexión anterior basada en MMA](server-migration.md). Este script también se puede encontrar en GitHub: [GitHub - microsoft/mdefordownlevelserver](https://github.com/microsoft/mdefordownlevelserver).
3. Guarde los tres archivos en una carpeta compartida usada por MECM como origen de software.

   :::image type="content" source="images/ua-migration.png" alt-text="Captura de pantalla de guardado de la carpeta compartida por MECM.":::

## <a name="create-the-package-as-an-application"></a>Creación del paquete como una aplicación

1. En la consola de MECM, siga estos pasos: **Biblioteca de software>Aplicaciones>Crear aplicación**.
2. Seleccione **Especificar manualmente la información de la aplicación**.
   :::image type="content" source="images/manual-application-information.png" alt-text="Captura de pantalla de la especificación manual de la selección de información de la aplicación." lightbox="images/manual-application-information.png":::
3. Seleccione **Siguiente** en la pantalla Centro de software del asistente.
4. En Tipos de implementación, haga clic en **Agregar**.
5. Seleccione **Manualmente para especificar la información del tipo de implementación** y seleccione **Siguiente**.
6. Asigne un nombre a la implementación de script y seleccione **Siguiente**.

   :::image type="content" source="images/manual-deployment-information.png" alt-text="Captura de pantalla que especifica la información de implementación del script.":::
7. En este paso, copie la ruta de acceso UNC en la que se encuentra el contenido. Ejemplo: `\\ServerName\h$\SOFTWARE_SOURCE\path`.

   :::image type="content" source="images/deployment-type-wizard.png" alt-text="Captura de pantalla que muestra la copia de la ruta de acceso UNC.":::
  
8. Además, establezca lo siguiente como programa de instalación:

     ```powershell
      Powershell.exe -ExecutionPolicy ByPass -File install.ps1 -RemoveMMA <workspace ID> -OnboardingScript .\WindowsDefenderATPOnboardingScript.cmd 
     ```

      Haga clic en **Siguiente** y asegúrese de agregar su propio identificador de área de trabajo en esta sección.
9. Haga clic en **Siguiente** y en Agregar una cláusula.
10. El método de detección se basará en la clave del Registro que se muestra a continuación.
      `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\Sense`

      Active la opción : **esta configuración del Registro debe salir en el sistema de destino para indicar la presencia de esta aplicación.**

      :::image type="content" source="images/detection-wizard.png" alt-text="Captura de pantalla que muestra el Asistente para tipos de detección":::

      >[!TIP]
      >El valor de la clave del Registro se obtuvo mediante la ejecución del comando de PowerShell que se muestra a continuación en un dispositivo que tiene instalada la solución unificada. También se pueden usar otros métodos creativos de detección. El objetivo es identificar si la solución unificada ya se ha instalado en un dispositivo específico. Puede dejar los campos Valor y Tipo de datos en blanco.

     ```powershell
      get-wmiobject Win32_Product | Sort-Object -Property Name |Format-Table IdentifyingNumber, Name, LocalPackage -AutoSize 
     ```

11. En la sección **Experiencia del usuario** , compruebe la configuración recomendada que se muestra en la captura de pantalla. Puede elegir lo que se adapte a su entorno y hacer clic en **Siguiente**. Para la **visibilidad del programa de instalación**, es recomendable instalar con **Normal** durante las pruebas de fase y, a continuación, cambiarlo a **Minimizado** para la implementación general.

     >[!TIP]
     >El tiempo de ejecución máximo permitido se puede reducir de (valor predeterminado) de 120 minutos a 60 minutos.

     :::image type="content" source="images/user-experience-in-deployment-type-wizard.png" alt-text="Captura de pantalla que muestra la experiencia del usuario en el Asistente para tipos de implementación.":::

12. Agregue los requisitos adicionales y, a continuación, seleccione **Siguiente**. 
13. En la sección Dependencias, seleccione **Siguiente**. 
14. Seleccione **Siguiente** hasta que aparezca la pantalla de finalización y, a continuación, **Cerrar**.
15. Siga **seleccionando Siguiente** hasta la finalización del Asistente para aplicaciones. Compruebe que todos se han marcado en verde.
16. Cierre el asistente, haga clic con el botón derecho en la aplicación creada recientemente e impleméntela en la colección de servidores de nivel inferior. Localmente, la instalación se puede confirmar en el Centro de software. Para obtener más información, consulte los registros de CM en `C:\Windows\CCM\Logs\AppEnforce.log`.

    :::image type="content" source="images/deploy-application.png" alt-text="Captura de pantalla que muestra la implementación de la aplicación creada." lightbox="images/deploy-application.png":::
     
17. Compruebe el estado de la migración en MECM > Supervisión > implementaciones.

    :::image type="content" source="images/deployment-status.png" alt-text="Captura de pantalla que muestra la comprobación del estado de la implementación." lightbox="images/deployment-status.png":::
      
18. Solución de problemas. Los archivos ETL se crearán y guardarán automáticamente localmente en cada servidor de esta ubicación `C:\Windows\ccmcache\#\`. El soporte técnico puede aprovechar estos archivos para solucionar problemas de incorporación.

## <a name="related-topics"></a>Temas relacionados

- [Configuración de Microsoft Monitoring Agent](/services-hub/health/mma-setup)
- [Implementación de aplicaciones: Configuration Manager](/mem/configmgr/apps/deploy-use/deploy-applications)
- [Microsoft Defender para punto de conexión: Configuration Manager](/mem/configmgr/protect/deploy-use/defender-advanced-threat-protection)
- [Incorporación de servidores Windows al servicio Microsoft Defender para punto de conexión](configure-server-endpoints.md)
- [Microsoft Defender para punto de conexión: Defender Windows Server 2012 R2 y 2016](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/defending-windows-server-2012-r2-and-2016/ba-p/2783292)
