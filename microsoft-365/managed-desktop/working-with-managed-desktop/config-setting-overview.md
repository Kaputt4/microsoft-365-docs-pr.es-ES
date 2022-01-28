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
ms.openlocfilehash: 910bd8d37853ce70acb6379599b0259446b0752e
ms.sourcegitcommit: 2c3b737e71038f843ef9e9ff4d5b99d6110b8ec5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2022
ms.locfileid: "62265672"
---
# <a name="configurable-settings---microsoft-managed-desktop"></a>Opciones configurables: Escritorio administrado de Microsoft

Microsoft Managed Desktop implementa la configuración y las directivas que se aplican a todos los dispositivos administrados por Microsoft Managed Desktop. Para obtener más información, consulta [Configuración del dispositivo](../service-description/device-policies.md).

La configuración configurable en Microsoft Managed Desktop ofrece a los administradores de TI una forma de personalizar e implementar configuraciones que son únicas para sus necesidades empresariales y de organización. Esta configuración se suma a las directivas y las opciones de configuración del dispositivo administradas por Microsoft Managed Desktop.  

Los cambios de configuración configurables se realizan en la nube. Se aplican a los dispositivos de Escritorio administrado de Microsoft en grupos de implementación definidos. Este proceso es similar al modo en que Microsoft Managed Desktop administra los cambios en las directivas y las opciones de configuración del dispositivo definidas y administradas por el servicio. Al usar el mismo proceso que usa Microsoft Managed Desktop para implementar cambios, se sigue avanzando en la organización, con prácticas modernas de administración de TI.

## <a name="when-to-use-configurable-settings"></a>¿Cuándo usar la configuración configurable?

Use la configuración configurable en los siguientes escenarios:

| Escenario | Descripción |
| ------ | ------ |
| Proceso de incorporación | Microsoft Managed Desktop recomienda personalizar la configuración configurable cuando se incorpora al servicio de Escritorio administrado de Microsoft o al incorporar un gran número de dispositivos (20 o más). <br><br>Las categorías de configuración se configuran en el portal de administración de Escritorio administrado de Microsoft. Después de incorporar y tener acceso al portal de administración, puede decidir qué categorías desea personalizar para su organización. Después, realice los cambios, realice una implementación y, a continuación, implemente los cambios. |
| Mantener la configuración | Revisa la configuración con regularidad y realiza las actualizaciones necesarias. Es posible que deba realizar cambios para admitir un cambio en su empresa. |

## <a name="setting-categories"></a>Establecer categorías

Las siguientes son las categorías de configuración configurables que puede personalizar:

