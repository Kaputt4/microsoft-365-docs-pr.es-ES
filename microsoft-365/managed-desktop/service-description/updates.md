---
title: Cómo se administran las actualizaciones en el escritorio administrado por Microsoft
description: Mantener el escritorio administrado de Microsoft actualizado es un equilibrio entre velocidad y estabilidad.
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 03a9b19a5b8ba957419e23c2bb12748c9c57e80d
ms.sourcegitcommit: adaedd1418a3bd6e4875b77fd9e008b47e0b2a51
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2020
ms.locfileid: "48104623"
---
# <a name="how-updates-are-handled-in-microsoft-managed-desktop"></a>Cómo se administran las actualizaciones en el escritorio administrado por Microsoft


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/update-rings); do not delete.-->

<!--Update management -->

Microsoft Managed Desktop conecta todos los dispositivos con una infraestructura moderna basada en la nube. Mantener Windows, Office, los controladores, el firmware y las aplicaciones de Microsoft Store para empresas actualizadas es un equilibrio entre velocidad y estabilidad. Los grupos de implementación se usarán para asegurarse de que las directivas y las actualizaciones del sistema operativo se implementan de forma segura. Para obtener más información al respecto, vea el vídeo [Microsoft Managed Desktop Change and Release Process](https://www.microsoft.com/videoplayer/embed/RE4mWqP).

Las actualizaciones que Microsoft publica son acumulativas y se clasifican como actualizaciones de calidad o de características.
Para obtener más información, vea [Windows Update para empresas: actualizar tipos](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb#update-types). 

## <a name="update-groups"></a>Actualizar grupos

Microsoft Managed Desktop usa cuatro grupos de Azure AD para administrar las actualizaciones:

- **Prueba**: se usa para validar cambios en la Directiva de escritorio administrada de Microsoft, actualizaciones del sistema operativo, actualizaciones de características y otros cambios que se envían al inquilino. No debe haber ningún usuario colocados en el grupo de prueba. El grupo de prueba está exento de todos los contratos de nivel de servicio establecidos y el soporte técnico del usuario. Este grupo está disponible para su uso para validar la compatibilidad de las aplicaciones con nuevos cambios en la Directiva o en el sistema operativo.  
- **Primero**: contiene los primeros y primeros fabricantes de software que pueden estar sujetos a actualizaciones preliminares. Los dispositivos de este grupo podrían experimentar interrupciones si hay escenarios que no se trataron durante las pruebas en el anillo de prueba.
- **Rápida**: prioriza la velocidad sobre la estabilidad. Es útil para detectar problemas de calidad antes de que se ofrezcan al grupo general. Este grupo funciona como una siguiente capa de validación, pero suele ser más estable que la prueba y los primeros grupos. 
- **Amplio**: último grupo para tener actualizaciones de características y calidad disponibles. Este grupo contiene la mayoría de los usuarios en el espacio empresarial y, por lo tanto, favorecer la estabilidad sobre la velocidad en la implementación. Las pruebas de aplicaciones deben realizarse aquí porque el entorno es más estable. 

> [!NOTE]
> Si necesita mover un usuario a un grupo de actualización diferente, envíe una solicitud de soporte técnico. Consulte [compatibilidad con Microsoft Managed Desktop](support.md) para obtener más información sobre el envío de solicitudes de soporte técnico. Si mueve a un usuario usted mismo, se revertirá el movimiento.

Para obtener más información sobre las funciones y responsabilidades de estos grupos de implementación, vea [funciones y responsabilidades del escritorio administrado de Microsoft](../intro/roles-and-responsibilities.md) .

Cómo funciona la implementación de actualizaciones:
- Microsoft Managed Desktop implementa una nueva actualización de la característica o de la calidad según la programación especificada a continuación.
- Durante la implementación, los monitores de escritorio administrados por Microsoft para detectar indicios de error o interrupción (según los datos de diagnóstico y el sistema de soporte técnico del usuario). Si se detecta alguno, la implementación en todos los grupos actuales y futuros se pausa inmediatamente.
    - Ejemplo: si se detecta un problema durante la implementación de una actualización de calidad en el primer grupo, las implementaciones de actualizaciones se realizarán en primer lugar, rápido y amplio hasta que se solucione el problema.
    - Se puede informar de los problemas de compatibilidad mediante el archivado de un vale en el portal de administración de escritorio administrado de Microsoft.
- Las actualizaciones de características y calidad se pausan independientemente. La pausa está en vigor durante 35 días de forma predeterminada, pero se puede reducir o extender en función de si se corrige el problema.
- Una vez que los grupos se hayan anulado, la implementación se reanudará de acuerdo con la programación que aparece a continuación.
- Este proceso de implementación se aplica a las actualizaciones de características y calidad, aunque la escala de tiempo varía en cada caso.




<table>
    <tr><th colspan="5">Actualizar la configuración de la implementación</th></tr>
    <tr><th>Tipo de actualización</th><th>Prueba</th><th>Primero</th><th>Rápida</th><th>Amplias</th></tr>
    <tr><td>Actualizaciones de calidad para el sistema operativo</td><td>0 días</td><td>0 días</td><td>0 días</td><td>3 días</td></tr>
    <tr><td>Actualizaciones de características para el sistema operativo</td><td>0 días</td><td>30 días</td><td>60 días</td><td>90 días</td></tr>
    <tr><td>Controladores o firmware</td><td colspan="4">Sigue la programación de las actualizaciones de calidad</td></tr>
    <tr><td>Definición de antivirus</td><td colspan="4">Se actualizó con cada examen</td></tr>
    <tr><td>Aplicaciones de Microsoft 365 para empresas</td><td colspan="4"><a href="https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/m365-apps#updates-to-microsoft-365-apps">Más información</a></td></tr>
    <tr><td>Microsoft Edge</td><td colspan="4"><a href="https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/edge-browser-app#updates-to-microsoft-edge">Más información</a></td></tr>
</table>

>[!NOTE]
>Estos períodos de aplazamiento se diseñan intencionalmente para garantizar altos niveles de seguridad y rendimiento para todos los usuarios. Además, en función de los datos recopilados en todos los dispositivos de escritorio administrados por Microsoft y el ámbito y el impacto variados de las actualizaciones, Microsoft Managed Desktop reserva flexibilidad para modificar la duración de los períodos de aplazamiento anteriores para todos y cada uno de los grupos de implementación de forma ad hoc.
>
>Microsoft Managed Desktop realiza una evaluación independiente de cada lanzamiento de características de Windows para evaluar su necesidad y utilidad de sus inquilinos administrados. Por lo tanto, el escritorio administrado de Microsoft puede o no implementar todas las actualizaciones de características de Windows. 

## <a name="windows-insider-program"></a>Programa Windows Insider

El escritorio administrado de Microsoft no admite dispositivos que forman parte del programa Windows Insider. El programa Windows Insider se usa para validar el software de Windows de versión preliminar y está diseñado para dispositivos que no son de misión crítica. Aunque esta es una iniciativa importante de Microsoft, no está pensada para una implementación amplia en entornos de producción. 

Los dispositivos que se encuentren con las compilaciones de Windows Insider podrían incluirse en el grupo de pruebas y estarán exentos de actualizar los contratos de nivel de servicio y los usuarios del escritorio administrado de Microsoft.

## <a name="bandwidth-management"></a>Administración de ancho de banda

Usamos la [optimización de entrega](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization) para todas las actualizaciones del sistema operativo y del controlador. Esto minimiza el tamaño de descarga desde el servicio de Windows Update al buscar actualizaciones de elementos del mismo nivel en la red corporativa.


