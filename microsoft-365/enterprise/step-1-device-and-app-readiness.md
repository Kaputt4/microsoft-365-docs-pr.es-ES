---
title: 'Paso 1: Preparación de dispositivos y aplicaciones'
ms.author: jogruszc
author: JGruszczyk
manager: jemed
ms.date: 09/14/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Obtenga información sobre cómo evaluar la preparación de los dispositivos y las aplicaciones en el entorno.
ms.openlocfilehash: 8c5f40f4f65c95aca628b64433676d473856e1c8
ms.sourcegitcommit: 3b2d3e2b38c4860db977e73dda119a465c669fa4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "33400134"
---
# <a name="step-1-device-and-app-readiness"></a>Paso 1: Preparación de dispositivos y aplicaciones

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-1.png)

<table>
<thead>
<td><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-3.png" alt="Step 1" height="130" width="130" /></td>
<td><p><strong>Paso 1: Preparación de dispositivos y aplicaciones</strong></p>
<p>Inicie el proyecto de implementación de escritorio con un inventario de los dispositivos y las aplicaciones, priorice lo que debe avanzar, pruebe los dispositivos y las aplicaciones prioritarios, y corrija los aspectos necesarios para prepararse para la implementación.</p></td>
<td><a href="https://aka.ms/ddev1" target="_blank"><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-14.png" alt="Step 1" height="120" width="213" /></a></td>
</thead>
</table>

>[!NOTE]
>La preparación de los dispositivos y las aplicaciones es el primer paso del ciclo de proceso de implementación recomendado, que abarca los aspectos integrales de la compatibilidad del hardware y las aplicaciones. Para ver el proceso de implementación de escritorio completo, visite el [Centro de implementación de escritorio](https://aka.ms/HowToShift).
>

En el pasado, el gran obstáculo para actualizar los equipos de escritorio del usuario era la compatibilidad de las aplicaciones y el hardware. Al planear el cambio a Windows 10 y Office 365 ProPlus, la buena noticia es que casi cualquier aplicación escrita en los últimos 10 años se ejecutará en Windows 10, y que los complementos COM y macros de VBA que su organización usaba en versiones de Office anteriores a Office 2010 seguirán funcionando en las versiones más recientes de Office, sin cambios.

Dicho esto, en función del tamaño y la antigüedad de la organización, es probable que la comprobación de la compatibilidad de las aplicaciones y el hardware siga siendo un paso inicial fundamental en el proceso de implementación en ocho fases recomendado.

Este artículo le guiará por esa primera fase (Preparación de dispositivos y aplicaciones) con las herramientas de evaluación de preparación de Microsoft, incluyendo la nueva herramienta Upgrade Readiness de Windows Analytics, una solución inteligente basada en la nube disponible con la licencia de Windows.

## <a name="windows-10-compatibility-scan"></a>Análisis de compatibilidad de Windows 10

Antes de implementar Windows 10 Microsoft recomienda comprobar la preparación de los dispositivos existentes que ejecutan Windows 7 o 8/8.1. Los medios de instalación de Windows 10 son compatibles con un modificador de línea de comandos para que setup.exe ejecute la actualización, pero solo compruebe compatibilidad, sin llegar a realizar la actualización. ScanOnly se puede ejecutar como un archivo por lotes secuenciados o integrado en una secuencia de tareas de System Center Configuration Manager, incluyendo la capacidad de ejecutar la ScanOnly directamente desde la red para que el medio de instalación de Windows 10 no se transmita al dispositivo local. Cuando ScanOnly acabe se devuelven los resultados a través de códigos de retorno de los archivos de registro generados por Setup.EXE.   

Una línea de comandos de ejemplo de ScanOnly que complete la detección de compatibilidad silenciosamente sería similar a la siguiente:

    Setup.EXE /Auto Upgrade /Quiet /NoReboot /Compat ScanOnly

Para obtener más información acerca de ScanOnly y otros modificadores de comando de configuración de Windows revise las [Opciones de configuración de línea de comandos de Windows](https://aka.ms/setupswitches).

## <a name="recommended-tool-windows-analytics-upgrade-readiness"></a>Herramienta recomendada: Upgrade Readiness de Windows Analytics

Upgrade Readiness de Windows Analytics ofrece numerosas ventajas acerca de los sistemas de administración de escritorio tradicionales y es la herramienta recomendada. No tiene agente y le guiará por los pasos que deben realizarse haciendo uso de la información de compatibilidad de aplicaciones y controladores recopilada a través de la actualización de millones de equipos de clientes. Esta información le proporciona una evaluación detallada, que identifica los problemas de compatibilidad que podrían bloquear la actualización, con vínculos a las correcciones sugeridas que conoce Microsoft.

Para configurar Upgrade Readiness de Windows Analytics primero debe configurar una suscripción de Azure e incluir un área de trabajo de Azure Log Analytics para ello. Una vez que tenga se esté ejecutando el servicio de Upgrade Readiness de Windows Analytics, podrá inscribir dispositivo con Windows 7 SP1 o una versión posterior conectado a Internet mediante la configuración de Directiva de grupo, así de simple. No hay ningún agente que tenga que implementar y el flujo de trabajo visual de Upgrade Readiness de Windows Analytics le guiará desde la implementación de prueba a la de producción. Si lo desea, puede exportar datos de Upgrade Readiness de Windows Analytics a herramientas de implementación de software como System Center Configuration Manager, a equipos de destino directamente y crear colecciones a medida que estén listas para su implementación.

Si en la actualidad no ha configurado Windows Analytics para su entorno o quiere suscribirse a una prueba, vaya a la [página de Windows Analytics](http://www.aka.ms/windowsanalytics) y empiece a trabajar.

## <a name="device-and-app-readiness-process"></a>Proceso de preparación de dispositivos y aplicaciones

La preparación de dispositivos y aplicaciones consta de cuatro pasos: 1. Inventario, 2. Priorizar, 3. Probar, 4. Corrección. Veamos cada uno por orden.

### <a name="1-inventory"></a>1\. Inventario

En Upgrade Readiness de Windows Analytics se usa un proceso sin agente para realizar el inventario de los equipos, aplicaciones y complementos de Office en el equipo de escritorio.

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-3.png)

También se proporcionan informes acerca de los sitios de Internet muy visitados, las aplicaciones y las ubicaciones de Intranet para ayudar con las pruebas de compatibilidad más adelante.

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-4.png)

### <a name="2-prioritize"></a>2\. Priorizar

Con el inventario realizado, Upgrade Readiness de Windows Analytics le ayuda a identificar y priorizar las aplicaciones y el hardware más común que se usa en la organización, y en qué centrarse para desbloquear tantos equipos como sea posible para la implementación.

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-5.png)

