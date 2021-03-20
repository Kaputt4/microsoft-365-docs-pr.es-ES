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
description: Obtenga lo último en aislamiento basado en hardware. Evite que ataques actuales y emergentes como vulnerabilidades o vínculos malintencionados interrumpan la productividad de los empleados y la seguridad empresarial.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a13196080aa0084411b737bfc157bbdb4b243a40
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907173"
---
# <a name="application-guard-for-office-for-admins"></a>Protección de aplicaciones para Office para administradores

**Se aplica a:** Word, Excel y PowerPoint para Microsoft 365, Windows 10 Enterprise

La Protección de aplicaciones de Microsoft Defender para Office (Application Guard for Office) ayuda a evitar que los archivos que no son de confianza tengan acceso a recursos de confianza, lo que mantiene a su empresa a salvo de ataques nuevos y emergentes. En este artículo se guía a los administradores a través de la configuración de dispositivos para una vista previa de Application Guard para Office. Proporciona información sobre los requisitos del sistema y los pasos de instalación para habilitar Application Guard para Office en un dispositivo.

## <a name="prerequisites"></a>Requisitos previos

### <a name="minimum-hardware-requirements"></a>Requisitos mínimos de hardware

* **CPU:** 64 bits, 4 núcleos (físicos o virtuales), extensiones de virtualización (Intel VT-x O AMD-V), core i5 equivalente o superior recomendado
* **Memoria física**: 8 GB de RAM
* **Disco duro:** 10 GB de espacio libre en la unidad del sistema (ssd recomendado)

### <a name="minimum-software-requirements"></a>Requisitos mínimos de software

