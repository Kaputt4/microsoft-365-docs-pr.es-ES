---
title: Protección de aplicaciones para Office 365 para administradores
keywords: protección de aplicaciones, protección, aislamiento, contenedor aislado, aislamiento de hardware
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Obtenga lo último en aislamiento basado en hardware. Impedir que ataques actuales y emergentes como vulnerabilidades de seguridad o vínculos malintencionados interrumpan la productividad de los empleados y la seguridad de la empresa.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: cf02f6776eb68537486b49c4fe45e8f88eeb38c6
ms.sourcegitcommit: c0cfb9b354db56fdd329aec2a89a9b2cf160c4b0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2021
ms.locfileid: "50094884"
---
# <a name="application-guard-for-office-for-admins"></a>Protección de aplicaciones para Office para administradores

**Se aplica a:** Word, Excel y PowerPoint para Microsoft 365, Windows 10 Enterprise

La Protección de aplicaciones de Microsoft Defender para Office (Protección de aplicaciones para Office) ayuda a evitar que los archivos que no son de confianza accedan a recursos de confianza, lo que mantiene la empresa a salvo de los ataques nuevos y emergentes. En este artículo se guía a los administradores a través de la configuración de dispositivos para obtener una vista previa de la Protección de aplicaciones para Office. Proporciona información sobre los requisitos del sistema y los pasos de instalación para habilitar la Protección de aplicaciones para Office en un dispositivo.

## <a name="prerequisites"></a>Requisitos previos

### <a name="minimum-hardware-requirements"></a>Requisitos mínimos de hardware

* **CPU:** 64 bits, 4 núcleos (físico o virtual), extensiones de virtualización (Intel VT-x O AMD-V), core i5 equivalente o superior recomendado
* **Memoria física:** 8 GB de RAM
* **Disco duro:** 10 GB de espacio libre en la unidad del sistema (se recomienda SSD)

### <a name="minimum-software-requirements"></a>Requisitos mínimos de software

