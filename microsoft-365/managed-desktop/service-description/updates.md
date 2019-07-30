---
title: Cómo se administran las actualizaciones en el escritorio administrado por Microsoft
description: Mantener el escritorio administrado de Microsoft actualizado es un equilibrio entre velocidad y estabilidad.
keywords: Escritorio administrado de Microsoft, Microsoft 365, Service, Documentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 01/09/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 7709779c73293a4523bf3cc381d0b59f7fbca325
ms.sourcegitcommit: d137cb1bd67a79d8af84357dc156824830d35aa7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/29/2019
ms.locfileid: "35924873"
---
# <a name="how-updates-are-handled-in-microsoft-managed-desktop"></a>Cómo se administran las actualizaciones en el escritorio administrado por Microsoft


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/update-rings); do not delete.-->

<!--Update management -->

Microsoft Managed Desktop conecta todos los dispositivos con una infraestructura moderna basada en la nube. Mantener actualizados Windows, Office, drivers, firmware y actualizaciones de aplicaciones de Microsoft Store para empresas es un equilibrio entre velocidad y estabilidad. Los grupos de implementación se usarán para garantizar que el sistema operativo y las directivas se implementan de forma segura. 

Las actualizaciones que Microsoft publica son acumulativas y se clasifican como actualizaciones de calidad o de características.
Para obtener más información, vea [Windows Update para empresas: actualizar tipos](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb#update-types). 

## <a name="update-groups"></a>Actualizar grupos

Microsoft Managed Desktop usa cuatro grupos de Azure AD para administrar las actualizaciones:

- **Prueba**: se usa para validar cambios de directiva de escritorio administrada de Microsoft, actualizaciones de sistema operativo, actualizaciones de características y otros cambios que se envían al inquilino. No debe haber ningún usuario final ubicado en el grupo de prueba. El grupo de prueba está exento de los SLA establecidos y del soporte técnico del usuario final. Este grupo está disponible para su uso para validar la compatibilidad de las aplicaciones con nuevas directivas o cambios del sistema operativo.  
- **Primero**: contiene los primeros y primeros fabricantes de software que pueden estar sujetos a actualizaciones preliminares. Los dispositivos de este grupo podrían experimentar interrupciones si hay escenarios que no se trataron durante las pruebas en el anillo de prueba.
- **Rápida**: prioriza la velocidad sobre la estabilidad. Es útil para detectar problemas de calidad antes de que se ofrezcan al grupo general. Este grupo funciona como una siguiente capa de validación, pero suele ser más estable que la prueba y los primeros grupos. 
- **Amplio**: último grupo para tener actualizaciones de características y calidad disponibles. Este grupo contiene la mayoría de los usuarios en el espacio empresarial y, por lo tanto, favorecer la estabilidad sobre la velocidad en la implementación. Las pruebas de aplicaciones deben realizarse aquí porque el entorno es más estable. 

Para obtener más información sobre las funciones y responsabilidades de estos grupos de implementación, vea [funciones y responsabilidades del escritorio administrado de Microsoft](../intro/roles-and-responsibilities.md) .

Cómo funciona la implementación de actualizaciones:
- Microsoft Managed Desktop implementa una nueva actualización de la característica o de la calidad según la programación especificada a continuación.
- Durante la implementación, los monitores de escritorio administrados por Microsoft para detectar indicios de error o interrupción (en función de las señales de datos de diagnóstico y el sistema de soporte del usuario final). Si se detecta alguno, la implementación en todos los grupos actuales y futuros se pausa inmediatamente.
    - Ejemplo: si se detecta un problema durante la implementación de una actualización de calidad en el primer grupo, las implementaciones de actualizaciones se realizarán en primer lugar, rápido y amplio hasta que se solucione el problema.
    - Se puede informar de los problemas de compatibilidad mediante el archivado de un vale en el portal de administración de escritorio de Microsoft administrado.
- Las actualizaciones de características y calidad se pausan independientemente. La pausa está en vigor durante 35 días de forma predeterminada, pero se puede reducir o extender en función de si se corrige el problema.
- Una vez que los grupos se hayan anulado, la implementación se reanudará de acuerdo con la programación que aparece a continuación.
- Este proceso de implementación se aplica a las actualizaciones de características y calidad, aunque la escala de tiempo varía en cada caso.

<table>
<tr><th colspan="5">Actualizar la configuración de la implementación</th></tr>
<tr><th>Tipo de actualización</th><th>Prueba</th><th>Primero</th><th>Rápida</th><th>Amplias</th></tr>
<tr><td>Actualizaciones de calidad para el sistema operativo</td><td>0 días</td><td>0 días</td><td>0 días</td><td>3 días</td></tr>
<tr><td>Actualizaciones de características para el sistema operativo</td><td>0 días</td><td>30 días</td><td>60 días</td><td>90 días</td></tr>
<tr><td>Controladores o firmware</td><td colspan="4">Sigue la programación de las actualizaciones de calidad</td></tr>
<tr><td>Definición de antivirus</td><td colspan="4">Se actualizó con cada examen</td></tr>
</table>

>[!NOTE]
>Estos períodos de aplazamiento se diseñan intencionalmente para garantizar altos niveles de seguridad y rendimiento para todos los usuarios. Además, en función de los datos recopilados en todos los dispositivos de escritorio administrados por Microsoft y el ámbito y el impacto variados de las actualizaciones, Microsoft Managed Desktop reserva flexibilidad para modificar la duración de los períodos de aplazamiento anteriores para todos y cada uno de los grupos de implementación en un ad hoc.
>
>Microsoft Managed Desktop realiza una evaluación independiente de cada lanzamiento de características de Windows para evaluar su necesidad y utilidad de sus inquilinos administrados. Por lo tanto, el escritorio administrado de Microsoft puede o no implementar todas las actualizaciones de características de Windows. 

## <a name="windows-insider-program"></a>Programa Windows Insider

El escritorio administrado de Microsoft no admite dispositivos que forman parte del programa Windows Insider. El programa Windows Insider se usa para validar el software de Windows de versión preliminar y está diseñado para dispositivos que no son de misión crítica. Aunque esta es una iniciativa importante de Microsoft, no está pensada para una implementación amplia en entornos de producción. 

Los dispositivos que se encuentren con las compilaciones de Windows Insider podrían incluirse en el grupo de prueba y estarán exentos de la actualización de los contratos de nivel de servicio (SLA) y del usuario final desde el escritorio administrado de Microsoft.

## <a name="bandwidth-management"></a>Administración de ancho de banda

La optimización de entrega se usa para todas las actualizaciones del sistema operativo y de los controladores. Reduce el tamaño de descarga desde el servicio de Windows Update al buscar actualizaciones de elementos del mismo nivel dentro de la red corporativa.


