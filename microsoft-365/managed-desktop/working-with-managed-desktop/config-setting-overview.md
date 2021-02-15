---
title: Opciones configurables para escritorio administrado de Microsoft
description: Información sobre las opciones configurables con escritorio administrado de Microsoft
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación, configuración, configuración configurable
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: bf8672ee6c3332ea6f8522f5086d72e58d1b9048
ms.sourcegitcommit: bdf65d48b20f0f428162c39ee997accfa84f4e5d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/20/2020
ms.locfileid: "49371495"
---
# <a name="configurable-settings---microsoft-managed-desktop"></a>Opciones configurables: Escritorio administrado de Microsoft

Escritorio administrado de Microsoft implementa la configuración y las directivas que se aplican a todos los dispositivos administrados por Escritorio administrado de Microsoft. Para obtener más información, consulta [Configuración del dispositivo.](../service-description/device-policies.md)

Las opciones configurables en escritorio administrado de Microsoft permiten a los administradores de TI personalizar e implementar configuraciones que son exclusivas de sus necesidades empresariales y de la organización. Esta configuración se suma a las directivas y las opciones de configuración de dispositivo que administra el Escritorio administrado de Microsoft.  

Los cambios de configuración configurables se realizan en la nube y se aplican a los dispositivos de Escritorio administrado de Microsoft en grupos de implementación definidos. Este proceso es similar al modo en que el Escritorio administrado de Microsoft administra los cambios en las directivas y las opciones de configuración de dispositivo definidas y administradas por el servicio. Al usar el mismo proceso que usa escritorio administrado de Microsoft para implementar cambios, sigue avanzando en la organización, mediante prácticas modernas de administración de TI.

## <a name="when-to-use-configurable-settings"></a>¿Cuándo usar opciones configurables?

Hay varias veces para usar opciones configurables. 

**Proceso de** incorporación: El Escritorio administrado de Microsoft recomienda personalizar la configuración configurable cuando se incorpora al servicio de Escritorio administrado de Microsoft o cuando se incorpora un gran número de dispositivos (20 o más). Las categorías de configuración se configuran en el portal de administración de Escritorio administrado de Microsoft. Después de incorporarse y tener acceso al portal de administración, puede decidir qué categorías de configuración desea personalizar para su organización, realizar los cambios, realizar una implementación por fases y, a continuación, implementar los cambios.

**Mantener la configuración:** revisa la configuración periódicamente y realiza las actualizaciones necesarias. Es posible que deba realizar cambios para admitir un cambio en su empresa.   

## <a name="setting-categories"></a>Establecer categorías

Estas son las categorías de configuración configurables que puede personalizar:
- [Imagen de fondo de escritorio:](config-setting-ref.md#desktop-background-picture) personalizar la imagen de fondo de escritorio para dispositivos de Escritorio administrado de Microsoft. 
- [Páginas de inicio del explorador:](config-setting-ref.md#browser-start-pages) agregue páginas de inicio para usarlas con Microsoft Edge. Ver página de inicio del explorador
- [Lista de sitios del modo de empresa:](config-setting-ref.md#enterprise-mode-site-list-location) agregar sitios y su modo de compatibilidad. Los sitios de la lista se iniciarán en Internet Explorer. 
- [Sitios de confianza:](config-setting-ref.md#trusted-sites) agregue sitios de confianza y establezca zonas de seguridad para cada sitio. 
- [Excepciones de sitio proxy:](config-setting-ref.md#proxy) configure el número de dirección y el número de puerto del servidor proxy, y agregue excepciones de sitio proxy.

Cada categoría de configuración se puede personalizar e implementar por sí misma. Puede implementar cambios en varias categorías de configuración al mismo tiempo, pero solo puede implementar un cambio cada vez en una categoría de configuración.

Por ejemplo:
- Puede implementar los cambios en la imagen de fondo del escritorio y los sitios de confianza, cada uno como su propia implementación, al mismo tiempo. 
- No puede implementar dos implementaciones en las páginas de inicio del explorador al mismo tiempo. La implementación más reciente detendrá las implementaciones anteriores que aún están en curso.

## <a name="configurable-setting-process"></a>Proceso de configuración configurable

El Escritorio administrado de Microsoft recomienda seguir un proceso similar al siguiente al usar opciones configurables para su organización:

**Paso 1: Planear:** obtenga información sobre las opciones configurables y decida qué categorías de configuración desea configurar para su organización. Crea una escala de tiempo para cuando esperas implementar cambios en cada grupo. Planee la comunicación con los usuarios que cumpla los procesos internos de administración de cambios. Por ejemplo, si va a agregar páginas de inicio del explorador, haga saber a los usuarios que tendrán un nuevo conjunto de páginas de inicio en el explorador después de la implementación.  

**Paso 2: configurar y realizar una implementación por fases:** realizar cambios en las opciones configurables en el portal de administración de Escritorio administrado de Microsoft. Espárense los cambios para que estén listos para implementarse. Recuerda que se debe dar a los usuarios información sobre los cambios y cómo cambiarán la experiencia del dispositivo.   

Los cambios se configuran y se configuran por fases en el portal de administración de Escritorio administrado de Microsoft. Para obtener más información, vea [Personalizar la configuración configurable.](config-setting-ref.md) 

**Paso 3: Comunicar los cambios** Comunique información sobre los próximos cambios a los usuarios. Para cada implementación, complete la comunicación que forma parte de los procesos de administración de cambios. Debes comunicar claramente cualquier cambio que repercuta en el funcionamiento de un usuario o en lo que verán en sus dispositivos.

**Paso 4: Implementar cambios:** implemente los cambios, empezando por el grupo De prueba. El grupo De prueba te permite validar y solucionar problemas en un grupo con menos dispositivos, antes de implementar cambios en grupos de dispositivos más grandes. Si se encuentra con algún problema, puede revertir el cambio, actualizar la configuración y realizar una nueva implementación. Escritorio administrado de Microsoft recomienda seguir el enfoque estructurado e implementar en grupos en este orden: Prueba, Primero, Rápido y, a continuación, General.   

Todas las opciones configurables se administran mediante el portal de administración de Escritorio administrado de Microsoft. Para obtener más información, vea [Implementar cambios.](config-setting-deploy.md) 

**Paso 5: realizar un seguimiento de los cambios:** realizar un seguimiento del progreso de los cambios en el estado de implementación. Para cada configuración, puede:
- **Seguimiento del progreso:** realiza un seguimiento del estado después de implementar el cambio. El estado cambiará a **En curso y,** a continuación, **completado** o **con error**. Si se produce un error en una implementación, se abre automáticamente una solicitud de soporte técnico para que las operaciones de escritorio administrado de Microsoft investiguen el problema.  
- **Vea la versión implementada:** cada cambio implementado tiene un número de versión.
- **Revertir cambios:** revertir un cambio detiene la implementación actual y revierte todos los grupos a los últimos cambios que se implementaron en todos los grupos. Va a volver al último valor de configuración válido conocido.
- **Validar los cambios:** una vez completada la implementación, valide que los cambios se aplicaron como esperaba.  

Si se ha fallado una implementación o no puede revertir un cambio, [abra](admin-support.md) una solicitud de soporte técnico con Operaciones de escritorio administrado de Microsoft. 

Para obtener más información, vea [Implementar y realizar un seguimiento de las opciones configurables.](config-setting-deploy.md)

## <a name="additional-resources"></a>Recursos adicionales
- [Referencia de parámetros configurables](config-setting-ref.md) 
- [Implementar parámetros configurables](config-setting-deploy.md) 