* **Windows 10:** Windows 10 Enterprise Edition, versión de compilación de cliente 2004 (20H1) compilación 19041 o posterior
* **Office:** compilación del canal actual de Office versión 2011 16.0.13530.10000 o posterior. Se admiten las versiones de 32 y 64 bits de Office.
* **Paquete de actualización:** actualización de seguridad mensual acumulativa de Windows 10 [KB4571756](https://support.microsoft.com/help/4571756/windows-10-update-KB4571756)

Para obtener información detallada sobre los requisitos del sistema, consulte [Requisitos del sistema para la Protección de](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/reqs-md-app-guard)aplicaciones de Microsoft Defender. Para obtener más información sobre los canales de actualización de Office, vea Información general sobre los canales [de actualización de Microsoft 365.](https://docs.microsoft.com/deployoffice/overview-update-channels)

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

3. Busque Protección **de aplicaciones de Microsoft Defender en modo administrado,** una directiva de grupo en Plantillas administrativas de configuración del equipo Componentes de Windows Protección de aplicaciones **de Microsoft \\ \\ \\ Defender**. Active esta directiva estableciendo el valor en Opciones como **2** **o 3** y, a continuación, **seleccione Aceptar** o **Aplicar**.

   ![Activar AG en modo administrado](../../media/ag04-deploy.png)

   En su lugar, puedes establecer la directiva CSP correspondiente:

   > OMA-URI: **./Device/Vendor/MSFT/WindowsDefenderApplicationGuard/Settings/AllowWindowsDefenderApplicationGuard** <br> Tipo de datos: **Integer** <br> Valor: **2**

4. Reinicie el sistema.

### <a name="set-diagnostics--feedback-to-send-full-data"></a>Establecer comentarios de & diagnóstico para enviar datos completos

Este paso garantiza que los datos necesarios para identificar y solucionar problemas lleguen a Microsoft. Sigue estos pasos para habilitar el diagnóstico en tu dispositivo Windows:

1. Abra **Configuración** desde el menú Inicio.

   ![Menú Inicio](../../media/ag05-diagnostic.png)

2. En **Configuración de Windows,** seleccione **Privacidad.**

   ![Menú Configuración de Windows](../../media/ag06-diagnostic.png)

3. En Privacidad, seleccione **Diagnósticos & comentarios y** seleccione **Datos de diagnóstico opcionales.**

   ![Menú de diagnóstico y comentarios](../../media/ag07a-diagnostic.png)

Para obtener más información sobre cómo configurar las opciones de diagnóstico de Windows, consulta Configuración de datos de [diagnóstico de Windows en tu organización.](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enterprise-management)

### <a name="confirm-that-application-guard-for-office-is-enabled-and-working"></a>Confirmar que la Protección de aplicaciones para Office está habilitada y funcionando

Antes de confirmar que la Protección de aplicaciones para Office está habilitada, inicie Word, Excel o PowerPoint en un dispositivo donde se hayan implementado las directivas. Asegúrese de que Office está activado. Es posible que primero deba usar su identidad de trabajo para activar el producto de Office.

Para confirmar que la Protección de aplicaciones para Office está habilitada, inicie Word, Excel o PowerPoint y, a continuación, abra un documento que no sea de confianza. Por ejemplo, puede abrir un documento que se descargó de Internet o un archivo adjunto de correo electrónico de alguien externo a su organización.

Al abrir por primera vez un archivo que no es de confianza, es posible que vea una pantalla de presentación de Office como en el ejemplo siguiente. Es posible que se muestre durante algún tiempo mientras se activa la Protección de aplicaciones para Office y se abre el archivo. Las aperturas posteriores de archivos que no son de confianza deben ser más rápidas.

![Pantalla de presentación de la aplicación de Office](../../media/ag08-confirm.png)

Al abrirse, el archivo debe mostrar algunos indicadores visuales de que el archivo se abrió dentro de la Protección de aplicaciones para Office:

* Una llamada en la cinta de opciones

  ![Archivo de documento que muestra una pequeña nota de App Guard](../../media/ag09-confirm.png)

* El icono de la aplicación con un escudo en la barra de tareas

  ![Icono en la barra de tareas](../../media/ag12-limitations.png)

## <a name="configure-application-guard-for-office"></a>Configurar la Protección de aplicaciones para Office

Office admite las siguientes directivas para permitirle configurar las capacidades de protección de aplicaciones para Office. Estas directivas se pueden configurar a través de directivas de grupo o a través del servicio de directivas de nube de Office.

> [!NOTE]
> La configuración de estas directivas puede deshabilitar algunas funcionalidades de los archivos abiertos en la Protección de aplicaciones para Office.

|Policy|Description|
|---|---|
|No usar la Protección de aplicaciones para Office|Habilitar esta directiva forzará a Word, Excel y PowerPoint a usar el contenedor de aislamiento vista protegida en lugar de la Protección de aplicaciones para Office. Esta directiva se puede usar para deshabilitar temporalmente la Protección de aplicaciones para Office cuando haya problemas al dejarla habilitada para Microsoft Edge.|
|Configurar la Protección de aplicaciones para la creación previa del contenedor de Office|Esta directiva determina si el contenedor de protección de aplicaciones para Office, para aislar archivos que no son de confianza, se ha creado previamente para mejorar el rendimiento en tiempo de ejecución. Si habilita esta configuración, puede especificar el número de días para continuar creando previamente un contenedor o permitir que office integrado heurístico cree previamente el contenedor.
|No permitir copiar o pegar documentos de Office abiertos en la Protección de aplicaciones para Office|Si se habilita esta directiva, el usuario no podrá copiar y pegar contenido de un documento abierto en la Protección de aplicaciones para Office en un documento abierto fuera de él.|
|Deshabilitar la aceleración de hardware en la Protección de aplicaciones para Office|Esta directiva controla si la Protección de aplicaciones para Office usa la aceleración de hardware para representar gráficos. Si habilita esta configuración, la Protección de aplicaciones para Office usa la representación basada en software (CPU) y no cargará ningún controlador de gráficos de terceros ni interactuará con ningún hardware gráfico conectado.
|Deshabilitar la protección de tipos de archivo no compatibles en la Protección de aplicaciones para Office|Esta directiva controla si la Protección de aplicaciones para Office bloqueará la apertura de tipos de archivo no compatibles o si habilitará el redireccionamiento a vista protegida.
|Desactivar el acceso a cámara y micrófono para los documentos abiertos en la Protección de aplicaciones para Office|Si se habilita esta directiva, se quitará el acceso de Office a la cámara y al micrófono dentro de la Protección de aplicaciones para Office.|
|Restringir la impresión de documentos abiertos en la Protección de aplicaciones para Office|Si se habilita esta directiva, se limitarán las impresoras en las que un usuario puede imprimir desde un archivo abierto en la Protección de aplicaciones para Office. Por ejemplo, puede usar esta directiva para restringir a los usuarios que solo impriman en PDF.|
|Impedir que los usuarios quiten la protección de aplicaciones para Office en archivos|Si se habilita esta directiva, se quitará la opción (dentro de la experiencia de la aplicación de Office) para deshabilitar la Protección de aplicaciones para Office o para abrir un archivo fuera de la Protección de aplicaciones para Office. <p> **Nota:** Los usuarios aún pueden omitir esta directiva quitando manualmente la propiedad mark-of-the-web del archivo o moviendo un documento a una ubicación de confianza.|
|

> [!NOTE]
> Las siguientes directivas requerirán que el usuario cerrar sesión e iniciar sesión de nuevo en Windows para que su efecto:
>
> * Deshabilitar copiar y pegar para los documentos abiertos en la Protección de aplicaciones para Office
> * Restringir la impresión de documentos abiertos en la Protección de aplicaciones para Office
> * Desactivar el acceso de micrófono y cámara a los documentos abiertos en la Protección de aplicaciones para Office

## <a name="submit-feedback"></a>Enviar comentarios

### <a name="submit-feedback-via-feedback-hub"></a>Enviar comentarios a través del Centro de opiniones

Si se produce algún problema al iniciar la Protección de aplicaciones para Office, se recomienda enviar sus comentarios a través del Centro de opiniones:

1. Abre la aplicación **Centro de opiniones** e inicia sesión.

2. Si aparece un cuadro de diálogo de error al iniciar la Protección de aplicaciones, selecciona Informar a **Microsoft** en el cuadro de diálogo de error para iniciar un nuevo envío de comentarios. De lo contrario, ve a seleccionar la categoría correcta para protección de aplicaciones y, a continuación, selecciona <https://aka.ms/mdagoffice-fb> **+ &nbsp; Agregar nuevos** comentarios cerca de la parte superior derecha.

3. Escriba un resumen en el cuadro **Resumir sus** comentarios si aún no se ha rellenado.

4. Escriba una descripción detallada del problema que experimentó y  los pasos que realizó en el cuadro Explicar con más detalle y, a continuación, **seleccione Siguiente**.

5. Seleccione la burbuja junto a **Problema.** Asegúrese de que la categoría seleccionada es Protección de aplicaciones de Microsoft Defender seguridad y privacidad **\> – Office** y, a continuación, seleccione **Siguiente**.

6. Seleccione **Nuevos comentarios y,** a **continuación, Siguiente.**

7. Recopile seguimientos sobre el problema:

   1. Expande **el icono Volver a crear mi** problema.

   2. Si el problema que estás experimentando se produce mientras se ejecuta la Protección de aplicaciones, abre una instancia de Protección de aplicaciones. Abrir una instancia permite recopilar seguimientos adicionales desde dentro del contenedor de protección de aplicaciones.

   3. Seleccione **Iniciar grabación** y espere a que el icono deje de girar y diga Detener *grabación.*

   4. Reproduzca completamente el problema con la Protección de aplicaciones. La reproducción puede incluir intentar iniciar una instancia de Protección de aplicaciones y esperar hasta que se produce un error, o reproducir un problema en una instancia de Protección de aplicaciones en ejecución.

   5. Selecciona el **icono Detener grabación.**

   6. Mantén abiertas todas las instancias de protección de aplicaciones en ejecución, incluso durante unos minutos después del envío, para que también se puedan recopilar diagnósticos de contenedor.

8. Adjunte capturas de pantalla o archivos relevantes relacionados con el problema.

9. Seleccione **Enviar**.

### <a name="submit-feedback-via-office-customer-voice"></a>Enviar comentarios a través de Office Customer Voice

También puede enviar comentarios desde Office si el problema se produce cuando los documentos de Office se abren en la Protección de aplicaciones. Consulte el Manual [de Office Insider para](https://insider.office.com/handbook) enviar comentarios.

## <a name="integration-with-microsoft-defender-for-endpoint-and-microsoft-defender-for-office-365"></a>Integración con Microsoft Defender para Endpoint y Microsoft Defender para Office 365

Protección de aplicaciones para Office se integra con Microsoft Defender para endpoint para proporcionar supervisión y alertas sobre actividad malintencionada que se produce en el entorno aislado.

Microsoft Defender para Endpoint es una plataforma de seguridad diseñada para ayudar a las redes empresariales a prevenir, detectar, investigar y responder a amenazas avanzadas. Para obtener más información sobre esta plataforma, vea [Microsoft Defender para Endpoint.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp) Para obtener más información sobre la incorporación de dispositivos a esta plataforma, consulta Incorporar dispositivos al servicio [Microsoft Defender para puntos de conexión.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/onboard-configure)

También puede configurar Microsoft Defender para Office 365 para que funcione con Defender for Endpoint. Para obtener más información, consulta [Integrar Defender para Office 365 con Microsoft Defender para Endpoint.](integrate-office-365-ti-with-wdatp.md)

## <a name="limitations-and-considerations"></a>Limitaciones y consideraciones

* Protección de aplicaciones para Office es un modo restringido que aísla documentos que no son de confianza para que no puedan acceder a recursos corporativos de confianza, una intranet, la identidad del usuario y archivos arbitrarios en el equipo. Como resultado, si un usuario intenta obtener acceso a una característica que tiene una dependencia en dicho acceso (por ejemplo, insertar una imagen desde un archivo local en el disco), se producirá un error en el acceso y se producirá un mensaje como el siguiente ejemplo. Para permitir que un documento que no es de confianza obtenga acceso a los recursos de confianza, los usuarios deben quitar la protección de protección de aplicaciones del documento.

  ![Cuadro de diálogo que le ayudará a mantener la seguridad, esta característica no está disponible](../../media/ag10-limitations.png)

  > [!NOTE]
  > Aconseja a los usuarios que solo quiten la protección si confían en el archivo y su origen o de dónde viene.

* El contenido activo en documentos como macros y ActiveX controles están deshabilitados en la Protección de aplicaciones para Office. Los usuarios deben quitar la protección de protección de aplicaciones para habilitar el contenido activo.

* Los archivos que no son de confianza de recursos compartidos de red o archivos compartidos desde OneDrive, OneDrive para la Empresa o SharePoint Online de otra organización se abren como de solo lectura en la Protección de aplicaciones. Los usuarios pueden guardar una copia local de estos archivos para seguir trabajando en el contenedor o quitar la protección para trabajar directamente con el archivo original.

* Los archivos protegidos por Information Rights Management (IRM) están bloqueados de forma predeterminada. Si los usuarios desean abrir estos archivos en vista protegida, un administrador debe configurar las opciones de directiva para los tipos de archivo no admitidos para la organización.

* Las personalizaciones de las aplicaciones de Office en la Protección de aplicaciones para Office no persistirán después de que un usuario cierra sesión e inicia sesión de nuevo o después de que se reinicie el dispositivo.

* Solo las herramientas de accesibilidad que usan el marco UIA pueden proporcionar una experiencia accesible para los archivos abiertos en la Protección de aplicaciones para Office.

* La conectividad de red es necesaria para el primer inicio de la Protección de aplicaciones después de la instalación. Se requiere conectividad para que la Protección de aplicaciones valide la licencia.

* En la sección de información del documento, la propiedad *Last Modified By* puede mostrar **WDAGUtilityAccount** como el usuario. WDAGUtilityAccount es el usuario anónimo configurado en la Protección de aplicaciones. La identidad del usuario de escritorio no se comparte dentro del contenedor de protección de aplicaciones.

## <a name="performance-optimizations-for-application-guard-for-office"></a>Optimizaciones de rendimiento para la Protección de aplicaciones para Office

En esta sección se proporciona información general sobre las optimizaciones de rendimiento usadas en la Protección de aplicaciones para Office. Esta información puede ayudar a los administradores a diagnosticar informes de usuarios relacionados con el rendimiento de Office o el sistema general cuando la Protección de aplicaciones está habilitada.

La Protección de aplicaciones usa un contenedor virtualizado para aislar documentos que no son de confianza del sistema. El proceso de crear un contenedor y configurar el contenedor de protección de aplicaciones para abrir documentos de Office tiene una sobrecarga de rendimiento que puede afectar negativamente a la experiencia del usuario cuando los usuarios abren un documento que no es de confianza.

Para proporcionar a los usuarios la experiencia de apertura de archivos esperada, la Protección de aplicaciones usa lógica para crear previamente un contenedor cuando se cumple la siguiente heurística en un sistema: un usuario ha abierto un archivo en vista protegida o protección de aplicaciones en los últimos 28 días.

Cuando se cumple esta heurística, Office creará previamente un contenedor de protección de aplicaciones para el usuario después de iniciar sesión en Windows. Mientras esta operación previa a la creación está en curso, el sistema puede experimentar un rendimiento lento, pero el efecto se resolverá en cuanto finalice la operación.

> [!NOTE]
> Las sugerencias necesarias para que la heurística cree previamente el contenedor las generan las aplicaciones de Office a medida que un usuario las usa. Si un usuario instala Office en un nuevo sistema en el que la Protección de aplicaciones está habilitada, Office no creará previamente el contenedor hasta después de la primera vez que un usuario abra un documento que no es de confianza en el sistema. El usuario observará que este primer archivo tarda más en abrirse en la Protección de aplicaciones.

## <a name="known-issues"></a>Problemas conocidos

* La selección de vínculos web ( `http` o ) no abre el `https` explorador.
* Por el momento, no se admite pegar contenido o imágenes en formato de texto enriquecido (RTF) en documentos de Office abiertos con la Protección de aplicaciones.
* Las actualizaciones de .NET hacen que los archivos no se abran en la Protección de aplicaciones. Como solución alternativa, los usuarios pueden reiniciar su dispositivo cuando se den cuenta de este error. Obtenga más información sobre el problema al recibir un mensaje de error al intentar abrir Windows Defender protección de aplicaciones [o espacio aislado de Windows.](https://support.microsoft.com/help/4575917/receiving-an-error-message-when-attempting-to-open-windows-defender-ap)