| Categoría | Descripción |
| ------ | ------ |
| [Imagen de fondo de escritorio](config-setting-ref.md#desktop-background-picture) | Personalice la imagen en segundo plano de escritorio para dispositivos de Escritorio administrado de Microsoft. |
| [Páginas de inicio del explorador](config-setting-ref.md#browser-start-pages) | Agregue páginas de inicio para usarlas con Microsoft Edge. |
| [Enterprise de sitio de modo de acceso](config-setting-ref.md#enterprise-mode-site-list-location) | Agregar sitios y su modo de compatibilidad. Los sitios de la lista se iniciarán en Internet Explorer. |
| [Sitios de confianza](config-setting-ref.md#trusted-sites) | Agregue sitios de confianza y establezca zonas de seguridad para cada sitio. |
| [Excepciones de sitio proxy](config-setting-ref.md#proxy) | Configure el número de dirección y el número de puerto del servidor proxy y agregue excepciones de sitio proxy. |

Cada categoría de configuración se puede personalizar e implementar por sí sola. Puede implementar cambios en varias categorías de configuración al mismo tiempo. Sin embargo, solo puede implementar un cambio a la vez en una categoría de configuración.

Por ejemplo:

- Puede implementar cambios en la imagen en segundo plano del escritorio y los sitios de confianza, cada uno como su propia implementación, al mismo tiempo.
- No puede implementar dos implementaciones en las páginas de inicio del explorador al mismo tiempo. La implementación más reciente detendrá las implementaciones anteriores que aún están en curso.

## <a name="configurable-setting-process"></a>Proceso de configuración configurable

Microsoft Managed Desktop recomienda seguir un proceso como el siguiente al usar opciones configurables para su organización:

| Paso  | Proceso |
| ------ | ------ |
| **Paso 1: planeación** | <ol type="1"><li>Obtenga información sobre la configuración configurable y decida qué categorías de configuración desea configurar para su organización.</li> <li>Crea una escala de tiempo cuando esperas implementar cambios en cada grupo.</li> <li>Planee la comunicación con los usuarios que cumplan los procesos de administración de cambios internos. Por ejemplo, si va a agregar páginas de inicio del explorador, informe a los usuarios de que tendrán un nuevo conjunto de páginas de inicio en su explorador después de la implementación.</li></ol> |
| **Paso 2: Configurar y fase de implementación** | <ol type="1"><li>Realice cambios en la configuración configurable en el portal de administración de Escritorio administrado de Microsoft.</li><li>Realice una fase de los cambios para que estén listos para implementarlos.</li> <li>Recuerda informar a los usuarios sobre los cambios y cómo cambiarán la experiencia del dispositivo.</li><li>Configure y realice cambios de fase en el portal de administración de Microsoft Managed Desktop. Para obtener más información, vea [Personalizar la configuración configurable](config-setting-ref.md).</li></ol>|
| **Paso 3: Comunicar cambios** | <ol type="1"><li>Comunicar información sobre los próximos cambios a los usuarios.</li> <li>Para cada implementación, complete la comunicación que forma parte de los procesos de administración de cambios. Debes comunicar claramente cualquier cambio que repercuta en el funcionamiento de un usuario o en lo que verán en sus dispositivos.</li></ol> |
| **Paso 4: Implementar cambios** | Implemente los cambios, empezando por el grupo Prueba. El grupo De prueba le permite validar y solucionar problemas en un grupo con menos dispositivos, antes de implementar cambios en grupos de dispositivos más grandes. <br><br>Si se encuentra con algún problema, puede revertir el cambio, actualizar la configuración y realizar una nueva implementación. Microsoft Managed Desktop recomienda seguir el enfoque estructurado e implementar en grupos en este orden: Test, First, Fast y, a continuación, Broad. <br><br>Todas las opciones de configuración configurables se administran mediante el portal de administración de Escritorio administrado de Microsoft. Para obtener más información, vea [Deploy changes](config-setting-deploy.md). |
| **Paso 5: Realizar un seguimiento de los cambios** | Realice un seguimiento del progreso de los cambios en la sección Estado de implementación. Para cada configuración, puede: <ul><li>**Realizar un seguimiento del progreso:**  Realice un seguimiento del estado después de implementar el cambio. El estado cambiará a **In progress** y, a continuación, **Complete** o **Failed**. Si se produce un error en una implementación, se abre automáticamente una solicitud de soporte técnico para que Microsoft Managed Desktop Operations investigue el problema.</li> <li>**Vea la versión implementada:** Cada cambio implementado tiene un número de versión.</li><li>**Revertir cambios:** Revertir un cambio detiene la implementación actual. Revierte todos los grupos a los últimos cambios implementados en todos los grupos. Vuelves al último valor de configuración conocido como bueno.</li><li>**Validar cambios:** Una vez completada la implementación, valide que los cambios se aplicaron como esperaba.</li></ul> |

Si se ha fallado una implementación o no se puede revertir un cambio, [abra una](admin-support.md) solicitud de soporte técnico con Operaciones de escritorio administrado de Microsoft.

Para obtener más información, vea [Deploy and track configurable settings](config-setting-deploy.md).

## <a name="additional-resources"></a>Recursos adicionales

- [Referencia de parámetros configurables](config-setting-ref.md)
- [Implementar parámetros configurables](config-setting-deploy.md)
