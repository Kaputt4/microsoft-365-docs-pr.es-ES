---
title: Opciones conFigurables para escritorio administrado de Microsoft
description: Información sobre las opciones configurables con el escritorio administrado de Microsoft
keywords: Escritorio administrado por Microsoft, Microsoft 365, servicio, documentación, configuración, configuración configurable
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 2/14/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 0d30e92eb9747079a7edc5a8fd198298508f342e
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32278222"
---
# <a name="configurable-settings---microsoft-managed-desktop"></a>Opciones conFigurables-escritorio administrado por Microsoft

Microsoft manAged Desktop implementa la configuración y las directivas que se aplican a todos los dispositivos administrados por el escritorio administrado por Microsoft. Para obtener más información, consulte [configuración de dispositivos](../service-description/device-policies.md).

Las opciones conFigurables del escritorio administrado de Microsoft proporcionan a los administradores de ti una forma de personalizar e implementar la configuración que es única para su organización y las necesidades empresariales. Estas opciones de configuración se agregan a la configuración de dispositivos y a las directivas administradas por el escritorio administrado por Microsoft.  

Los cambios de configuración conFigurables se realizan en la nube y se aplican a los dispositivos de escritorio administrados por Microsoft en los grupos de implementación definidos. Este proceso es similar al modo en que Microsoft manAged Desktop administra los cambios en las directivas y la configuración de configuruation de dispositivos definidas y administradas por el servicio. Si usa el mismo proceso que Microsoft manAged Desktop usa para implementar cambios, sigue adelante con las prácticas modernas de administración de TI para avanzar la organización.

## <a name="when-to-use-configurable-settings"></a>¿Cuándo se deben usar las opciones configurables?

Hay algunas veces en las que puede usar opciones configurables. 

**Proceso de incorporación** : Microsoft Managed Desktop recomienda personalizar las opciones configurables al incorporarse al servicio de escritorio administrado de Microsoft o al incorporar un gran número de dispositivos (20 o más). Las categorías de configuración se configuran en el portal de administración de escritorio administrado de Microsoft. Una vez que haya incorporado y tenga acceso al portal de administración, puede decidir qué categorías de configuración desea personalizar para su organización, realizar los cambios, ensayar una implementación y, a continuación, implementar los cambios.

**Mantener configuración** : revisa la configuración con regularidad y realiza las actualizaciones necesarias. Es posible que deba realizar cambios para admitir un cambio en su empresa.   

## <a name="setting-categories"></a>Establecer categorías

Estas son las categorías de configuración configurables que puede personalizar:
- [Imagen de fondo de escritorio](config-setting-ref.md#desktop-background-picture) : Personalice la imagen de fondo de escritorio de los dispositivos de escritorio administrados por Microsoft. 
- [Páginas de inicio del explorador](config-setting-ref.md#browser-start-pages) : agrega páginas de inicio para usarlas con Microsoft Edge. Ver página de inicio del explorador
- [Lista de sitios del modo de empresa](config-setting-ref.md#enterprise-mode-site-list-location) : agregue sitios y su modo de compatibilidad. Los sitios de la lista se iniciarán en Internet Explorer. 
- [Sitios de confianza](config-setting-ref.md#trusted-sites) : agregue sitios de confianza y establezca zonas de seguridad para cada sitio. 
- [Excepciones de sitio proxy](config-setting-ref.md#proxy) : configure el número de puerto y número de dirección del servidor proxy y agregue excepciones de sitio de proxy.

Cada categoría de configuración se puede personalizar e implementar por su cuenta. Puede implementar cambios en varias categorías de configuración al mismo tiempo, pero solo puede implementar un cambio a la vez en una categoría de configuración.

Por ejemplo:
- Puede implementar cambios en la imagen de fondo de escritorio y en los sitios de confianza, cada uno como su propia implementación, al mismo tiempo. 
- No puede implementar dos implementaciones en las páginas de inicio del explorador al mismo tiempo. La implementación más reciente detendrá las implementaciones anteriores que aún están en curso.

## <a name="configurable-setting-process"></a>Proceso de configuración configurable

Microsoft manAged Desktop recomienda seguir un proceso similar al siguiente cuando se usan opciones configurables para su organización:

**Paso 1: Plan** : Obtenga información sobre la configuración configurable y decida qué categorías de configuración desea configurar para su organización. Cree una escala de tiempo para cuando tenga previsto implementar cambios en cada grupo. Planee la comunicación a los usuarios que cumplan los procesos internos de administración de cambios. Por ejemplo, si va a agregar páginas de inicio del explorador, indique a los usuarios que tendrán un nuevo conjunto de páginas de inicio en el explorador después de la implementación.  

**Paso 2: configurar y ensayar la implementación** : realice cambios en la configuración configurable en el portal de administración de escritorio administrado de Microsoft. Ensaye los cambios para que estén listos para la implementación. Recuerde informar a los usuarios sobre los cambios y cómo los cambios cambiarán la experiencia del dispositivo.   

Configure y almacene los cambios en el portal de administración de escritorio administrado de Microsoft. Para obtener más información, vea [personalizar opciones](config-setting-ref.md)configurables. 

**Paso 3: comunicar los cambios** Comunique la información sobre los próximos cambios a sus usuarios. Para cada implementación, complete la comunicación que forma parte de los procesos de administración de cambios. Debe comunicarse con claridad cualquier cambio que afecte al funcionamiento de un usuario o lo que verán en sus dispositivos.

**Paso 4: implementar los** cambios: implemente los cambios, comenzando con el grupo de prueba. El grupo de pruebas permite validar y solucionar problemas en un grupo con menos dispositivos, antes de implementar cambios en grupos de dispositivos de mayor tamaño. Si tiene algún problema, puede revertir el cambio, actualizar la configuración y ensayar una nueva implementación. Microsoft manAged Desktop recomienda seguir el enfoque estructurado e implementarlo en grupos en este orden: test, First, Fast y, a continuación, general.   

Todas las opciones de configuración que se pueden configurar se administran mediante el portal de administración de escritorio administrado de Microsoft. Para obtener más información, vea [implementar cambios](config-setting-deploy.md). 

**Paso 5: control de cambios** : realice un seguimiento del progreso de los cambios en el estado de la implementación. Para cada configuración, puede:
- **Seguimiento del progreso** : realice un seguimiento del estado después de implementar el cambio. El estado cambiará a **en curso**y, a continuación ****, se completará o **no**. Si se produce un error en la implementación, se abre automáticamente una solicitud de soporte técnico para las operaciones de escritorio administradas de Microsoft para investigar el problema.  
- **Ver versión implementada** : cada cambio implementado tiene un número de versión.
- **Revertir cambios** : la reversión de un cambio detiene la implementación actual y revierte todos los grupos a los últimos cambios que se implementaron en todos los grupos. Va a revertir al valor de configuración de última configuración buena conocida.
- **Validar cambios** : una vez completada la implementación, valide que los cambios se han aplicado como se esperaba.  

Si se produce un error en una implementación o no puede revertir un cambio, [abra una solicitud de soporte técnico](admin-support.md) con Microsoft Managed Desktop Operations. 

Para obtener más información, vea [implementar y realizar un seguimiento](config-setting-deploy.md)de las opciones configurables.

## <a name="additional-resources"></a>Recursos adicionales
- [Referencia de opciones conFigurables](config-setting-ref.md) 
- [Implementar opciones configurables](config-setting-deploy.md) 