* **Windows 10:** Windows 10 Enterprise edition, versión de compilación de cliente 2004 (20H1) compilación 19041 o posterior
* **Office**: Office Current Channel Build version 2011 16.0.13530.10000 o posterior. Se admiten versiones de Office de 32 bits y 64 bits.
* **Paquete de actualización:** actualización de seguridad mensual acumulativa de Windows 10 [KB4571756](https://support.microsoft.com/help/4571756/windows-10-update-KB4571756)

Para obtener información detallada sobre los requisitos del sistema, consulte [System requirements for Microsoft Defender Application Guard](/windows/security/threat-protection/microsoft-defender-application-guard/reqs-md-app-guard). Para obtener más información sobre los canales de actualización de Office, vea [Overview of update channels for Microsoft 365](/deployoffice/overview-update-channels).

### <a name="licensing-requirements"></a>Requisitos de licencia

* Seguridad de Microsoft 365 E5 o Microsoft 365 E5

## <a name="deploy-application-guard-for-office"></a>Implementar Application Guard para Office

### <a name="enable-application-guard-for-office"></a>Habilitar Application Guard para Office

1. Descargar e instalar actualizaciones de seguridad mensuales acumulativas de **Windows 10 KB4571756**.

2. Selecciona **Protección de aplicaciones de Microsoft Defender** en Características de Windows y selecciona **Aceptar**. Al habilitar la característica de Protección de aplicaciones, se pedirá un reinicio del sistema. Puede elegir reiniciar ahora o después del paso 3.

   ![Cuadro de diálogo Características de Windows que muestra AG](../../media/ag03-deploy.png)

   La característica también se puede habilitar ejecutando el siguiente comando de PowerShell como administrador:

   ```powershell
   Enable-WindowsOptionalFeature -online -FeatureName Windows-Defender-ApplicationGuard
   ```

3. Busque Protección **de aplicaciones de Microsoft Defender en modo** administrado , una directiva de grupo en Configuración del equipo Plantillas administrativas Componentes de Windows Componentes de Microsoft Defender Application **\\ \\ \\ Guard**. Active esta directiva estableciendo el valor en Opciones como **2** o **3** y, a continuación, **seleccione Aceptar** o **Aplicar**.

   ![Activar AG en modo administrado](../../media/ag04-deploy.png)

   En su lugar, puede establecer la directiva CSP correspondiente:

   > OMA-URI: **./Device/Vendor/MSFT/WindowsDefenderApplicationGuard/Settings/AllowWindowsDefenderApplicationGuard** <br> Tipo de datos: **Integer** <br> Valor: **2**

4. Reinicie el sistema.

### <a name="set-diagnostics--feedback-to-send-full-data"></a>Establecer comentarios de & diagnóstico para enviar datos completos

Este paso garantiza que los datos necesarios para identificar y corregir problemas lleguen a Microsoft. Sigue estos pasos para habilitar el diagnóstico en tu dispositivo Windows:

1. Abre **Configuración** desde el menú Inicio.

   ![Menú Inicio](../../media/ag05-diagnostic.png)

2. En **Configuración de Windows,** seleccione **Privacidad**.

   ![Menú Configuración de Windows](../../media/ag06-diagnostic.png)

3. En Privacidad, seleccione **Diagnósticos & comentarios y** seleccione **Datos de diagnóstico opcionales.**

   ![Menú diagnóstico y comentarios](../../media/ag07a-diagnostic.png)

Para obtener más información sobre cómo configurar las opciones de diagnóstico de Windows, consulte [Configuring Windows diagnostic data in your organization](/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enterprise-management).

### <a name="confirm-that-application-guard-for-office-is-enabled-and-working"></a>Confirmar que Application Guard para Office está habilitado y funcionando

Antes de confirmar que Application Guard para Office está habilitado, inicie Word, Excel o PowerPoint en un dispositivo donde se hayan implementado las directivas. Asegúrese de que Office está activado. Es posible que deba usar su identidad de trabajo para activar primero el producto de Office.

Para confirmar que Application Guard para Office está habilitado, inicie Word, Excel o PowerPoint y, a continuación, abra un documento que no sea de confianza. Por ejemplo, puede abrir un documento que se descargó de Internet o un archivo adjunto de correo electrónico de alguien fuera de su organización.

Al abrir por primera vez un archivo que no es de confianza, puede que vea una pantalla de presentación de Office como en el siguiente ejemplo. Es posible que se muestre durante algún tiempo mientras se activa Application Guard para Office y se abre el archivo. Las aperturas posteriores de archivos que no son de confianza deben ser más rápidas.

![Pantalla de presentación de la aplicación de Office](../../media/ag08-confirm.png)

Al abrirse, el archivo debe mostrar algunos indicadores visuales de que el archivo se abrió dentro de Application Guard para Office:

* Una llamada en la cinta de opciones

  ![Archivo doc que muestra una pequeña nota de App Guard](../../media/ag09-confirm.png)

* Icono de aplicación con un escudo en la barra de tareas

  ![Icono en la barra de tareas](../../media/ag12-limitations.png)

## <a name="configure-application-guard-for-office"></a>Configurar Application Guard para Office

Office admite las siguientes directivas para permitirle configurar las capacidades de Application Guard para Office. Estas directivas se pueden configurar a través de directivas de grupo o a través del servicio de directivas en la nube de Office.

> [!NOTE]
> La configuración de estas directivas puede deshabilitar algunas funcionalidades de los archivos abiertos en Application Guard para Office.

|Directiva|Descripción|
|---|---|
|No usar Application Guard para Office|Habilitar esta directiva forzará a Word, Excel y PowerPoint a usar el contenedor de aislamiento vista protegida en lugar de Application Guard para Office. Esta directiva se puede usar para deshabilitar temporalmente Application Guard para Office cuando haya problemas al dejarla habilitada para Microsoft Edge.|
|Configurar la creación previa del contenedor de Office de Application Guard para Office|Esta directiva determina si el contenedor de Application Guard para Office, para aislar archivos que no son de confianza, se ha creado previamente para mejorar el rendimiento en tiempo de ejecución. Si habilita esta configuración, puede especificar el número de días para continuar creando previamente un contenedor o permitir que la heurística integrada de Office cree previamente el contenedor.
|No permitir copiar o pegar documentos de Office abiertos en Application Guard para Office|Habilitar esta directiva impedirá que un usuario copie y pega contenido de un documento abierto en Application Guard para Office en un documento abierto fuera de él.|
|Deshabilitar la aceleración de hardware en Application Guard para Office|Esta directiva controla si Application Guard para Office usa la aceleración de hardware para representar gráficos. Si habilita esta configuración, Application Guard para Office usa la representación basada en software (CPU) y no cargará ningún controlador de gráficos de terceros ni interactuará con ningún hardware gráfico conectado.
|Deshabilitar la protección de tipos de archivo no compatibles en Application Guard para Office|Esta directiva controla si Application Guard para Office bloqueará la apertura de tipos de archivo no admitidos o si habilitará la redirección a vista protegida.
|Desactivar el acceso a cámara y micrófono para documentos abiertos en Application Guard para Office|Al habilitar esta directiva, se quitará el acceso de Office a la cámara y al micrófono dentro de Application Guard para Office.|
|Restringir la impresión de documentos abiertos en Application Guard para Office|Al habilitar esta directiva, se limitarán las impresoras en las que un usuario puede imprimir desde un archivo abierto en Application Guard para Office. Por ejemplo, puede usar esta directiva para restringir que los usuarios solo impriman en PDF.|
|Impedir que los usuarios quiten Application Guard para la protección de Office en archivos|Al habilitar esta directiva, se quitará la opción (dentro de la experiencia de la aplicación de Office) para deshabilitar Application Guard para la protección de Office o para abrir un archivo fuera de Application Guard para Office. <p> **Nota:** Los usuarios aún pueden omitir esta directiva quitando manualmente la propiedad mark-of-the-web del archivo o moviendo un documento a una ubicación de confianza.|
|

> [!NOTE]
> Las siguientes directivas requerirán que el usuario inicie sesión de nuevo en Windows para que su efecto:
>
> * Deshabilitar la copia y pegado de documentos abiertos en Application Guard para Office
> * Restringir la impresión de documentos abiertos en Application Guard para Office
> * Desactivar el acceso de cámara y micrófono a documentos abiertos en Application Guard para Office

## <a name="submit-feedback"></a>Enviar comentarios

### <a name="submit-feedback-via-feedback-hub"></a>Enviar comentarios a través del Centro de opiniones

Si encuentra algún problema al iniciar Application Guard para Office, se le recomienda enviar sus comentarios a través del Centro de opiniones:

1. Abre la **aplicación Centro de opiniones** e inicia sesión.

2. Si obtiene un cuadro de diálogo de error al iniciar Protección de aplicaciones, seleccione Informar a **Microsoft** en el cuadro de diálogo de error para iniciar un nuevo envío de comentarios. De lo contrario, vaya a para seleccionar la categoría correcta para Protección de aplicaciones y, a continuación, seleccione <https://aka.ms/mdagoffice-fb> **+ &nbsp; Agregar nuevos comentarios** cerca de la parte superior derecha.

3. Escriba un resumen en el cuadro **Resumir** sus comentarios si aún no está rellenado por usted.

4. Escriba una descripción detallada del problema que experimentó y  los pasos que realizó en el cuadro Explicar con más detalle y, a continuación, **seleccione Siguiente**.

5. Seleccione la burbuja junto a **Problema**. Asegúrese de que la categoría seleccionada es Seguridad y privacidad Protección de aplicaciones de **Microsoft Defender – \> Office** y, a continuación, **seleccione Siguiente**.

6. Seleccione **Nuevos comentarios** y, a **continuación, Siguiente**.

7. Recopilar seguimientos sobre el problema:

   1. Expanda el **icono Volver a crear mi** problema.

   2. Si el problema que está experimentando se produce mientras se ejecuta Application Guard, abra una instancia de Application Guard. Abrir una instancia permite recopilar seguimientos adicionales desde dentro del contenedor de Application Guard.

   3. Seleccione **Iniciar grabación** y espere a que el icono deje de girar y diga Detener *grabación.*

   4. Reproduce completamente el problema con Application Guard. La reproducción puede incluir intentar iniciar una instancia de Application Guard y esperar hasta que se produce un error, o reproducir un problema en una instancia de Application Guard en ejecución.

   5. Seleccione el **icono Detener grabación.**

   6. Mantenga abiertas todas las instancias de Application Guard en ejecución, incluso durante unos minutos después del envío, para que también se puedan recopilar diagnósticos de contenedor.

8. Adjunte las capturas de pantalla o archivos relevantes relacionados con el problema.

9. Seleccione **Enviar**.

### <a name="submit-feedback-via-office-customer-voice"></a>Enviar comentarios a través de Office Customer Voice

También puede enviar comentarios desde Office si el problema se produce cuando se abren documentos de Office en Application Guard. Consulte el [Manual de Office Insider](https://insider.office.com/handbook) para enviar comentarios.

## <a name="integration-with-microsoft-defender-for-endpoint-and-microsoft-defender-for-office-365"></a>Integración con Microsoft Defender para Endpoint y Microsoft Defender para Office 365

Application Guard para Office se integra con Microsoft Defender para Endpoint para proporcionar supervisión y alertas sobre actividad malintencionada que se produce en el entorno aislado.

Microsoft Defender para endpoint es una plataforma de seguridad diseñada para ayudar a las redes empresariales a prevenir, detectar, investigar y responder a amenazas avanzadas. Para obtener más información acerca de esta plataforma, consulte [Microsoft Defender for Endpoint](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp). Para obtener más información acerca de la incorporación de dispositivos a esta plataforma, consulte Incorporación de dispositivos [al servicio Microsoft Defender para endpoints](/windows/security/threat-protection/microsoft-defender-atp/onboard-configure).

También puede configurar Microsoft Defender para Office 365 para que funcione con Defender for Endpoint. Para obtener más información, consulte [Integrar Defender para Office 365 con Microsoft Defender para endpoint](integrate-office-365-ti-with-wdatp.md).

## <a name="limitations-and-considerations"></a>Limitaciones y consideraciones

* Application Guard para Office es un modo restringido que aísla documentos que no son de confianza para que no puedan tener acceso a recursos corporativos de confianza, una intranet, la identidad del usuario y archivos arbitrarios en el equipo. Como resultado, si un usuario intenta obtener acceso a una característica que depende de dicho acceso (por ejemplo, insertar una imagen de un archivo local en el disco), el acceso producirá un error y producirá un mensaje como el siguiente ejemplo. Para habilitar un documento que no es de confianza para obtener acceso a recursos de confianza, los usuarios deben quitar la protección de Protección de aplicaciones del documento.

  ![Cuadro de diálogo que dice Para ayudarle a mantener la seguridad, esta característica no está disponible](../../media/ag10-limitations.png)

  > [!NOTE]
  > Aconseje a los usuarios que solo quiten la protección si confían en el archivo y su origen o de dónde provenía.

* El contenido activo en documentos como macros y controles ActiveX están deshabilitados en Application Guard para Office. Los usuarios deben quitar la protección de Protección de aplicaciones para habilitar el contenido activo.

* Los archivos que no son de confianza de recursos compartidos de red o archivos compartidos de OneDrive, OneDrive para la Empresa o SharePoint Online de una organización diferente se abren como de solo lectura en Application Guard. Los usuarios pueden guardar una copia local de estos archivos para continuar trabajando en el contenedor o quitar la protección para trabajar directamente con el archivo original.

* Los archivos protegidos por Information Rights Management (IRM) se bloquean de forma predeterminada. Si los usuarios desean abrir estos archivos en la vista protegida, un administrador debe configurar la configuración de directiva para los tipos de archivo no admitidos para la organización.

* Las personalizaciones de aplicaciones de Office en Application Guard para Office no persistirán después de que un usuario cierra sesión e inicia sesión de nuevo o después de reiniciar el dispositivo.

* Solo las herramientas de accesibilidad que usan el marco UIA pueden proporcionar una experiencia accesible para los archivos abiertos en Application Guard para Office.

* La conectividad de red es necesaria para el primer inicio de Application Guard después de la instalación. La conectividad es necesaria para que Application Guard valide la licencia.

* En la sección información del documento, la propiedad *Last Modified By* puede mostrar **WDAGUtilityAccount** como usuario. WDAGUtilityAccount es el usuario anónimo configurado en Application Guard. La identidad del usuario de escritorio no se comparte dentro del contenedor de Application Guard.

## <a name="performance-optimizations-for-application-guard-for-office"></a>Optimizaciones de rendimiento para Application Guard para Office

En esta sección se proporciona información general sobre las optimizaciones de rendimiento usadas en Application Guard para Office. Esta información puede ayudar a los administradores a diagnosticar informes de usuarios relacionados con el rendimiento de Office o el sistema general cuando Application Guard está habilitado.

Application Guard usa un contenedor virtualizado para aislar documentos que no son de confianza lejos del sistema. El proceso de creación de un contenedor y configuración del contenedor de Application Guard para abrir documentos de Office tiene una sobrecarga de rendimiento que puede afectar negativamente a la experiencia del usuario cuando los usuarios abren un documento que no es de confianza.

Para proporcionar a los usuarios la experiencia de apertura de archivos esperada, Application Guard usa lógica para crear previamente un contenedor cuando se cumple la siguiente heurística en un sistema: un usuario ha abierto un archivo en vista protegida o protección de aplicaciones en los últimos 28 días.

Cuando se cumple esta heurística, Office creará previamente un contenedor de Application Guard para el usuario después de iniciar sesión en Windows. Aunque esta operación previa a la creación está en curso, el sistema puede experimentar un rendimiento lento, pero el efecto se resolverá tan pronto como se complete la operación.

> [!NOTE]
> Las aplicaciones de Office generan las sugerencias necesarias para que los heurísticos creen previamente el contenedor a medida que un usuario las usa. Si un usuario instala Office en un nuevo sistema donde Application Guard está habilitado, Office no creará previamente el contenedor hasta después de la primera vez que un usuario abra un documento que no sea de confianza en el sistema. El usuario observará que este primer archivo tarda más tiempo en abrirse en Application Guard.

## <a name="known-issues"></a>Problemas conocidos

* La selección de vínculos web ( `http` o ) no abre el `https` explorador.
* En este momento, no se admite pegar contenido o imágenes de formato de texto enriquecido (RTF) en documentos de Office abiertos con Application Guard.
* Las actualizaciones de .NET hacen que los archivos no se abran en Application Guard. Como solución alternativa, los usuarios pueden reiniciar su dispositivo cuando se tomen este error. Obtenga más información sobre el problema en Recibir un mensaje de error al intentar abrir Windows Defender Protección de [aplicaciones o Espacio aislado de Windows](https://support.microsoft.com/help/4575917/receiving-an-error-message-when-attempting-to-open-windows-defender-ap).