---
title: Cómo se controlan las actualizaciones en Microsoft Managed Desktop
description: Mantener el escritorio administrado de Microsoft actualizado es un equilibrio entre velocidad y estabilidad.
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: tiaraquan
f1.keywords:
- NOCSH
ms.author: tiaraquan
manager: dougeby
ms.topic: article
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.openlocfilehash: 5e696f1b89cf03bbd4123252ea967e2aca10ef49
ms.sourcegitcommit: 007822d16e332522546e948f5c216327254a4d49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/17/2022
ms.locfileid: "62879257"
---
# <a name="how-updates-are-handled-in-microsoft-managed-desktop"></a>Cómo se controlan las actualizaciones en Microsoft Managed Desktop

<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/update-rings); do not delete.-->

<!--Update management -->

Microsoft Managed Desktop conecta todos los dispositivos a una infraestructura moderna basada en la nube.

Mantener Windows, Office, controladores, firmware y Microsoft Store para Empresas aplicaciones actualizadas es un equilibrio entre velocidad y estabilidad. Usamos grupos de actualizaciones para garantizar que las directivas y actualizaciones del sistema operativo se revierte de forma segura. Para obtener más información, vea el vídeo [Microsoft Managed Desktop Change and Release Process](https://www.microsoft.com/videoplayer/embed/RE4mWqP).

Las actualizaciones publicadas por Microsoft son acumulativas y se clasifican como actualizaciones de calidad o características. Para obtener más información, [vea Windows Update for Business: Update types](/windows/deployment/update/waas-manage-updates-wufb#update-types).

## <a name="update-groups"></a>Actualizar grupos

Microsoft Managed Desktop usa cuatro Azure AD para administrar actualizaciones:

| Group | Descripción |
| ------ | ------ |
| Prueba | Se usa para validar los cambios de directiva de Escritorio administrado de Microsoft, las actualizaciones del sistema operativo, las actualizaciones de características y otros cambios que se insertan en la Azure AD ("inquilino"). El grupo De prueba es: <ul><li>Lo mejor para las pruebas o los usuarios que pueden proporcionar comentarios anticipados.</li><li>Exento de los contratos de nivel de servicio establecidos y la compatibilidad con usuarios.</li><li>Disponible para validar la compatibilidad de aplicaciones con nuevos cambios en la directiva o el sistema operativo.</li></ul> |
| Primero | Contiene los primeros usuarios y dispositivos de software que podrían estar sujetos a actualizaciones previas a la versión. <br><br> Los dispositivos de este grupo pueden experimentar interrupciones si hay escenarios que no se han cubierto durante las pruebas en el anillo de prueba. |
| Rápida | Prioriza la velocidad sobre la estabilidad. El grupo Rápido es: <ul><li>Es útil para detectar problemas de calidad antes de ofrecerlos al grupo Broad.</li> <li>La siguiente capa de validación y suele ser más estable que los grupos Test y First.</li></ul> |
| Amplias | Este grupo es el último que tiene actualizaciones de características y calidad disponibles. <br><br> El grupo Broad contiene la mayoría de los usuarios de la Azure AD y, por lo tanto, favorece la estabilidad sobre la velocidad en la implementación. Las pruebas de aplicaciones deben realizarse con este grupo porque el entorno es el más estable. |

### <a name="moving-devices-between-update-groups"></a>Mover dispositivos entre grupos de actualización

Es posible que quieras que algunos dispositivos reciban actualizaciones en último lugar y otros que quieras ir primero. Para mover estos dispositivos al grupo de actualizaciones adecuado, consulta [Asignar dispositivos a un grupo de implementación](../working-with-managed-desktop/assign-deployment-group.md).

Para obtener más información sobre roles y responsabilidades dentro de estos grupos de implementación, vea [Roles y responsabilidades de escritorio administrado de Microsoft](../intro/roles-and-responsibilities.md)

### <a name="using-microsoft-managed-desktop-update-groups"></a>Uso de grupos de actualización de Escritorio administrado de Microsoft

Hay partes del servicio que administras, como la implementación de aplicaciones, donde es posible que sea necesario dirigirte a todos los dispositivos administrados.

## <a name="update-deployment"></a>Actualización de la implementación

A continuación se describe cómo funciona la implementación de actualizaciones.

| Paso | Descripción |
| ------ | ------ |
| Paso 1 | Microsoft Managed Desktop implementa una nueva característica o actualización de calidad de acuerdo con la programación especificada en la tabla siguiente.|
| Paso 2 | Durante la implementación, Microsoft Managed Desktop supervisa si hay signos de error o interrupción en función de los datos de diagnóstico y el sistema de soporte técnico del usuario. Si se detecta alguna, pausamos inmediatamente la implementación en todos los grupos actuales y futuros.<br><br> Por ejemplo, si se detecta un problema al implementar una actualización de calidad en el grupo First, las implementaciones de actualización a los grupos First, Fast y Broad se pausarán hasta que se mitigue el problema. <br><br> Puede notificar problemas de compatibilidad mediante la presentación de un vale en el portal de administración de Escritorio administrado de Microsoft. <br><br> Las actualizaciones de características y calidad se pausan de forma independiente. La pausa está en vigor durante 35 días de forma predeterminada. Sin embargo, puede reducirse o extenderse en función de si se mitiga el problema. |
| Paso 3 | Una vez que los grupos no se usan, la implementación se reanuda de acuerdo con la programación de la tabla. |
| Paso 4| Los usuarios tienen la capacidad de responder a las notificaciones de reinicio durante un período establecido. Este período se conoce como fecha límite y se mide desde el momento en que se ofrece la actualización al dispositivo. <br><br> Durante este tiempo, el dispositivo solo se reiniciará automáticamente fuera del horario activo. Una vez expirado este período, se ha alcanzado la fecha límite y el dispositivo se reiniciará en la próxima oportunidad disponible, independientemente de las horas activas. <br><br> La fecha límite para las actualizaciones de calidad es de tres días; para las actualizaciones de características son cinco días. |

> [!NOTE]
> Este proceso de implementación se aplica a las actualizaciones de características y de calidad, aunque la escala de tiempo varía para cada una.

## <a name="deployment-settings"></a>Configuración de implementación

Actualice la configuración de implementación que se muestra a continuación:

| Tipo de actualización | Prueba | Primero | Rápida | Amplias |
| ------ | ------ | ------ | ------ | ------ |
| Actualizaciones de calidad para el sistema operativo | Cero días | Cero días | Cero días | Siete días |
| Actualizaciones de características para el sistema operativo | Cero días | 30 días | 60 días | 90 días |
| Controladores/firmware | Sigue la programación de actualizaciones de calidad. | Sigue la programación de actualizaciones de calidad. | Sigue la programación de actualizaciones de calidad. | Sigue la programación de actualizaciones de calidad. |
| Definición antivirus | Se actualiza con cada examen. | Se actualiza con cada examen. | Se actualiza con cada examen. | Se actualiza con cada examen. |
| Aplicaciones de Microsoft 365 para empresas | [Más información](../get-started/m365-apps.md#updates-to-microsoft-365-apps) | [Más información](../get-started/m365-apps.md#updates-to-microsoft-365-apps) | [Más información](../get-started/m365-apps.md#updates-to-microsoft-365-apps) | [Más información](../get-started/m365-apps.md#updates-to-microsoft-365-apps) |
| Microsoft Edge | [Más información](../get-started/edge-browser-app.md#updates-to-microsoft-edge) | [Más información](../get-started/edge-browser-app.md#updates-to-microsoft-edge) | [Más información](../get-started/edge-browser-app.md#updates-to-microsoft-edge) | [Más información](../get-started/edge-browser-app.md#updates-to-microsoft-edge) |
| Microsoft Teams | [Más información](../get-started/teams.md#updates) | [Más información](../get-started/teams.md#updates) | [Más información](../get-started/teams.md#updates) | [Más información](../get-started/teams.md#updates) |

>[!NOTE]
>Estos períodos de aplazamiento están diseñados intencionadamente para garantizar altos estándares de seguridad y rendimiento para todos los usuarios.<br><br> En función de los datos recopilados en todos los dispositivos de Escritorio administrado de Microsoft y el alcance y el impacto de las actualizaciones, Microsoft Managed Desktop se reserva flexibilidad para modificar la longitud de los períodos de aplazamiento anteriores para todos y cada uno de los grupos de implementación de forma ad hoc.
>
>Microsoft Managed Desktop realiza una evaluación independiente de cada versión Windows de características para evaluar su necesidad y utilidad para sus inquilinos administrados. Por lo tanto, Microsoft Managed Desktop podría o no implementar todas las actualizaciones Windows características.

## <a name="windows-insider-program"></a>Programa Windows Insider

Microsoft Managed Desktop no admite dispositivos que forman parte del programa Windows Insider.

El Windows Insider se usa para validar la versión previa Windows software. Está pensado para dispositivos que no son críticos. Aunque es una iniciativa importante de Microsoft, no está diseñada para una implementación amplia en entornos de producción.

Los dispositivos que se Windows compilaciones de Insider pueden colocarse en el grupo Prueba. Estos dispositivos estarán exentos de actualizar los contratos de nivel de servicio y el soporte del usuario de Microsoft Managed Desktop.

## <a name="bandwidth-management"></a>Administración de ancho de banda

Usamos [optimización de distribución](/windows/deployment/update/waas-delivery-optimization) para todas las actualizaciones de controladores y sistemas operativos. Optimización de distribución minimiza el tamaño de descarga del servicio de actualización Windows mediante la búsqueda de actualizaciones de los sistemas del mismo nivel dentro de la red corporativa.
