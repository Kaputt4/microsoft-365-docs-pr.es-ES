---
title: Configuración configurable para Escritorio administrado de Microsoft
description: Información sobre la configuración configurable con Microsoft Managed Desktop
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación, configuración, configuración configurable
ms.service: m365-md
author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: tiaraquan
manager: dougeby
ms.topic: article
ms.openlocfilehash: dcfa702511f5b1047b4d40b36e1466b6e08749fc
ms.sourcegitcommit: a6651b841f111ea2776cab88bf2c80f805fa8e09
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/13/2022
ms.locfileid: "62033266"
---
# <a name="configurable-settings---microsoft-managed-desktop"></a>Opciones configurables: Escritorio administrado de Microsoft

Microsoft Managed Desktop implementa la configuración y las directivas que se aplican a todos los dispositivos administrados por Microsoft Managed Desktop. Para obtener más información, consulta [Configuración del dispositivo](../service-description/device-policies.md).

La configuración configurable en Microsoft Managed Desktop ofrece a los administradores de TI una forma de personalizar e implementar configuraciones que son únicas para sus necesidades empresariales y de organización. Esta configuración se suma a las directivas y las opciones de configuración del dispositivo administradas por Microsoft Managed Desktop.  

Los cambios de configuración configurables se realizan en la nube y se aplican a los dispositivos de Escritorio administrado de Microsoft en grupos de implementación definidos. Este proceso es similar al modo en que Microsoft Managed Desktop administra los cambios en las directivas y las opciones de configuración del dispositivo definidas y administradas por el servicio. Al usar el mismo proceso que usa Microsoft Managed Desktop para implementar cambios, se sigue avanzando en la organización, con prácticas modernas de administración de TI.

## <a name="when-to-use-configurable-settings"></a>¿Cuándo usar la configuración configurable?

Hay varias veces para usar la configuración configurable. 

**Proceso de incorporación:** Microsoft Managed Desktop recomienda personalizar la configuración configurable cuando se incorpora al servicio de Escritorio administrado de Microsoft o al incorporar un gran número de dispositivos (20 o más). Las categorías de configuración se configuran en el portal de administración de Escritorio administrado de Microsoft. Después de incorporar y tener acceso al portal de administración, puede decidir qué categorías desea personalizar para su organización, realizar los cambios, realizar una implementación y, a continuación, implementar los cambios.

**Mantener la configuración:** revisa la configuración con regularidad y realiza las actualizaciones necesarias. Es posible que deba realizar cambios para admitir un cambio en su empresa.   

## <a name="setting-categories"></a>Establecer categorías

Estas son las categorías de configuración configurables que puede personalizar:
- [Imagen de fondo de escritorio:](config-setting-ref.md#desktop-background-picture) personalice la imagen de fondo de escritorio para dispositivos de Escritorio administrado de Microsoft. 
- [Páginas de inicio del explorador:](config-setting-ref.md#browser-start-pages) agregar páginas de inicio para usar con Microsoft Edge. Consulte Página de inicio del explorador
- [Enterprise de sitios de modo de](config-setting-ref.md#enterprise-mode-site-list-location) acceso: agregar sitios y su modo de compatibilidad. Los sitios de la lista se iniciarán en Internet Explorer. 
- [Sitios de confianza:](config-setting-ref.md#trusted-sites) agregue sitios de confianza y establezca zonas de seguridad para cada sitio. 
- [Excepciones de sitio proxy:](config-setting-ref.md#proxy) configure el número de dirección y el número de puerto del servidor proxy y agregue excepciones de sitio proxy.

Cada categoría de configuración se puede personalizar e implementar por sí sola. Sin embargo, puede implementar cambios en varias categorías de configuración al mismo tiempo, pero solo puede implementar un cambio a la vez en una categoría de configuración.

Por ejemplo:
- Puede implementar cambios en la imagen en segundo plano del escritorio y los sitios de confianza, cada uno como su propia implementación, al mismo tiempo. 
- No puede implementar dos implementaciones en las páginas de inicio del explorador al mismo tiempo. La implementación más reciente detendrá las implementaciones anteriores que aún están en curso.

## <a name="configurable-setting-process"></a>Proceso de configuración configurable

Microsoft Managed Desktop recomienda seguir un proceso similar al siguiente al usar la configuración configurable para su organización:

**Paso 1- Plan:** obtenga información sobre las opciones configurables y decida qué categorías de configuración desea configurar para su organización. Cree una escala de tiempo para cuando espera implementar cambios en cada grupo. Planee la comunicación con los usuarios que cumplan los procesos de administración de cambios internos. Por ejemplo, si va a agregar páginas de inicio del explorador, haga saber a los usuarios que tendrán un nuevo conjunto de páginas de inicio en su explorador después de la implementación.  

**Paso 2: Configurar e implementar la** fase: realice cambios en la configuración configurable en el portal de administración de Escritorio administrado de Microsoft. Realice una fase de los cambios para que estén listos para implementarlos. Recuerda que los usuarios sepan los cambios y cómo cambiarán la experiencia del dispositivo.   

Puede configurar y realizar cambios de fase en el portal de administración de Escritorio administrado de Microsoft. Para obtener más información, vea [Personalizar la configuración configurable](config-setting-ref.md). 

**Paso 3: Comunicar cambios** Comunicar información sobre los próximos cambios a los usuarios. Para cada implementación, complete la comunicación que forma parte de los procesos de administración de cambios. Debes comunicar claramente cualquier cambio que repercuta en el funcionamiento de un usuario o en lo que verán en sus dispositivos.

**Paso 4: Implementar cambios:** implementar los cambios, empezando por el grupo Prueba. El grupo De prueba le permite validar y solucionar problemas en un grupo con menos dispositivos, antes de implementar cambios en grupos de dispositivos más grandes. Si se encuentra con algún problema, puede revertir el cambio, actualizar la configuración y realizar una nueva implementación. Microsoft Managed Desktop recomienda seguir el enfoque estructurado e implementar en grupos en este orden: Test, First, Fast y, a continuación, Broad.   

Todas las opciones de configuración configurables se administran mediante el portal de administración de Escritorio administrado de Microsoft. Para obtener más información, vea [Deploy changes](config-setting-deploy.md). 

**Paso 5: realizar un seguimiento de los cambios:** realizar un seguimiento del progreso de los cambios en el estado de implementación. Para cada configuración, puede:
- **Realizar un seguimiento del** progreso: realizar un seguimiento del estado después de implementar el cambio. El estado cambiará a **In progress** y, a continuación, **Complete** o **Failed**. Si se produce un error en una implementación, se abre automáticamente una solicitud de soporte técnico para que Microsoft Managed Desktop Operations investigue el problema.  
- **Vea versión implementada:** cada cambio implementado tiene un número de versión.
- **Revertir cambios:** revertir un cambio detiene la implementación actual y revierte todos los grupos a los últimos cambios que se implementaron en todos los grupos. Va a volver al último valor de configuración conocido como bueno.
- **Validar los cambios:** una vez completada la implementación, valide que los cambios se aplicaron como esperaba.  

Si se ha fallado una implementación o no se puede revertir un cambio, [abra una](admin-support.md) solicitud de soporte técnico con operaciones de escritorio administrado de Microsoft. 

Para obtener más información, vea [Deploy and track configurable settings](config-setting-deploy.md).

## <a name="additional-resources"></a>Recursos adicionales
- [Referencia de parámetros configurables](config-setting-ref.md) 
- [Implementar parámetros configurables](config-setting-deploy.md) 
