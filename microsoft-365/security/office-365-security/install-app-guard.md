---
title: Protección de aplicaciones para Office para administradores
keywords: protección de aplicaciones, protección, aislamiento, contenedor aislado, aislamiento de hardware
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
manager: dansimp
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Obtenga lo último en aislamiento basado en hardware. Evite que ataques actuales y emergentes, como vulnerabilidades de seguridad o vínculos malintencionados, interrumpan la productividad de los empleados y la seguridad empresarial.
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: 49056945f7c507c6f1d7c62684035e518c7ce549
ms.sourcegitcommit: 2b89bcff547e00be3d38dc8d1e6cbcf8f41eba42
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2022
ms.locfileid: "67599701"
---
# <a name="application-guard-for-office-for-admins"></a>Protección de aplicaciones para Office para administradores

**Se aplica a:** Aplicaciones de Word, Excel y PowerPoint para Microsoft 365, Windows 10 Enterprise, Windows 11 Empresas

Protección de aplicaciones de Microsoft Defender para Office (Protección de aplicaciones para Office) ayuda a evitar que los archivos que no son de confianza accedan a recursos de confianza, lo que mantiene a su empresa a salvo de ataques nuevos y emergentes. En este artículo se guía a los administradores a través de la configuración de dispositivos para una versión preliminar de Application Guard para Office. Proporciona información sobre los requisitos del sistema y los pasos de instalación para habilitar Application Guard para Office en un dispositivo.

## <a name="prerequisites"></a>Requisitos previos

### <a name="minimum-hardware-requirements"></a>Requisitos mínimos de hardware

* **CPU**: 64 bits, 4 núcleos (físicos o virtuales), extensiones de virtualización (Intel VT-x O AMD-V), core i5 equivalente o superior recomendado
* **Memoria física**: 8 GB de RAM
* **Disco duro**: 10 GB de espacio libre en la unidad del sistema (ssd recomendado)

### <a name="minimum-software-requirements"></a>Requisitos mínimos de software

