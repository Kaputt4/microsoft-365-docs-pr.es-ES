---
title: Implementación de Windows 10 Enterprise para dispositivos existentes como actualización local
description: Proporciona instrucciones sobre cómo configurar e implementar una imagen de Windows 10 Enterprise con System Center Configuration Manager como una actualización inmediata.
keywords: Microsoft 365, Microsoft 365 Enterprise, documentación de Microsoft 365, Windows 10 Enterprise, implementación, actualización local, administrador de configuración, administrador de configuración de System Center
author: greg-lindsay
localization_priority: Normal
ms.collection: M365-modern-desktop
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 08/30/2018
ms.author: greglin
ms.openlocfilehash: f38d25423e57de56135d5232304e5192b7a2a209
ms.sourcegitcommit: 2aeafb631aaabc53eea0a8029711eb891e48d249
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2019
ms.locfileid: "37746476"
---
# <a name="step-2-deploy-windows-10-enterprise-for-existing-devices-as-an-in-place-upgrade"></a>Paso 2: implementar Windows 10 Enterprise para los dispositivos existentes como actualización local

*Este artículo se aplica a las versiones E3 y E5 de Microsoft 365 Enterprise*

![Fase 3: Windows 10 Enterprise](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

La ruta más sencilla para actualizar equipos que ejecutan Windows 7 o Windows 8,1 a Windows 10 es a través de una actualización inmediata. Puede usar una secuencia de tareas del administrador de configuración de System Center (Administrador de configuración) para automatizar el proceso por completo. 

Si ya tiene equipos que ejecutan Windows 7 o Windows 8,1, le recomendamos esta ruta si su organización está implementando Windows 10. Esto aprovecha el programa de instalación de Windows (Setup. exe) para realizar una actualización inmediata, que conserva automáticamente todos los datos, la configuración, las aplicaciones y los controladores de la versión del sistema operativo existente. Esto requiere menos esfuerzo de ti, ya que no es necesario disponer de una infraestructura de implementación compleja.

Siga estos pasos para configurar e implementar una imagen de Windows 10 Enterprise con Configuration Manager como una actualización inmediata.

## <a name="the-windows-10-deployment-with-system-center-configuration-manager-poster"></a>Implementación de Windows 10 con póster de System Center Configuration Manager

El póster de Configuration Manager es una página en el modo horizontal (17x11). Haga clic en la imagen siguiente para ver un PDF en el explorador. 

[![Implementación de Windows 10 con el póster de Configuration Manager](./media/windows10-deploy-inplaceupgrade/windows10-deployment-config-manager.png)](https://opdhsblobprod04.blob.core.windows.net/contents/d0d41f25ce48460387a79ace64acad6b/810b475c713ebb3ad65d13746940ef91?sv=2015-04-05&sr=b&sig=tKD38RgLAoOCAWJ5ppEbLevBAHk7KHtWrXldy2Jl6mY%3D&st=2019-10-24T22%3A16%3A08Z&se=2019-10-25T22%3A26%3A08Z&sp=r)

También puede descargar este póster en formato [PDF](https://github.com/MicrosoftDocs/windows-itpro-docs/raw/public/windows/deployment/media/Windows10DeploymentConfigManager.pdf) o [Visio](https://github.com/MicrosoftDocs/windows-itpro-docs/raw/public/windows/deployment/media/Windows10DeploymentConfigManager.vsdx) .

## <a name="part-1-verify-readiness-to-upgrade-windows"></a>Parte 1: comprobar la disponibilidad para actualizar Windows

En primer lugar, use la capacidad de actualización de Windows Analytics para proporcionar valiosas información y recomendaciones sobre los equipos, las aplicaciones y los controladores de su organización, sin costo adicional ni requisitos de infraestructura adicionales. Este nuevo servicio le guía a través de los proyectos de actualización de características y actualización mediante un flujo de trabajo basado en las prácticas recomendadas por Microsoft. Los datos de inventario actualizados le permiten equilibrar el coste y el riesgo en los proyectos de actualización.

Consulte [administrar las actualizaciones de Windows con preparación de actualización](https://docs.microsoft.com/windows/deployment/upgrade/manage-windows-upgrades-with-upgrade-readiness) para obtener más información, introducción, uso y solución de problemas de preparación para la actualización.

A continuación, siga la guía para usar System Center Configuration Manager (rama actual) para actualizar el sistema operativo Windows 7 o posterior a Windows 10. Al igual que con cualquier implementación de alto riesgo, se recomienda realizar una copia de seguridad de los datos de usuario antes de continuar. OneDrive: el almacenamiento en la nube está listo para usarse para los usuarios con licencia de Microsoft 365 y puede usarse para almacenar sus archivos de forma segura. Para obtener más información, consulte [Guía de inicio rápido de OneDrive](https://aka.ms/ODfBquickstartguide). Para obtener acceso a esta página, debe iniciar sesión como administrador de inquilino o administrador global en un inquilino de Office 365 o Microsoft 365.

Para obtener una lista de versiones de Configuration Manager y las versiones de cliente de Windows 10 correspondientes que son compatibles, consulte [compatibilidad con Windows 10 para System Center Configuration Manager](https://aka.ms/supportforwin10sccm).

**Para comprobar la disponibilidad para actualizar Windows**

Revise estos requisitos antes de iniciar la implementación de Windows 10:

- **Ediciones de Windows aptas para la actualización** : los dispositivos deben estar ejecutando ediciones de Windows 7 o Windows 8,1 que sean aptas para actualizar a Windows 10 Enterprise. Para obtener una lista de las ediciones compatibles, vea [rutas de actualización de Windows 10](https://aka.ms/win10upgradepaths). 
- **Dispositivos compatibles** : la mayoría de los equipos compatibles con Windows 8,1 serán compatibles con Windows 10. Es posible que tengas que instalar controladores actualizados en Windows 10 para que los dispositivos funcionen correctamente. Consulta [Especificaciones de Windows 10](https://aka.ms/windows10specifications) para obtener más información.
- **Preparación** de la implementación: Asegúrese de que tiene lo siguiente antes de comenzar a configurar la implementación:
    - Medios de instalación de Windows 10: los medios de instalación deben encontrarse en una unidad independiente, con el ISO ya montado. Puede obtener el ISO de las [descargas para suscriptores de MSDN](https://aka.ms/msdn-subscriber-downloads) o del [centro de servicios de licencias por volumen](https://aka.ms/mvlsc).
    - Copias de seguridad de datos de usuario: aunque los datos de usuario se migrarán a la actualización, el procedimiento recomendado es configurar un escenario de copia de seguridad. Por ejemplo, exporte todos los datos de usuario a una cuenta de OneDrive, una unidad flash USB con cifrado de BitLocker To Go o un servidor de archivos de red. Para obtener más información, vea [copia de seguridad o transferencia de datos en Windows](https://aka.ms/backuptransferdatawindows).
- **Preparación del entorno** : usará una estructura de servidor de Configuration Manager existente para prepararse para la implementación del sistema operativo. Además de la configuración básica, se deben realizar las siguientes configuraciones en el entorno de Configuration Manager:
    1. [Extienda el esquema de Active](https://aka.ms/extendadschema) Directory y [cree un contenedor de administración del sistema](https://aka.ms/createsysmancontainer).
    2. Habilitar detección de bosques de Active Directory y detección de sistema de Active Directory. Para obtener más información, vea [Configure Discovery Methods for System Center Configuration Manager](https://aka.ms/configurediscoverymethods).
    3. Cree límites de intervalo IP y grupo de límites para la asignación de contenido y sitios. Para obtener más información, consulte [definir límites de sitio y grupos de límites para System Center Configuration Manager](https://aka.ms/definesiteboundaries).
    4. Agregar y configurar el rol de punto de servicios de informes de Configuration Manager. Para obtener más información, consulte [configuración de informes en Configuration Manager](https://aka.ms/configurereporting).
    5. Cree una estructura de carpeta del sistema de archivos para los paquetes.
    6. Cree una estructura de carpeta de la consola de Configuration Manager para los paquetes.
    7. Instale las actualizaciones del administrador de configuración de System Center (rama actual) y los requisitos previos de Windows 10 adicionales.

## <a name="part-2-add-a-windows-10-os-image-using-configuration-manager"></a>Parte 2: agregar una imagen del sistema operativo Windows 10 con Configuration Manager
Ahora deberá crear un paquete de actualización del sistema operativo que contenga los medios de instalación de Windows 10 completos. En los pasos siguientes, usará Configuration Manager para crear un paquete de actualización para Windows 10 Enterprise x64.

**Para agregar una imagen del sistema operativo Windows 10 con Configuration Manager**

1. Mediante la consola del administrador de configuración, en el área de trabajo de la **biblioteca de software** , haga clic con el botón secundario en el nodo **paquetes de actualización del sistema operativo** y seleccione **Agregar paquete de actualización del sistema operativo**.
2. En la página **origen de datos** , especifique la ruta de acceso UNC al medio de Windows 10 Enterprise x64 y, a continuación, seleccione **siguiente**.
3. En la página **General** , especifique la **actualización de Windows 10 Enterprise x64**y, a continuación, seleccione **siguiente**. 
4. En la página de **Resumen** , seleccione **siguiente**y, a continuación, haga clic en **cerrar**. 
5. Haga clic con el botón secundario en el paquete de **actualización de Windows 10 Enterprise x64** y, a continuación, seleccione **distribuir contenido**. 
6. Elija su punto de distribución.

## <a name="part-3-configure-deployment-settings"></a>Parte 3: configurar las opciones de implementación
En este paso, configurará una secuencia de tareas de actualización que contiene la configuración para la actualización de Windows 10. A continuación, identificará los dispositivos que se van a actualizar y, a continuación, implementará la secuencia de tareas en esos dispositivos.

### <a name="create-a-task-sequence"></a>Creación de una secuencia de tareas
Para crear una secuencia de tareas de actualización, siga estos pasos:
  
1. En la consola de Configuration Manager, en el área de trabajo **biblioteca de software** , expanda **sistemas operativos**. 
2. Haga clic con el botón secundario en el nodo **secuencias de tareas** y seleccione **crear secuencia de tareas**.
3. En la página **crear una nueva secuencia de tareas** , seleccione **actualizar un sistema operativo desde el paquete de actualización**y, a continuación, seleccione **siguiente**.
4. En la página **información de secuencia de tareas** , especifique la actualización de **Windows 10 Enterprise x64**y, a continuación, seleccione **siguiente**.
5. En la página **actualizar el sistema operativo Windows** , seleccione **examinar** y elija el **paquete de actualización del sistema operativo para la actualización de Windows 10 Enterprise x64**, seleccione **Aceptar**y, a continuación, seleccione **siguiente**.
6. Continúe con las restantes páginas del asistente y, a continuación, seleccione **cerrar**.

### <a name="create-a-device-collection"></a>Crear una colección de dispositivos
Después de crear la secuencia de tareas de actualización, tendrá que crear una recopilación que contenga los dispositivos que va a actualizar.

> [!NOTE]
> Use la siguiente configuración para probar la implementación en un único dispositivo. Puede usar diferentes reglas de pertenencia para incluir grupos de dispositivos cuando esté listo. Para obtener más información, vea [Cómo crear colecciones en System Center Configuration Manager](https://aka.ms/sccm-create-collections).

1. En la consola de Configuration Manager, en el área de trabajo de **activos y cumplimiento** , haga clic con el botón secundario en **colecciones de dispositivos**y seleccione **crear colección de dispositivos**. 
2. En el Asistente para crear colección de dispositivos, en la página **General** , especifique la siguiente configuración y, a continuación, seleccione **siguiente**:
    - Nombre: actualización de Windows 10 Enterprise x64
    - Restricción de la colección: todos los sistemas
3. En la página **reglas de pertenencia** , seleccione **Agregar** > regla**directa** de regla para iniciar el Asistente para crear regla de pertenencia directa.
4. En la página **principal** del Asistente para crear regla de pertenencia directa, seleccione **siguiente**.
5. En la página **buscar recursos** , escriba la siguiente configuración y reemplace el texto del **valor** de marcador de posición por el nombre del dispositivo que va a actualizar: 
    - Clase de recursos: recurso del sistema
    - Nombre de atributo: nombre
    - Valor: *PC0003*
6. En la página **seleccionar recursos** , seleccione su dispositivo y, a **continuación**, seleccione siguiente.
7. Complete el Asistente para crear regla de pertenencia directa y el Asistente para crear colección de dispositivos.  
8. Revise la colección de actualizaciones de Windows 10 Enterprise x64. No continúe hasta que vea los equipos que agregó en la colección.

### <a name="create-an-operating-system-deployment"></a>Crear una implementación de sistema operativo
Siga estos pasos para crear una implementación de la secuencia de tareas.

1. En la consola de Configuration Manager, en el área de trabajo **biblioteca de software** , haga clic con el botón secundario en la secuencia de tareas que creó en un paso anterior y, después, seleccione **implementar**.
2. En la página **General** , seleccione la colección de **actualizaciones de Windows 10 Enterprise x64** y, a continuación, seleccione **siguiente**.
3. En la página **contenido** , seleccione **siguiente**.
4. En la página Configuración de la **implementación** , seleccione las siguientes opciones y, a continuación, seleccione **siguiente**:

    > [!NOTE]
    > Para esta implementación de prueba, deberá establecer el propósito en **disponible**, lo que requiere la intervención del usuario para iniciar la implementación. En un entorno de producción, es posible que quiera automatizar la implementación con el propósito necesario, que implica la configuración de opciones adicionales, como la programación cuando se ejecuta la implementación. 

    - Acción: instalar
    - Propósito: disponible

5. En la página **programación** , acepte la configuración predeterminada y, a continuación, seleccione **siguiente**.
6. En la página **experiencia del usuario** , acepte la configuración predeterminada y, a continuación, seleccione **siguiente**.
7. En la página **alertas** , acepte la configuración predeterminada y, a continuación, seleccione **siguiente**.
8. En la página de **Resumen** , seleccione **siguiente**y, a continuación, haga clic en **cerrar**.

## <a name="part-4-start-the-windows-10-upgrade-task-sequence"></a>Parte 4: iniciar la secuencia de tareas de actualización de Windows 10
Siga estos pasos para iniciar la secuencia de tareas de actualización de Windows 10 en el dispositivo que va a actualizar.
 
1. Inicie sesión en el equipo con Windows e inicie el **centro de software**.
2. Seleccione la secuencia de tareas que ha creado en el paso anterior y, a continuación, seleccione **instalar**.
3. Cuando comienza la secuencia de tareas, automáticamente inicia el proceso de actualización en el lugar invocando el programa de instalación de Windows (Setup. exe) con los parámetros de línea de comandos necesarios para realizar una actualización automática, que conserva todos los datos, la configuración, las aplicaciones y factores.
4. Una vez completada correctamente la secuencia de tareas, el equipo se actualizará completamente a Windows 10.

Si experimenta problemas al usar Windows 10 en un entorno empresarial, puede consultar [las principales soluciones de soporte técnico de Microsoft para los problemas más comunes](https://docs.microsoft.com/windows/client-management/windows-10-support-solutions). Estos recursos incluyen artículos de Knowledge base, actualizaciones y artículos de bibliotecas.

Durante la implementación de actualizaciones en toda la organización, use la capacidad de actualización de cumplimiento de Windows Analytics para proporcionar una vista holística del cumplimiento de la actualización del sistema operativo, el progreso de la implementación de la actualización y la solución de errores para los dispositivos Windows 10. Este nuevo servicio usa datos de diagnóstico que incluyen el progreso de la instalación, la configuración de Windows Update y otra información para proporcionar este tipo de información sin costo adicional ni requisitos de infraestructura adicionales. Tanto si se usa con Windows Update para empresas como con otras herramientas de administración, puede tener la certeza de que los dispositivos se han actualizado correctamente.

Consulte [supervisar actualizaciones de Windows y antivirus de Windows Defender con el cumplimiento](https://docs.microsoft.com/windows/deployment/update/update-compliance-monitor) de la actualización para obtener más información, empezar a usar y usar el cumplimiento de actualizaciones.

Como control provisional, puede consultar los [criterios de salida](windows10-exit-criteria.md#crit-windows10-step2) correspondientes a este paso.

## <a name="next-step"></a>Siguiente paso

|||
|:-------|:-----|
|![Paso 3](./media/stepnumbers/Step3.png)| [Implementar Windows 10 Enterprise para dispositivos nuevos con Windows AutoPilot](windows10-deploy-autopilot.md) |
