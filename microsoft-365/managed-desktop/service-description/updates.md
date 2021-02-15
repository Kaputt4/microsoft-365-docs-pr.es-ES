---
title: Cómo se controlan las actualizaciones en el Escritorio administrado de Microsoft
description: Mantener actualizado el Escritorio administrado de Microsoft es un equilibrio de velocidad y estabilidad.
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 4d8de363cc9111fade719fdf5384519d1236f431
ms.sourcegitcommit: 05657b39eaafc0503b01c6adcc5d8a5e615dc02c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/27/2021
ms.locfileid: "50031344"
---
# <a name="how-updates-are-handled-in-microsoft-managed-desktop"></a>Cómo se controlan las actualizaciones en el Escritorio administrado de Microsoft


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/update-rings); do not delete.-->

<!--Update management -->

Escritorio administrado de Microsoft conecta todos los dispositivos a una infraestructura moderna basada en la nube. Mantener actualizados Windows, Office, los controladores, el firmware y las aplicaciones de la Microsoft Store para Empresas es un equilibrio entre velocidad y estabilidad. Los grupos de implementación se usarán para garantizar que las directivas y las actualizaciones del sistema operativo se implementarán de forma segura. Para obtener más información, vea el vídeo [Microsoft Managed Desktop Change and Release Process](https://www.microsoft.com/videoplayer/embed/RE4mWqP).

Las actualizaciones publicadas por Microsoft son acumulativas y se clasifican como actualizaciones de calidad o características.
Para obtener más información, consulta [Windows Update para empresas: tipos de actualización.](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb#update-types) 

## <a name="update-groups"></a>Actualizar grupos

Escritorio administrado de Microsoft usa cuatro grupos de Azure AD para administrar las actualizaciones:

- **Prueba:** se usa para validar los cambios de directiva de Escritorio administrado de Microsoft, las actualizaciones del sistema operativo, las actualizaciones de características y otros cambios que se insertan en el espacio empresarial. No debe haber ningún usuario en el grupo de prueba. El grupo de pruebas está exento de los contratos de nivel de servicio establecidos y la compatibilidad con usuarios. Este grupo está disponible para su uso para validar la compatibilidad de aplicaciones con nuevos cambios de directiva o sistema operativo.  
- **En** primer lugar: contiene dispositivos y usuarios iniciales de software que podrían estar sujetos a actualizaciones de versión previa. Los dispositivos de este grupo pueden experimentar interrupciones si hay escenarios que no se han cubierto durante las pruebas en el anillo de pruebas.
- **Rápido:** prioriza la velocidad sobre la estabilidad. Es útil para detectar problemas de calidad antes de ofrecerlos al grupo General. Este grupo actúa como una siguiente capa de validación, pero suele ser más estable que los grupos Test y First. 
- **Amplia:** último grupo que tiene actualizaciones de características y calidad disponibles. Este grupo contiene la mayoría de los usuarios del inquilino y, por lo tanto, favorece la estabilidad sobre la velocidad de implementación. Las pruebas de aplicaciones deben realizarse aquí, ya que el entorno es más estable. 

### <a name="moving-devices-between-update-groups"></a>Mover dispositivos entre grupos de actualización
Es posible que quieras que algunos dispositivos reciban actualizaciones en último lugar y otros que quieras ir primero. Para mover estos dispositivos al grupo de actualización adecuado, [envía una](https://docs.microsoft.com/microsoft-365/managed-desktop/working-with-managed-desktop/admin-support?view=o365-worldwide) solicitud de soporte técnico de administrador y los moveremos por ti. 

> [!NOTE]
> Si necesitas mover un usuario a un grupo de actualización diferente, envía una solicitud de soporte técnico. No mueva dispositivos entre grupos de actualización usted mismo. Hay consecuencias graves si un dispositivo se mueve incorrectamente. El dispositivo podría actualizarse inesperadamente y es posible que las directivas entren en conflicto, cambiando la configuración del dispositivo.

Para obtener más información sobre roles y responsabilidades dentro de estos grupos de implementación, vea Roles y responsabilidades de Escritorio administrado [de Microsoft](../intro/roles-and-responsibilities.md)

### <a name="using-microsoft-managed-desktop-update-groups"></a>Uso de grupos de actualización de Escritorio administrado de Microsoft 
Hay partes del servicio que administras, como la implementación de aplicaciones, donde podría ser necesario dirigirte a todos los dispositivos administrados. En estos casos, tiene sentido usar grupos de actualización para llegar a esos usuarios con la comprensión de que no se puede agregar, quitar o cambiar la pertenencia de esos grupos. 

## <a name="how-update-deployment-works"></a>Cómo funciona la implementación de actualizaciones:
1. Escritorio administrado de Microsoft implementa una nueva característica o actualización de calidad según la programación especificada en la tabla siguiente.
2. Durante la implementación, Escritorio administrado de Microsoft supervisa si hay signos de error o interrupción en función de los datos de diagnóstico y el sistema de soporte técnico del usuario. Si se detecta alguna, pausamos inmediatamente la implementación en todos los grupos actuales y futuros.
    - Ejemplo: si se detecta un problema al implementar una actualización de calidad en el grupo First, todas las implementaciones de actualización a First, Fast y Broad se pondrán en pausa hasta que se resuelva el problema.
    - Puede informar de problemas de compatibilidad archivando un vale en el portal de administración de escritorio administrado de Microsoft.
    - Las actualizaciones de características y calidad se pausan de forma independiente. La pausa está en vigor durante 35 días de forma predeterminada, pero se puede reducir o ampliar en función de si se corrige el problema.
3. Una vez que los grupos están sin pausar, la implementación se reanuda de acuerdo con la programación de la tabla.

Este proceso de implementación se aplica a las actualizaciones de características y de calidad, aunque la escala de tiempo varía para cada una.




<table>
    <tr><th colspan="5">Actualizar la configuración de implementación</th></tr>
    <tr><th>Tipo de actualización</th><th>Prueba</th><th>Primero</th><th>Rápida</th><th>Amplias</th></tr>
    <tr><td>Actualizaciones de calidad para el sistema operativo</td><td>0 días</td><td>0 días</td><td>0 días</td><td>3 días</td></tr>
    <tr><td>Actualizaciones de características para el sistema operativo</td><td>0 días</td><td>30 días</td><td>60 días</td><td>90 días</td></tr>
    <tr><td>Controladores/firmware</td><td colspan="4">Sigue la programación de actualizaciones de calidad</td></tr>
    <tr><td>Definición de antivirus</td><td colspan="4">Actualizado con cada examen</td></tr>
    <tr><td>Aplicaciones de Microsoft 365 para empresas</td><td colspan="4"><a href="https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/m365-apps#updates-to-microsoft-365-apps">Más información</a></td></tr>
    <tr><td>Microsoft Edge</td><td colspan="4"><a href="https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/edge-browser-app#updates-to-microsoft-edge">Más información</a></td></tr>
    <tr><td>Microsoft Teams</td><td colspan="4"><a href="https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/teams#updates">Más información</a></td></tr>
</table>

>[!NOTE]
>Estos períodos de aplazamiento están diseñados intencionadamente para garantizar altos estándares de seguridad y rendimiento para todos los usuarios. Además, en función de los datos recopilados en todos los dispositivos de Escritorio administrado de Microsoft y del alcance y el impacto de las actualizaciones, Escritorio administrado de Microsoft se reserva flexibilidad para modificar la duración de los períodos de aplazamiento anteriores para todos y cada uno de los grupos de implementación de forma ad hoc.
>
>Escritorio administrado de Microsoft realiza una evaluación independiente de cada versión de características de Windows para evaluar su necesidad y utilidad para sus inquilinos administrados. Por lo tanto, escritorio administrado de Microsoft podría o no implementar todas las actualizaciones de características de Windows. 

## <a name="windows-insider-program"></a>Programa Windows Insider

Escritorio administrado de Microsoft no admite dispositivos que forman parte del programa Windows Insider. El programa Windows Insider se usa para validar el software de Windows de versión previa y está pensado para dispositivos que no son esenciales. Aunque es una iniciativa importante de Microsoft, no está pensada para una implementación amplia en entornos de producción. 

Los dispositivos que se encuentran con compilaciones de Windows Insider pueden colocarse en el grupo de pruebas y estarán exentos de los contratos de nivel de servicio de actualización y la compatibilidad con usuarios del Escritorio administrado de Microsoft.

## <a name="bandwidth-management"></a>Administración de ancho de banda

Usamos [Optimización de distribución](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization) para todas las actualizaciones del sistema operativo y los controladores. Esto minimiza el tamaño de descarga del servicio de Windows Update al buscar actualizaciones de sistemas del mismo nivel dentro de la red corporativa.

