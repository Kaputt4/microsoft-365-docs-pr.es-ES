---
title: Protección de aplicaciones para Office 365 (versión preliminar pública) para administradores
keywords: protección de aplicaciones, protección, aislamiento, contenedor aislado, aislamiento de hardware
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Obtenga lo último en aislamiento basado en hardware. Impedir que ataques actuales y emergentes como vulnerabilidades de seguridad o vínculos malintencionados interrumpan la productividad de los empleados y la seguridad de la empresa.
ms.openlocfilehash: f5a5feb14db75c5baccecf0c6afafe0c42517224
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794513"
---
# <a name="application-guard-for-office-public-preview-for-admins"></a>Protección de aplicaciones para Office (versión preliminar pública) para administradores

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


**Se aplica a:** Word, Excel y PowerPoint para Microsoft 365, Windows 10 Enterprise

> [!IMPORTANT]
> Parte de la información está relacionada con un producto de versión preliminar que puede modificarse considerablemente antes de su lanzamiento comercial. Microsoft makes no warranties, express or implied, with respect to the information provided here.

La Protección de aplicaciones de Microsoft Defender para Office (Protección de aplicaciones para Office) ayuda a evitar que los archivos que no son de confianza accedan a recursos de confianza, lo que mantiene la empresa a salvo de los ataques nuevos y emergentes. En este artículo se guía a los administradores a través de la configuración de dispositivos para obtener una vista previa de la Protección de aplicaciones para Office. Proporciona información sobre los requisitos del sistema y los pasos de instalación para habilitar la Protección de aplicaciones para Office en un dispositivo.

## <a name="prerequisites"></a>Requisitos previos

### <a name="minimum-hardware-requirements"></a>Requisitos mínimos de hardware

* **CPU:** 64 bits, 4 núcleos (físico o virtual), extensiones de virtualización (Intel VT-x O AMD-V), equivalente core i5 o superior recomendado
* **Memoria física:** 8 GB de RAM
* **Disco duro:** 10 GB de espacio libre en la unidad del sistema (se recomienda SSD)

### <a name="minimum-software-requirements"></a>Requisitos mínimos de software