También proporciona instrucciones para ayudarle a evaluar qué actualizaciones son necesarias para resolver problemas durante el paso siguiente: las pruebas.

### <a name="3-testing"></a>3\. Probar

Descubrirá que la mayoría de los controladores, aplicaciones y complementos inventariados funcionan tal cual. Para aquellos elementos que Upgrade Readiness de Windows Analytics indica que tienen problemas, se proporciona información conocida como dónde encontrar actualizaciones de versión para resolver problemas de compatibilidad. En lugar de dedicar tiempo y recursos para resolver problemas complejos en aplicaciones que no son críticas que están implementadas de forma dispersa y en dispositivos antiguos, puede en su lugar trabajar con los usuarios para retirar y reemplazar estos elementos.

También puede usar Upgrade Readiness de Windows Analytics para evaluar los problemas de compatibilidad basados en el explorador, para identificar los sitios y las aplicaciones web a las que acceden los usuarios en los que todavía se usan controles ActiveX, objetos auxiliares del explorador, VBScript u otras tecnologías heredadas que no son compatibles con el explorador Microsoft Edge. Los usuarios tendrán que seguir usando Internet Explorer 11 para estos sitios y los puede agregar a la [lista de sitios del modo de empresa](https://docs.microsoft.com/es-ES/microsoft-edge/deploy/emie-to-improve-compatibility), con Enterprise Mode Site List Manager.

Además, para facilitar el cambio a Office 365 ProPlus, es posible que quiera usar [Readiness Toolkit para Office](https://docs.microsoft.com/es-ES/deployoffice/use-the-readiness-toolkit-to-assess-application-compatibility-for-office-365-pro) a fin de probar la compatibilidad de los complementos y las macros de Microsoft Visual Basic para Aplicaciones (VBA).

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-6.png)

### <a name="4-remediation"></a>4\. Corrección

La fase final de la preparación de las aplicaciones y los dispositivos es la "corrección". Aquí le interesará recopilar los paquetes de software o controladores necesarios; los usará para sustituir o actualizar las versiones anteriores como parte del proceso de implementación.

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-7.png)

Mientras recorre la lista para corregir los problemas, verá que aumenta el número de equipos "Listos para la implementación". Esto significa que las aplicaciones y los controladores en los equipos se indican como compatibles con la versión de Windows 10 seleccionada como destino para la implementación.

### <a name="configuration-manager-software-inventory-for-application-prioritization"></a>Inventario de software de Configuration Manager para la priorización de aplicaciones

El inventario de software de Configuration Manager es una alternativa a usar soluciones de análisis basadas en la nube para la preparación de aplicaciones y dispositivos. Puede usar cuentas de instalación y explorar equipos específicos para ayudar a clasificar la validación y pruebas de compatibilidad y establecer los paquetes de aplicaciones como compatibles con Windows 10 a través de la configuración del paquete. Aunque esta opción no ofrece la capacidad para comparar la información de compatibilidad conocida con servicios de análisis de Microsoft, puede ser una solución eficaz para un conjunto más pequeño de aplicaciones prioritarias para pruebas manuales. 

Para obtener más información, vea [Introducción al inventario de software en System Center Configuration Manager](https://docs.microsoft.com/es-ES/sccm/core/clients/manage/inventory/introduction-to-software-inventory) y cómo establecer requisitos de plataforma en paquetes de aplicación en [Paquetes y programas en System Center Configuration Manager](https://docs.microsoft.com/es-ES/sccm/apps/deploy-use/packages-and-programs).


## <a name="desktop-app-assure"></a>Desktop App Assure

Otra herramienta para ayudar con la compatibilidad de aplicaciones de Windows 10 y Office 365 ProPlus es el programa [Desktop App Assure](https://aka.ms/desktopappassure) disponible a través del Centro de FastTrack. Mediante Desktop App Assure en caso de problemas de aplicación válida un ingeniero de Microsoft colaborará con usted sin coste adicional para ayudarle a solucionar la compatibilidad de aplicaciones.

## <a name="continued-use-of-diagnostic-data-tools"></a>Uso continuado de herramientas de datos de diagnóstico

Upgrade Readiness de Windows Analytics no es solo una herramienta para ayudar en el cambio a Windows 10 y Office 365 ProPlus. Una vez que haya equipos de escritorio que se ejecutan en Windows 10 y Office 365, se puede usar para ayudar a mantener la implementación y administrar las actualizaciones de características semestrales para mantenerse actualizado.

## <a name="next-step"></a>Siguiente paso 

## <a name="step-2-directory-and-network-readinesshttpsakamsmdd2"></a>[Paso 2: Preparación de los directorios y la red](https://aka.ms/mdd2)