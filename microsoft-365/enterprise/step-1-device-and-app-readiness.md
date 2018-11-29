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
ms.openlocfilehash: a9fa85ea37de06399aa2264b09c61e588edc2107
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871807"
---
# <a name="step-1-device-and-app-readiness"></a>Paso 1: Preparación de dispositivos y aplicaciones

Inicie el proyecto de implementación de escritorio con un inventario de los dispositivos y las aplicaciones, priorice lo que quiera migrar, pruebe los dispositivos y las aplicaciones prioritarios, y corrija los aspectos necesarios para prepararse para la implementación.

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-1.png)

<table>
<thead>
<td><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-3.png" alt="Step 1" height="130" width="130" /></td>
<td><p><strong>Paso 1: Preparación de dispositivos y aplicaciones</strong></p>
<p>Inicie el proyecto de implementación de escritorio con un inventario de los dispositivos y las aplicaciones, priorice lo que quiera migrar, pruebe los dispositivos y las aplicaciones prioritarios, y corrija los aspectos necesarios para prepararse para la implementación.</p></td>
<td><a href="https://aka.ms/ddev1" target="_blank"><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-14.png" alt="Step 1" height="120" width="213" /></a></td>
</thead>
</table>

>[!NOTE]
>La preparación de los dispositivos y las aplicaciones es el primer paso del ciclo de proceso de implementación recomendado, que abarca los aspectos integrales de la compatibilidad del hardware y las aplicaciones. Para ver el proceso de implementación de escritorio completo, visite el [Centro de implementación de escritorios modernos](https://aka.ms/HowToShift).
>

En el pasado, el gran obstáculo para actualizar los equipos de escritorio del usuario era la compatibilidad de las aplicaciones y el hardware. Al planear el cambio a Windows 10 y Office 365 ProPlus, la buena noticia es que casi cualquier aplicación escrita en los últimos 10 años se ejecutará en Windows 10, y que los complementos COM y macros de VBA que su organización usaba en versiones de Office anteriores a Office 2010 seguirán funcionando en las versiones más recientes de Office, sin cambios.

Dicho esto, en función del tamaño y la antigüedad de la organización, es probable que la comprobación de la compatibilidad de las aplicaciones y el hardware siga siendo un paso inicial fundamental en el proceso de implementación en ocho fases recomendado.

Este artículo le guiará por esa primera fase —Preparación de dispositivos y aplicaciones— con la nueva herramienta Upgrade Readiness de Windows Analytics, una solución inteligente basada en la nube disponible con la licencia de Windows.

Si en la actualidad no ha configurado Windows Analytics para su entorno o quiere suscribirse a una prueba, vaya a la [página de Windows Analytics](http://www.aka.ms/windowsanalytics) y empiece a trabajar.

## <a name="recommended-tool-windows-analytics-upgrade-readiness"></a>Herramienta recomendada: Upgrade Readiness de Windows Analytics

Upgrade Readiness de Windows Analytics ofrece numerosas ventajas sobre los sistemas de administración de escritorio tradicionales y es la herramienta recomendada. No tiene agente; le guiará por lo que tiene que realizar, y usa la información de compatibilidad de aplicaciones y controladores que ha obtenido a través de la actualización de millones de equipos cliente para proporcionar una evaluación detallada, en la que se identifican los problemas de compatibilidad que podrían bloquear la actualización, con vínculos a correcciones sugeridas conocidas para Microsoft.

Para configurar Upgrade Readiness de Windows Analytics, primero debe configurar una suscripción de Azure, en la que tiene que incluir un área de trabajo de Azure Log Analytics. Una vez en ejecución el servicio Upgrade Readiness de Windows Analytics, puede inscribir cualquier dispositivo Windows 7 SP1 o versiones posteriores conectado a Internet a través de la configuración de directiva de grupo. Es muy sencillo. No hay que implementar ningún agente y el flujo de trabajo visual de Upgrade Readiness de Windows Analytics le guiará desde la implementación piloto a la de producción. Si quiere, puede exportar datos desde Upgrade Readiness de Windows Analytics a herramientas de implementación de software como System Center Configuration Manager, para seleccionar equipos como destino de forma directa y crear colecciones a medida que estén listas para la implementación.

## <a name="device-and-app-readiness-process"></a>Proceso de preparación de dispositivos y aplicaciones

Preparación de dispositivos y aplicaciones consta de cuatro pasos: 1. Inventario, 2. Priorizar, 3. Pruebas 4. Corregir. Veamos cada uno de ellos por separado.

### <a name="1-inventory"></a>1\. Inventario

En Upgrade Readiness de Windows Analytics se usa un proceso sin agente para realizar el inventario de los equipos, aplicaciones y complementos de Office en el equipo de escritorio.

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-3.png)

También se proporcionan informes sobre los sitios de Internet muy visitados, las aplicaciones y las ubicaciones de Intranet para ayudar con las pruebas de compatibilidad más adelante.

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-4.png)