* **Windows 10:** Windows 10 Enterprise Edition, versión de compilación de cliente 2004 (20H1) compilación 19041
* **Office:** compilación del canal beta de Office versión 2008 16.0.13212 o posterior
* **Paquete de actualización:** actualizaciones de seguridad mensuales acumulativas de Windows 10 [KB4571756](https://support.microsoft.com/help/4571756/windows-10-update-KB4571756)

Para obtener información detallada sobre los requisitos del sistema, consulte [Requisitos del sistema para la Protección de](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/reqs-md-app-guard)aplicaciones de Microsoft Defender. Para obtener más información sobre las compilaciones de Office Insider Preview, consulte Introducción a la implementación de compilaciones [de Office Insider.](https://insider.office.com/business/deploy)

### <a name="licensing-requirements"></a>Requisitos de licencia

* Seguridad de Microsoft 365 E5 o Microsoft 365 E5

## <a name="deploy-application-guard-for-office"></a>Implementar la Protección de aplicaciones para Office

### <a name="enable-application-guard-for-office"></a>Habilitar la Protección de aplicaciones para Office

1. Descargar e instalar actualizaciones de seguridad mensuales acumulativas **de Windows 10 KB4571756**.

2. Seleccione **Protección de aplicaciones de Microsoft Defender** en Características de Windows y seleccione **Aceptar.** Si habilitas la característica protección de aplicaciones, se te pedirá que reinicies el sistema. Puedes elegir reiniciar ahora o después del paso 3.

   ![Cuadro de diálogo Características de Windows que muestra AG](../../media/ag03-deploy.png)

   La característica también se puede habilitar ejecutando el siguiente comando de PowerShell como administrador:

   ```powershell
   Enable-WindowsOptionalFeature -online -FeatureName Windows-Defender-ApplicationGuard
   ```

3. Busca la directiva de grupo Protección de aplicaciones de Microsoft Defender en modo administrado ubicada en Plantillas administrativas de configuración del equipo Componentes de Windows Protección de **\\ aplicaciones de Microsoft \\ \\ Defender.** Active esta directiva estableciendo el valor en Opciones como **2** o **3** y, a continuación, **seleccione Aceptar** o **Aplicar.**

   ![Activar AG en modo administrado](../../media/ag04-deploy.png)

   Como alternativa, puedes establecer la directiva CSP correspondiente:

   > OMA-URI: **./Device/Vendor/MSFT/WindowsDefenderApplicationGuard/Settings/AllowWindowsDefenderApplicationGuard** <br> Tipo de datos: **Integer** <br> Valor: **2**

4. Reinicia el sistema.

### <a name="set-diagnostics--feedback-to-send-full-data"></a>Establecer comentarios de & diagnóstico para enviar datos completos

Este paso garantiza que los datos necesarios para identificar y solucionar problemas lleguen a Microsoft. Sigue estos pasos para habilitar el diagnóstico en el dispositivo Windows:

1. Abra **Configuración** desde el menú Inicio.

   ![Menú Inicio](../../media/ag05-diagnostic.png)

2. En **Configuración de Windows,** seleccione **Privacidad.**

   ![Menú Configuración de Windows](../../media/ag06-diagnostic.png)

3. En Privacidad, seleccione **Diagnósticos & comentarios y** seleccione **Datos de diagnóstico opcionales.**

   ![Menú de diagnóstico y comentarios](../../media/ag07a-diagnostic.png)

Para obtener más información sobre cómo configurar las opciones de diagnóstico de Windows, consulta Configuración de datos de [diagnóstico de Windows en tu organización.](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enterprise-management)

### <a name="confirm-that-application-guard-for-office-is-enabled-and-working"></a>Confirmar que la Protección de aplicaciones para Office está habilitada y funcionando

Antes de confirmar que la Protección de aplicaciones para Office está habilitada, inicie Word, Excel o PowerPoint en un dispositivo donde se hayan implementado las directivas. Asegúrese de que Office está activado. Es posible que primero deba usar su identidad de trabajo para activar el producto de Office.

Para confirmar que la Protección de aplicaciones para Office está habilitada, inicie Word, Excel o PowerPoint y abra un documento que no sea de confianza. Por ejemplo, puede abrir un documento descargado de Internet o un archivo adjunto de correo electrónico de alguien externo a su organización.

En el primer inicio de un archivo que no es de confianza, es posible que vea una pantalla de presentación de Office como la siguiente. Es posible que se muestre durante algún tiempo mientras se activa la Protección de aplicaciones para Office y se abre el archivo. Los inicios posteriores de archivos que no son de confianza deben ser más rápidos.

![Pantalla de presentación de la aplicación de Office](../../media/ag08-confirm.png)

Al abrirse, el archivo debe mostrar algunos indicadores visuales de que el archivo se abrió dentro de la Protección de aplicaciones para Office:

* Una llamada en la cinta de opciones

  ![Archivo de documento que muestra una pequeña nota de App Guard](../../media/ag09-confirm.png)

* El icono de la aplicación con un escudo en la barra de tareas

  ![Icono en la barra de tareas](../../media/ag12-limitations.png)

## <a name="configure-application-guard-for-office"></a>Configurar la Protección de aplicaciones para Office

Office admite las siguientes directivas para permitirle configurar las capacidades de protección de aplicaciones para Office. Estas directivas se pueden configurar a través de directivas de grupo o a través del servicio de directivas de nube de Office.

> [!NOTE]
> Estas directivas estarán disponibles próximamente.
> Además, la configuración de estas directivas puede deshabilitar algunas funcionalidades de los archivos abiertos en la Protección de aplicaciones para Office.

|Directiva|Descripción|
|---|---|
|Deshabilitar la Protección de aplicaciones para Office|Habilitar esta directiva forzará a Word, Excel y PowerPoint a usar el contenedor de aislamiento vista protegida en lugar de la Protección de aplicaciones para Office. Esta directiva se puede usar para deshabilitar temporalmente la Protección de aplicaciones para Office cuando haya problemas al dejarla habilitada para Edge.|
|Deshabilitar copiar y pegar para los documentos abiertos en la Protección de aplicaciones|Si se habilita esta directiva, el usuario no podrá copiar y pegar contenido de un documento abierto en la Protección de aplicaciones para Office en un documento abierto fuera de él.|
|Impedir que los usuarios quiten la protección de protección de aplicaciones en los archivos|Si se habilita esta directiva, se quitará la opción (dentro de la experiencia de la aplicación de Office) para deshabilitar la protección de la Protección de aplicaciones o abrir un archivo fuera de la Protección de aplicaciones. <p> **Nota:** Los usuarios aún pueden omitir esta directiva quitando manualmente la propiedad mark-of-the-web del archivo o moviendo un documento a una ubicación de confianza.|
|Restringir la impresión de documentos abiertos en la Protección de aplicaciones|Si se habilita esta directiva, se limitarán las impresoras en las que un usuario pueda imprimir desde un archivo abierto en la Protección de aplicaciones para Office. Por ejemplo, puede usar esta directiva para restringir a los usuarios que solo impriman en PDF.|
|Desactivar el acceso a cámara y micrófono para documentos abiertos en la Protección de aplicaciones|Si se habilita esta directiva, se quitará el acceso de Office a la cámara y al micrófono dentro de la Protección de aplicaciones para Office.|
|

> [!NOTE]
> Las siguientes directivas requerirán que el usuario cierre sesión y vuelva a iniciar sesión en Windows para que su efecto:
>
> * Deshabilitar copiar y pegar para los documentos abiertos en la Protección de aplicaciones
> * Restringir la impresión de documentos abiertos en la Protección de aplicaciones
> * Desactivar el acceso de micrófono y cámara a los documentos abiertos en la Protección de aplicaciones

## <a name="submit-feedback"></a>Enviar comentarios

### <a name="submit-feedback-via-feedback-hub"></a>Enviar comentarios a través del Centro de opiniones

Si se produce algún problema al iniciar la Protección de aplicaciones para Office, se recomienda enviar sus comentarios a través del Centro de opiniones:

1. Abre la aplicación **Centro de opiniones** e inicia sesión.

2. Si aparece un cuadro de diálogo de error al iniciar la Protección de aplicaciones, selecciona Informar a **Microsoft** en el cuadro de diálogo de error para iniciar un nuevo envío de comentarios. De lo contrario, ve a seleccionar la categoría correcta para protección de aplicaciones y, a continuación, selecciona <https://aka.ms/mdagoffice-fb> **+ Agregar nuevos** comentarios cerca de la parte superior derecha.

3. Rellene el cuadro **Resumir sus** comentarios si aún no se ha rellenado.

4. Rellene el cuadro **Explicar con más** detalle con una descripción detallada del problema que experimentó y los pasos que realizó y, a continuación, seleccione **Siguiente**.

5. Selecciona la burbuja junto a Problema. Asegúrese de que la categoría seleccionada es Protección de aplicaciones de Microsoft Defender seguridad y privacidad **\> – Office** y, a continuación, seleccione **Siguiente**.

6. Seleccione **Nuevos comentarios** y, a **continuación, Siguiente.**

7. Recopile seguimientos sobre el problema:

   1. Expande **el icono Volver a crear mi** problema.

   2. Si el problema que estás experimentando se produce mientras se ejecuta la Protección de aplicaciones, abre una instancia de Protección de aplicaciones. Esto permite recopilar seguimientos adicionales desde dentro del contenedor de protección de aplicaciones.

   3. Seleccione **Iniciar grabación y** espere a que el icono deje de girar y diga Detener *grabación.*

   4. Reproduzca completamente el problema con la Protección de aplicaciones. Esto puede incluir intentar iniciar una instancia de Protección de aplicaciones y esperar hasta que se produce un error, o reproducir un problema en una instancia de Protección de aplicaciones en ejecución.

   5. Selecciona el **icono Detener grabación.**

   6. Mantenga abiertas todas las instancias de protección de aplicaciones en ejecución, incluso hasta unos minutos después del envío, para que también se pueda recopilar el diagnóstico del contenedor.

8. Adjunte capturas de pantalla o archivos relevantes relacionados con el problema.

9. Seleccione **Enviar**.

### <a name="submit-feedback-via-office-customer-voice"></a>Enviar comentarios a través de Office Customer Voice

También puede enviar comentarios desde Office si el problema se produce cuando los documentos de Office se abren en la Protección de aplicaciones. Consulte el Manual [de Office Insider para](https://insider.office.com/handbook) enviar comentarios.

## <a name="integration-with-microsoft-defender-for-endpoint-and-microsoft-defender-for-office-365"></a>Integración con Microsoft Defender para Endpoint y Microsoft Defender para Office 365

Protección de aplicaciones para Office se integra con Microsoft Defender para endpoint para proporcionar supervisión y alertas sobre la actividad malintencionada que tiene lugar en el entorno aislado.

Microsoft Defender para endpoint es una plataforma de seguridad diseñada para ayudar a las redes empresariales a prevenir, detectar, investigar y responder a amenazas avanzadas. Para obtener más información sobre esta plataforma, visita la [página de Microsoft Defender para puntos de](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp) conexión. Obtenga más información sobre la incorporación de dispositivos a esta plataforma en La incorporación de dispositivos [al servicio Microsoft Defender para puntos de conexión.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/onboard-configure)

También puede configurar Microsoft Defender para Office 365 para que funcione con Defender for Endpoint. Consulte [Integrar Defender para Office 365 con Microsoft Defender para Endpoint.](integrate-office-365-ti-with-wdatp.md)

## <a name="limitations-and-considerations"></a>Limitaciones y consideraciones

* Protección de aplicaciones para Office es un modo restringido que aísla a los documentos que no son de confianza del acceso a recursos corporativos de confianza, intranet, identidad del usuario y archivos arbitrarios presentes en el equipo. Como resultado, si un usuario intenta obtener acceso a una característica que tiene una dependencia en dicho acceso, por ejemplo, insertar una imagen desde un archivo local en el disco, se producirá un error y se producirá un mensaje como el siguiente. Para permitir que un documento que no es de confianza obtenga acceso a los recursos de confianza, los usuarios deben quitar la protección de protección de aplicaciones del documento.

  ![Cuadro de diálogo que le ayudará a mantener la seguridad, esta característica no está disponible](../../media/ag10-limitations.png)

  > [!NOTE]
  > Aconseja a los usuarios que solo quiten la protección si confían en el archivo y su origen o de dónde viene.

* El contenido activo en documentos como macros y ActiveX controles están deshabilitados en la Protección de aplicaciones para Office. Los usuarios deben quitar la protección de protección de aplicaciones para habilitar el contenido activo.

* Los archivos que no son de confianza abiertos desde recursos compartidos de red o archivos compartidos desde OneDrive, OneDrive para la Empresa o SharePoint Online desde otra organización se abren como de solo lectura en la Protección de aplicaciones. Los usuarios pueden guardar una copia local de estos archivos para seguir trabajando en el contenedor o quitar la protección para trabajar directamente con el archivo original.

* Los archivos protegidos por Information Rights Management (IRM) siguen abiertos en la vista protegida.

* Las personalizaciones de las aplicaciones de Office en la Protección de aplicaciones para Office no persistirán después de que un usuario cierra sesión y vuelve a abrir o reinicia el dispositivo.

* Solo las herramientas de accesibilidad que usan el marco UIA pueden proporcionar una experiencia accesible para los archivos abiertos en la Protección de aplicaciones para Office.

* La conectividad de red es necesaria para el primer inicio de la Protección de aplicaciones después de la instalación. Esto es necesario para que la Protección de aplicaciones valide la licencia.

* En la sección de información del documento, la propiedad *Last Modified By* puede mostrar WDAGUtilityAccount como el usuario. Este es el usuario anónimo configurado en la Protección de aplicaciones, dado que la identidad del usuario de escritorio no se comparte dentro del contenedor de protección de aplicaciones.

## <a name="performance-optimizations-for-application-guard"></a>Optimizaciones de rendimiento para protección de aplicaciones

En esta sección se proporciona información general sobre las optimizaciones de rendimiento usadas en la Protección de aplicaciones para Office. Esta información puede ayudar a los administradores a diagnosticar informes de usuarios relacionados con el rendimiento de Office o el sistema general cuando la Protección de aplicaciones está habilitada.

La Protección de aplicaciones usa un contenedor virtualizado para aislar los documentos que no son de confianza del sistema. El proceso de crear un contenedor y configurar el contenedor de protección de aplicaciones para abrir documentos de Office tiene una sobrecarga de rendimiento que puede afectar negativamente a la experiencia del usuario cuando los usuarios abren un documento que no es de confianza.

Para proporcionar a los usuarios la experiencia de apertura de archivos esperada, la Protección de aplicaciones usa lógica para crear previamente un contenedor cuando se cumple la siguiente heurística en un sistema: un usuario ha abierto un archivo en vista protegida o protección de aplicaciones en los últimos 28 días.

Cuando se cumple esta heurística, Office creará previamente un contenedor de protección de aplicaciones para el usuario después de iniciar sesión en Windows. Cuando esta operación previa a la creación está en curso, el sistema puede experimentar un rendimiento lento. Esto se resolverá en cuanto finalice la operación.

> [!NOTE]
> Las sugerencias necesarias para la heurística usada para crear previamente el contenedor las generan las aplicaciones de Office a medida que un usuario las usa. Si un usuario instala Office en un nuevo sistema en el que la Protección de aplicaciones está habilitada, Office no creará previamente el contenedor hasta después de la primera vez que un usuario abra un documento que no es de confianza en el sistema. El usuario observará que este primer archivo tarda más en abrirse en la Protección de aplicaciones.

## <a name="known-issues-in-preview"></a>Problemas conocidos en versión preliminar

* Al hacer clic en vínculos web ( `http` o ) no se abre el `https` explorador.
* Las actualizaciones de .NET hacen que los archivos no se abran en la Protección de aplicaciones. Como solución alternativa, los usuarios pueden reiniciar su dispositivo cuando se encuentre este problema. Obtenga más información sobre el problema al recibir un mensaje de error al intentar abrir Windows Defender protección de aplicaciones [o espacio aislado de Windows.](https://support.microsoft.com/help/4575917/receiving-an-error-message-when-attempting-to-open-windows-defender-ap)
