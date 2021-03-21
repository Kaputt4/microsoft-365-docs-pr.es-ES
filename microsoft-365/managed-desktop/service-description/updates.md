---
title: Cómo se controlan las actualizaciones en Microsoft Managed Desktop
description: Mantener el escritorio administrado de Microsoft actualizado es un equilibrio entre velocidad y estabilidad.
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 5961ac4eb16928754849f5f32ecd06d4d2e4650d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917721"
---
# <a name="how-updates-are-handled-in-microsoft-managed-desktop"></a>Cómo se controlan las actualizaciones en Microsoft Managed Desktop


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/update-rings); do not delete.-->

<!--Update management -->

Microsoft Managed Desktop conecta todos los dispositivos a una infraestructura moderna basada en la nube. Mantener las aplicaciones de Windows, Office, controladores, firmware y Microsoft Store para empresas actualizadas es un equilibrio entre velocidad y estabilidad. Los grupos de implementación se usarán para garantizar que las directivas y actualizaciones del sistema operativo se implementarán de forma segura. Para obtener más información, vea el vídeo [Microsoft Managed Desktop Change and Release Process](https://www.microsoft.com/videoplayer/embed/RE4mWqP).

Las actualizaciones publicadas por Microsoft son acumulativas y se clasifican como actualizaciones de calidad o características.
Para obtener más información, [consulta Windows Update para empresas: Tipos de actualización.](/windows/deployment/update/waas-manage-updates-wufb#update-types) 

## <a name="update-groups"></a>Actualizar grupos

Microsoft Managed Desktop usa cuatro grupos de Azure AD para administrar actualizaciones:

- **Prueba:** se usa para validar los cambios de directiva de Escritorio administrado de Microsoft, las actualizaciones del sistema operativo, las actualizaciones de características y otros cambios que se insertan en el espacio empresarial. No debe haber ningún usuario en el grupo de prueba. El grupo de prueba está exento de los acuerdos de nivel de servicio establecidos y la compatibilidad con usuarios. Este grupo está disponible para su uso para validar la compatibilidad de aplicaciones con nuevos cambios en la directiva o el sistema operativo.  
- **En** primer lugar: contiene los primeros usuarios y dispositivos de software que podrían estar sujetos a actualizaciones previas a la versión. Los dispositivos de este grupo pueden experimentar interrupciones si hay escenarios que no se han cubierto durante las pruebas en el anillo de prueba.
- **Rápido:** prioriza la velocidad sobre la estabilidad. Es útil para detectar problemas de calidad antes de ofrecerlos al grupo Broad. Este grupo sirve como una siguiente capa de validación, pero normalmente es más estable que los grupos Test y First. 
- **Broad:** último grupo que tiene actualizaciones de características y calidad disponibles. Este grupo contiene la mayoría de los usuarios del espacio empresarial y, por lo tanto, favorece la estabilidad sobre la velocidad en la implementación. Las pruebas de aplicaciones deben realizarse aquí, ya que el entorno es más estable. 

### <a name="moving-devices-between-update-groups"></a>Mover dispositivos entre grupos de actualización
Es posible que quieras que algunos dispositivos reciban actualizaciones en último lugar y otros que quieras ir primero. Para mover estos dispositivos al grupo de actualización adecuado, [envíe una](../working-with-managed-desktop/admin-support.md?view=o365-worldwide) solicitud de soporte técnico de administrador y moveremos los dispositivos por usted. 

> [!NOTE]
> Si necesita mover un usuario a un grupo de actualización diferente, envíe una solicitud de soporte técnico. No mueva dispositivos entre grupos de actualización usted mismo. Hay consecuencias graves si un dispositivo se mueve incorrectamente. El dispositivo podría actualizarse inesperadamente y las directivas podrían estar en conflicto, cambiando la configuración del dispositivo.

Para obtener más información sobre roles y responsabilidades dentro de estos grupos de implementación, vea [Roles y responsabilidades](../intro/roles-and-responsibilities.md) de escritorio administrado de Microsoft

### <a name="using-microsoft-managed-desktop-update-groups"></a>Uso de grupos de actualización de Escritorio administrado de Microsoft 
Hay partes del servicio que administras, como la implementación de aplicaciones, donde es posible que sea necesario dirigirte a todos los dispositivos administrados. En estos casos, tiene sentido usar grupos de actualización para llegar a esos usuarios con el conocimiento de que no se puede agregar, quitar o cambiar la pertenencia a esos grupos. 

## <a name="how-update-deployment-works"></a>Cómo funciona la implementación de actualización:
1. Microsoft Managed Desktop implementa una nueva característica o actualización de calidad según la programación especificada en la tabla siguiente.
2. Durante la implementación, Microsoft Managed Desktop supervisa si hay signos de error o interrupción en función de los datos de diagnóstico y el sistema de soporte técnico del usuario. Si se detecta alguna, pausamos inmediatamente la implementación en todos los grupos actuales y futuros.
    - Ejemplo: si se detecta un problema al implementar una actualización de calidad en el grupo First, las implementaciones de actualización a First, Fast y Broad se pausarán hasta que se resuelva el problema.
    - Puede notificar problemas de compatibilidad mediante la presentación de un vale en el portal de administración de Escritorio administrado de Microsoft.
    - Las actualizaciones de características y calidad se pausan de forma independiente. La pausa está en vigor durante 35 días de forma predeterminada, pero se puede reducir o ampliar en función de si se corrige el problema.
3. Una vez que los grupos están en pausa, la implementación se reanuda de acuerdo con la programación de la tabla.

Este proceso de implementación se aplica a las actualizaciones de características y de calidad, aunque la escala de tiempo varía para cada una.




<table>
    <tr><th colspan="5">Actualizar la configuración de implementación</th></tr>
    <tr><th>Tipo de actualización</th><th>Prueba</th><th>Primero</th><th>Rápida</th><th>Amplias</th></tr>
    <tr><td>Actualizaciones de calidad para el sistema operativo</td><td>0 días</td><td>0 días</td><td>0 días</td><td>3 días</td></tr>
    <tr><td>Actualizaciones de características para el sistema operativo</td><td>0 días</td><td>30 días</td><td>60 días</td><td>90 días</td></tr>
    <tr><td>Controladores/firmware</td><td colspan="4">Sigue la programación de actualizaciones de calidad</td></tr>
    <tr><td>Definición antivirus</td><td colspan="4">Actualizado con cada examen</td></tr>
    <tr><td>Aplicaciones de Microsoft 365 para empresas</td><td colspan="4"><a href="/microsoft-365/managed-desktop/get-started/m365-apps#updates-to-microsoft-365-apps">Más información</a></td></tr>
    <tr><td>Microsoft Edge</td><td colspan="4"><a href="/microsoft-365/managed-desktop/get-started/edge-browser-app#updates-to-microsoft-edge">Más información</a></td></tr>
    <tr><td>Microsoft Teams</td><td colspan="4"><a href="/microsoft-365/managed-desktop/get-started/teams#updates">Más información</a></td></tr>
</table>

>[!NOTE]
>Estos períodos de aplazamiento están diseñados intencionadamente para garantizar altos estándares de seguridad y rendimiento para todos los usuarios. Además, en función de los datos recopilados en todos los dispositivos de Escritorio administrado de Microsoft y el alcance y el impacto de las actualizaciones, Microsoft Managed Desktop se reserva flexibilidad para modificar la longitud de los períodos de aplazamiento anteriores para todos y cada uno de los grupos de implementación de forma ad hoc.
>
>Microsoft Managed Desktop realiza una evaluación independiente de cada versión de característica de Windows para evaluar su necesidad y utilidad para sus inquilinos administrados. Por lo tanto, Microsoft Managed Desktop podría o no implementar todas las actualizaciones de características de Windows. 

## <a name="windows-insider-program"></a>Programa Windows Insider

Microsoft Managed Desktop no admite dispositivos que forman parte del programa Windows Insider. El programa Windows Insider se usa para validar el software de Windows de versión previa y está pensado para dispositivos que no son críticos. Aunque es una iniciativa importante de Microsoft, no está diseñada para una implementación amplia en entornos de producción. 

Los dispositivos que se encuentran con las compilaciones de Windows Insider pueden colocarse en el grupo De prueba y estarán exentos de actualizar los contratos de nivel de servicio y el soporte del usuario del Escritorio administrado de Microsoft.

## <a name="bandwidth-management"></a>Administración de ancho de banda

Usamos [optimización de distribución](/windows/deployment/update/waas-delivery-optimization) para todas las actualizaciones de controladores y sistemas operativos. Esto minimiza el tamaño de descarga del servicio Windows Update al buscar actualizaciones de los sistemas del mismo nivel dentro de la red corporativa.