* **Windows**: edición Windows 10 Enterprise, compilación de cliente 2004 (20H1) compilación 19041 o posterior. Se admiten todas las versiones de Windows 11.
* **Office**: Aplicaciones Microsoft 365 con la compilación 16.0.13530.10000 o posterior. Para las instalaciones de Canal actual y Canal mensual de empresa, es igual a la versión 2011. Para Semi-Annual Enterprise Channel y Semi-Annual Enterprise Channel (versión preliminar), la versión mínima es 2108 o posterior. Se admiten versiones de 32 y 64 bits.
* **Paquete de actualización**: Windows 10 actualización de seguridad mensual acumulativa [KB4571756](https://support.microsoft.com/help/4571756/windows-10-update-KB4571756)

Para conocer los requisitos detallados del sistema, consulte [Requisitos del sistema para Protección de aplicaciones de Microsoft Defender](/windows/security/threat-protection/microsoft-defender-application-guard/reqs-md-app-guard). Además, consulte las guías del fabricante del equipo sobre cómo habilitar la tecnología de virtualización.
Para obtener más información sobre Aplicaciones Microsoft 365 canales de actualización, consulte [Introducción a los canales de actualización para Aplicaciones Microsoft 365](/deployoffice/overview-update-channels).

### <a name="licensing-requirements"></a>Requisitos de licencias

* Seguridad de Microsoft 365 E5
* Microsoft 365 A5 para profesores
* Microsoft 365 A5 para estudiantes

> [!NOTE]
> Aplicaciones Microsoft 365 para empresas con activación de equipos compartidos o licencias basadas en dispositivos no tienen acceso a Application Guard para Office.
>
> Los planes de licencia de documentos seguros permiten el acceso a Application Guard para Office. Para obtener más información, vea [Documentos seguros en Microsoft 365 E5/A5](/microsoft-365/security/office-365-security/safe-docs).

## <a name="deploy-application-guard-for-office"></a>Implementación de Application Guard para Office

### <a name="enable-application-guard-for-office"></a>Habilitar Protección de aplicaciones para Office

1. Descargue e instale **Windows 10 actualizaciones de seguridad mensuales acumulativas KB4571756**.

2. Seleccione **Protección de aplicaciones de Microsoft Defender** en Características de Windows y seleccione **Aceptar**. Al habilitar la característica Protección de aplicaciones, se solicitará un reinicio del sistema. Puede optar por reiniciar ahora o después del paso 3.

   :::image type="content" source="../../media/ag03-deploy.png" alt-text="Cuadro de diálogo Características de Windows que muestra el grupo de disponibilidad" lightbox="../../media/ag03-deploy.png":::

   La característica también se puede habilitar ejecutando el siguiente comando de PowerShell como administrador:

   ```powershell
   Enable-WindowsOptionalFeature -online -FeatureName Windows-Defender-ApplicationGuard
   ```

3. Busque **Protección de aplicaciones de Microsoft Defender en modo administrado**, una directiva de grupo en **Configuración\\del equipo Plantillas\\administrativas Componentes\\ de Windows Protección de aplicaciones de Microsoft Defender**. Para activar esta directiva, establezca el valor en Opciones como **2** o **3** y, a continuación, seleccione **Aceptar** o **Aplicar**.

   :::image type="content" source="../../media/ag04-deploy.png" alt-text="Opción para activar el grupo de disponibilidad en modo administrado" lightbox="../../media/ag04-deploy.png":::

   En su lugar, puede establecer la directiva CSP correspondiente:

   > OMA-URI: **./Device/Vendor/MSFT/WindowsDefenderApplicationGuard/Settings/AllowWindowsDefenderApplicationGuard** <br> Tipo de datos: **Integer** <br> Valor: **2**

4. Reinicie el sistema.

### <a name="set-diagnostics--feedback-to-send-full-data"></a>Establecer diagnósticos & comentarios para enviar datos completos

> [!NOTE]
> Esto no es necesario, pero la configuración de datos de diagnóstico opcionales ayudará a diagnosticar los problemas notificados.

Este paso garantiza que los datos necesarios para identificar y corregir problemas lleguen a Microsoft. Siga estos pasos para habilitar los diagnósticos en el dispositivo Windows:

1. Abra **Configuración** en el menú Inicio.

   :::image type="content" source="../../media/ag05-diagnostic.png" alt-text="Menú Inicio" lightbox="../../media/ag05-diagnostic.png":::

2. En **Configuración de Windows**, seleccione **Privacidad**.

   :::image type="content" source="../../media/ag06-diagnostic.png" alt-text="Menú Configuración de Windows" lightbox="../../media/ag06-diagnostic.png":::

3. En Privacidad, seleccione **Diagnóstico & comentarios** y seleccione **Datos de diagnóstico opcionales**.

   :::image type="content" source="../../media/ag07a-diagnostic.png" alt-text="Menú Diagnósticos y comentarios" lightbox="../../media/ag07a-diagnostic.png":::

Para obtener más información sobre cómo configurar las opciones de diagnóstico de Windows, consulte [Configuración de datos de diagnóstico de Windows en su organización](/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enterprise-management).

### <a name="confirm-that-application-guard-for-office-is-enabled-and-working"></a>Confirme que Application Guard para Office está habilitado y funcionando.

Antes de confirmar que Application Guard para Office está habilitado, inicie Word, Excel o PowerPoint en un dispositivo donde se hayan implementado las directivas. Asegúrese de que Office está activado. Es posible que tenga que usar su identidad de trabajo para activar primero el producto de Office.

Para confirmar que Application Guard para Office está habilitado, inicie Word, Excel o PowerPoint y, a continuación, abra un documento que no sea de confianza. Por ejemplo, puede abrir un documento que se descargó de Internet o un archivo adjunto de correo electrónico de alguien fuera de su organización.

Cuando abra por primera vez un archivo que no es de confianza, es posible que vea una pantalla de presentación de Office como en el ejemplo siguiente. Es posible que se muestre durante algún tiempo mientras se activa Application Guard para Office y se abre el archivo. Las aperturas posteriores de archivos que no son de confianza deben ser más rápidas.

:::image type="content" source="../../media/ag08-confirm.png" alt-text="Página de presentación de la aplicación de Office" lightbox="../../media/ag08-confirm.png":::

Al abrirse, el archivo debe mostrar algunos indicadores visuales de que el archivo se abrió dentro de Application Guard para Office:

* Una llamada en la cinta de opciones

  :::image type="content" source="../../media/ag09-confirm.png" alt-text="El archivo doc que muestra una pequeña nota de App Guard" lightbox="../../media/ag09-confirm.png":::

* Icono de aplicación con un escudo en la barra de tareas

  ![Icono en la barra de tareas.](../../media/ag12-limitations.png)

## <a name="configure-application-guard-for-office"></a>Configuración de Application Guard para Office

Office admite las siguientes directivas para permitirle configurar las funcionalidades de Application Guard para Office. Estas directivas se pueden configurar a través de directivas de grupo o a través del [servicio de directivas en la nube de Office](/DeployOffice/overview-office-cloud-policy-service).

> [!NOTE]
> La configuración de estas directivas puede deshabilitar algunas funcionalidades para los archivos abiertos en Application Guard para Office.

|Policy|Descripción|
|---|---|
|No usar Application Guard para Office|La habilitación de esta directiva obligará a Word, Excel y PowerPoint a usar el contenedor de aislamiento vista protegida en lugar de Application Guard para Office. Esta directiva se puede usar para deshabilitar temporalmente Application Guard para Office cuando haya problemas al dejarla habilitada para Microsoft Edge.|
|Configuración de la creación previa del contenedor de Application Guard para Office|Esta directiva determina si el contenedor de Application Guard para Office, para aislar archivos que no son de confianza, se crea previamente para mejorar el rendimiento en tiempo de ejecución. Si habilita esta configuración, puede especificar el número de días para continuar creando previamente un contenedor o permitir que la heurística integrada de Office cree previamente el contenedor.
|No permitir copiar y pegar documentos de Office abiertos en Protección de aplicaciones para Office|Habilitar esta directiva impedirá que un usuario copie y pegue contenido de un documento abierto en Application Guard para Office en un documento abierto fuera de él.|
|Deshabilitación de la aceleración de hardware en Application Guard para Office|Esta directiva controla si Application Guard para Office usa la aceleración de hardware para representar gráficos. Si habilita esta configuración, Application Guard para Office usa la representación basada en software (CPU) y no cargará ningún controlador de gráficos de terceros ni interactuará con ningún hardware de gráficos conectado.
|Deshabilitación de la protección de tipos de archivo no admitidos en Application Guard para Office|Esta directiva controla si Application Guard para Office impedirá que se abran tipos de archivo no admitidos o si habilitará el redireccionamiento a la vista protegida.
|Desactivar el acceso de cámara y micrófono para los documentos abiertos en Protección de aplicaciones para Office|Al habilitar esta directiva, se quitará el acceso de Office a la cámara y al micrófono dentro de Application Guard para Office.|
|Restricción de la impresión de documentos abiertos en Application Guard para Office|Al habilitar esta directiva, se limitarán las impresoras en las que un usuario puede imprimir desde un archivo abierto en Application Guard para Office. Por ejemplo, puede usar esta directiva para restringir a los usuarios que solo impriman en PDF.|
|Impedir que los usuarios quiten protección de Application Guard para Office en los archivos|Al habilitar esta directiva, se quitará la opción (dentro de la experiencia de aplicación de Office) para deshabilitar Protección de aplicaciones para Protección de Office o para abrir un archivo fuera de Application Guard para Office. <p> **Nota:** Los usuarios todavía pueden omitir esta directiva quitando manualmente la propiedad mark-of-the-web del archivo o moviendo un documento a una ubicación de confianza.|

> [!NOTE]
> Las siguientes directivas requerirán que el usuario cierre la sesión e inicie sesión de nuevo en Windows para que surta efecto:
>
> * Deshabilitación de copiar y pegar para documentos abiertos en Protección de aplicaciones para Office
> * Restricción de la impresión de documentos abiertos en Application Guard para Office
> * Desactivar el acceso de cámara y micrófono a los documentos abiertos en Protección de aplicaciones para Office

## <a name="submit-feedback"></a>Enviar comentarios

### <a name="submit-feedback-via-feedback-hub"></a>Enviar comentarios a través del Centro de comentarios

Si encuentra algún problema al iniciar Application Guard para Office, se recomienda enviar sus comentarios a través del Centro de comentarios:

1. Abra la **aplicación Centro de comentarios** e inicie sesión.

2. Si aparece un cuadro de diálogo de error al iniciar Application Guard, seleccione **Notificar a Microsoft** en el cuadro de diálogo de error para iniciar un nuevo envío de comentarios. De lo contrario, vaya a <https://aka.ms/mdagoffice-fb> para seleccionar la categoría correcta para Protección de aplicaciones y, a continuación, seleccione **+&nbsp;Agregar nuevos comentarios** cerca de la parte superior derecha.

3. Escriba un resumen en el cuadro **Resumir sus comentarios** si aún no se ha rellenado automáticamente.

4. Escriba una descripción detallada del problema que ha experimentado y qué pasos ha realizado en el cuadro **Explicar con más detalle** y, a continuación, seleccione **Siguiente**.

5. Seleccione la burbuja junto a **Problema**. Asegúrese de que la categoría seleccionada es **Seguridad y privacidad \> Protección de aplicaciones de Microsoft Defender – Office** y, a continuación, seleccione **Siguiente**.

6. Seleccione **Nuevos comentarios** y, a continuación, **Siguiente**.

7. Recopilar seguimientos sobre el problema:

   1. Expanda el icono **Volver a crear mi problema** .

   2. Si el problema que está experimentando se produce mientras se ejecuta Application Guard, abra una instancia de Application Guard. La apertura de una instancia permite recopilar seguimientos adicionales desde dentro del contenedor de Application Guard.

   3. Seleccione **Iniciar grabación** y espere a que el icono deje de girar y diga *Detener grabación*.

   4. Reproduzca completamente el problema con Application Guard. La reproducción puede incluir intentar iniciar una instancia de Application Guard y esperar hasta que se produzca un error o reproducir un problema en una instancia de Application Guard en ejecución.

   5. Seleccione el icono **Detener grabación** .

   6. Mantenga abiertas las instancias de Application Guard en ejecución, incluso durante unos minutos después del envío, para que también se puedan recopilar diagnósticos de contenedor.

8. Adjunte las capturas de pantalla o archivos pertinentes relacionados con el problema.

9. Seleccione **Enviar**.

### <a name="submit-feedback-via-office-customer-voice"></a>Enviar comentarios a través de Office Customer Voice

También puede enviar comentarios desde Dentro de Office si el problema se produce cuando los documentos de Office se abren en Application Guard. Consulte el [Manual de Office Insider](https://insider.office.com/handbook) para enviar comentarios.

## <a name="integration-with-microsoft-defender-for-endpoint-and-microsoft-defender-for-office-365"></a>Integración con Microsoft Defender para punto de conexión y Microsoft Defender para Office 365

Application Guard para Office se integra con Microsoft Defender para punto de conexión para proporcionar supervisión y alertas sobre la actividad malintencionada que se produce en el entorno aislado.

[Documentos seguros en Microsoft E365 E5](/microsoft-365/security/office-365-security/safe-docs) es una característica que usa Microsoft Defender para punto de conexión para examinar los documentos abiertos en Application Guard para Office. Para obtener una capa adicional de protección, los usuarios no pueden salir de Application Guard para Office hasta que se hayan determinado los resultados del examen.

Microsoft Defender para punto de conexión es una plataforma de seguridad diseñada para ayudar a las redes empresariales a prevenir, detectar, investigar y responder a amenazas avanzadas. Para obtener más información sobre esta plataforma, consulte [Microsoft Defender para punto de conexión](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp). Para más información sobre la incorporación de dispositivos a esta plataforma, consulte [Incorporación de dispositivos al servicio Microsoft Defender para punto de conexión](/windows/security/threat-protection/microsoft-defender-atp/onboard-configure).

También puede configurar Microsoft Defender para Office 365 para que funcionen con Defender para punto de conexión. Para obtener más información, consulte [Integración de Defender para Office 365 con Microsoft Defender para punto de conexión](integrate-office-365-ti-with-mde.md).

## <a name="limitations-and-considerations"></a>Limitaciones y consideraciones

* Protección de aplicaciones para Office es un modo protegido que aísla documentos que no son de confianza para que no puedan acceder a recursos corporativos de confianza, una intranet, la identidad del usuario y archivos arbitrarios en el equipo. Como resultado, si un usuario intenta acceder a una característica que tiene una dependencia de dicho acceso, como insertar una imagen de un archivo local en el disco, el acceso produce un error y genera un mensaje similar al ejemplo siguiente. Para habilitar un documento que no es de confianza para acceder a recursos de confianza, los usuarios deben quitar la protección de Application Guard del documento.

  :::image type="content" source="../../media/ag09-confirm.png" alt-text="Cuadro de diálogo que indica el mensaje de seguridad y el estado de la característica" lightbox="../../media/ag09-confirm.png":::

  > [!NOTE]
  > Aconseje a los usuarios que solo quiten la protección si confían en el archivo y su origen o de dónde procede.

* Cuando un documento que no es de confianza se almacena en una ubicación de confianza, el documento hereda la confianza de la ubicación. Normalmente, el almacenamiento en la nube de una organización se identifica como una ubicación de confianza.

* El contenido activo en documentos como macros y controles ActiveX está deshabilitado en Protección de aplicaciones para Office. Los usuarios deben quitar la protección de Application Guard para habilitar el contenido activo.

* Archivos que no son de confianza de recursos compartidos de red o archivos compartidos desde OneDrive, OneDrive para la Empresa o SharePoint Online desde una organización diferente abierta como de solo lectura en Application Guard. Los usuarios pueden guardar una copia local de dichos archivos para seguir trabajando en el contenedor o quitar la protección para trabajar directamente con el archivo original.

* Los archivos protegidos por Information Rights Management (IRM) se bloquean de forma predeterminada. Si los usuarios quieren abrir estos archivos en la vista protegida, un administrador debe configurar las opciones de directiva para los tipos de archivo no admitidos para la organización.

* Las personalizaciones de las aplicaciones de Office en Application Guard para Office no se conservarán después de que un usuario cierre la sesión e inicie sesión de nuevo o después de reiniciar el dispositivo.

* Solo las herramientas de accesibilidad que usan el marco UIA pueden proporcionar una experiencia accesible para los archivos abiertos en Application Guard para Office.

* Se requiere conectividad de red para el primer inicio de Application Guard después de la instalación. La conectividad es necesaria para que Application Guard valide la licencia.

* En la sección de información del documento, la propiedad *Last Modified By* puede mostrar **WDAGUtilityAccount** como el usuario. WDAGUtilityAccount es el usuario anónimo configurado en Application Guard. La identidad del usuario de escritorio no se comparte dentro del contenedor de Application Guard.

## <a name="performance-optimizations-for-application-guard-for-office"></a>Optimizaciones de rendimiento para Application Guard para Office

En esta sección se proporciona información general sobre las optimizaciones de rendimiento que se usan en Application Guard para Office. Esta información puede ayudar a los administradores a diagnosticar informes de usuarios relacionados con el rendimiento de Office o el sistema general cuando application guard está habilitado.

Application Guard usa un contenedor virtualizado para aislar documentos que no son de confianza del sistema. El proceso de crear un contenedor y configurar el contenedor de Application Guard para abrir documentos de Office tiene una sobrecarga de rendimiento que podría afectar negativamente a la experiencia del usuario cuando los usuarios abren un documento que no es de confianza.

Para proporcionar a los usuarios la experiencia de apertura de archivos esperada, Application Guard usa lógica para crear previamente un contenedor cuando se cumple la siguiente heurística en un sistema: un usuario ha abierto un archivo en la vista protegida o en Application Guard en los últimos 28 días.

Cuando se cumpla esta heurística, Office creará previamente un contenedor de Application Guard para el usuario después de iniciar sesión en Windows. Aunque esta operación de creación previa está en curso, el sistema puede experimentar un rendimiento lento, pero el efecto se resolverá en cuanto se complete la operación.

> [!NOTE]
> Las sugerencias necesarias para que la heurística cree previamente el contenedor las generan las aplicaciones de Office a medida que un usuario las usa. Si un usuario instala Office en un nuevo sistema donde Application Guard está habilitado, Office no creará previamente el contenedor hasta la primera vez que un usuario abra un documento que no es de confianza en el sistema. El usuario observará que este primer archivo tarda más en abrirse en Application Guard.

## <a name="known-issues"></a>Problemas conocidos

* Al seleccionar vínculos web (`http` o `https`) no se abre el explorador.
* La configuración predeterminada para la directiva de protección de copiar y pegar es habilitar el acceso del Portapapeles solo al texto.
* La configuración predeterminada para la directiva de protección de tipos de archivo no admitidos es bloquear la apertura de tipos de archivo no compatibles que no son de confianza y que están cifrados o que tienen establecido Information Rights Management (IRM). Esto incluye archivos cifrados mediante etiquetas de confidencialidad de Microsoft Purview Information Protection.
* Los archivos CSV y HTML no se admiten en este momento.
* Application Guard para Office actualmente no funciona con volúmenes comprimidos NTFS. Si ve un error "ERROR_VIRTUAL_DISK_LIMITATION", intente descomprimir el volumen.
* Novedades a .NET podría provocar que los archivos no se abran en Application Guard. Como solución alternativa, los usuarios pueden reiniciar su dispositivo cuando se den cuenta de este error. Obtenga más información sobre el problema en [Recepción de un mensaje de error al intentar abrir Protección de aplicaciones de Windows Defender o Espacio aislado de Windows](https://support.microsoft.com/help/4575917/receiving-an-error-message-when-attempting-to-open-windows-defender-ap).
* Consulte [Preguntas más frecuentes: Protección de aplicaciones de Microsoft Defender para obtener información adicional.](/windows/security/threat-protection/microsoft-defender-application-guard/faq-md-app-guard)