### <a name="2-prioritize"></a>2\. Priorizar

Con el inventario realizado, Upgrade Readiness de Windows Analytics le ayuda a identificar y priorizar las aplicaciones y el hardware más común que se usa en la organización, y en qué centrarse para desbloquear tantos equipos como sea posible para la implementación,

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-5.png)

además de proporcionar instrucciones para ayudarle a evaluar qué actualizaciones son necesarias para resolver problemas durante el paso siguiente: las pruebas.

### <a name="3-testing"></a>3\. Pruebas

Comprobará que la mayoría de los controladores, aplicaciones y complementos del inventario funcionan tal cual. Para los elementos que Upgrade Readiness de Windows Analytics considera que tienen problemas, proporciona información conocida, incluido dónde encontrar las actualizaciones de la versión para resolver los problemas de compatibilidad. En lugar de dedicar tiempo y recursos a resolver problemas complejos en aplicaciones y dispositivos antiguos que no son críticos y apenas se implementan, puede trabajar con los usuarios para retirar y reemplazar esos elementos.

También puede usar Upgrade Readiness de Windows Analytics para evaluar los problemas de compatibilidad basados en el explorador, para identificar los sitios y las aplicaciones web a las que acceden los usuarios en los que todavía se usan controles ActiveX, objetos auxiliares del explorador, VBScript u otras tecnologías heredadas que no son compatibles con el explorador Microsoft Edge. Los usuarios tendrán que seguir usando Internet Explorer 11 para estos sitios y los puede agregar a la [lista de sitios del modo de empresa](https://docs.microsoft.com/es-ES/microsoft-edge/deploy/emie-to-improve-compatibility), con Enterprise Mode Site List Manager.

Además, para facilitar el cambio a Office 365 ProPlus, es posible que quiera usar [Readiness Toolkit para Office](https://docs.microsoft.com/es-ES/deployoffice/use-the-readiness-toolkit-to-assess-application-compatibility-for-office-365-pro) a fin de probar la compatibilidad de los complementos y las macros de Microsoft Visual Basic para Aplicaciones (VBA).

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-6.png)

### <a name="4-remediation"></a>4\. Corrección

La fase final de la preparación de las aplicaciones y los dispositivos es la "corrección". Aquí le interesará recopilar los paquetes de software o controladores necesarios; los usará para sustituir o actualizar las versiones anteriores como parte del proceso de implementación.

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-7.png)

Mientras recorre la lista para corregir los problemas, verá que aumenta el número de equipos "Listos para la implementación". Esto significa que las aplicaciones y los controladores en los equipos se indican como compatibles con la versión de Windows 10 seleccionada como destino para la implementación.

## <a name="continued-use-of-telemetry-tools"></a>Uso continuado de herramientas de telemetría

Upgrade Readiness de Windows Analytics no es solo una herramienta para ayudar en el cambio a Windows 10 y Office 365 ProPlus. Una vez que haya equipos de escritorio que se ejecutan en Windows 10 y Office 365, se puede usar para ayudar a mantener la implementación y administrar las actualizaciones de características semestrales para mantenerse actualizado.

## <a name="next-step"></a>Siguiente paso 

## <a name="step-2-directory-and-network-readinesshttpsakamsmdd2"></a>[Paso 2: Preparación de los directorios y la red](https://aka.ms/mdd2)