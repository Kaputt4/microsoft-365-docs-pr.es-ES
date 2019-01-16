---
title: Cómo se controlan las actualizaciones en el Escritorio administrado de Microsoft
description: Mantener actualizados Microsoft Managed Desktop es un equilibrio entre velocidad y estabilidad.
keywords: Servicio de escritorio administrado de Microsoft, Microsoft 365, documentación
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 01/09/2019
ms.openlocfilehash: bee6381b0f2b7b1e2d929329c3cf628ab7657678
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2019
ms.locfileid: "26871265"
---
# <a name="how-updates-are-handled-in-microsoft-managed-desktop"></a>Cómo se controlan las actualizaciones en el Escritorio administrado de Microsoft


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/update-rings); do not delete.-->

<!--Update management -->

Microsoft Managed Desktop se conecta a todos los dispositivos a una infraestructura basada en la nube moderna. Mantener Windows, Office, controladores, firmware y Microsoft Store para actualizaciones de la aplicación empresarial actualizado es un equilibrio entre velocidad y estabilidad. Suena de implementación se usarán para asegurarse de sistema operativo y las directivas se implementan de forma segura. 

## <a name="update-groups"></a>Actualizar grupos

Microsoft Managed Desktop usa cuatro grupos de Azure AD para administrar las actualizaciones:

- Prueba: Los dispositivos que no sea de producción pensados para validar los cambios antes de implementar los cambios en el resto del inquilino. Dispositivos en este anillo están fuera del ámbito de soporte técnico del usuario final documentado. 
- En primer lugar: Contiene los primeros usuarios de software, y los dispositivos pueden estar sujetos a las actualizaciones de versión preliminar.
- Fast: Da prioridad a la velocidad a través de estabilidad. Útil para detectar problemas de calidad antes de que se ofrecen al grupo amplia. 
- Amplia: Último grupo para tener característica y calidad actualizaciones disponibles. Este grupo contiene la mayoría de los usuarios en el inquilino y, por lo tanto, favorezca estabilidad sobre la velocidad de implementación.

Actualizaciones publicadas por Microsoft son acumulativas y es posible que se pueden clasificar como actualizaciones de calidad o característica. Para obtener más información, vea [Windows Update: preguntas más frecuentes sobre](https://support.microsoft.com/help/12373/windows-update-faq). 

Cómo funciona la distribución de actualización:
- Microsoft Managed Desktop implementa una nueva actualización de característica o calidad según la programación especificada debajo.
- Durante la implementación, los monitores de escritorio administrado de Microsoft signos de error o interrupción (basado en señales de telemetría y el sistema de soporte técnico del usuario final). Si se detecta alguno, de la implementación a todos los grupos actuales y futuros inmediatamente está en pausa.
    - Ejemplo: si se detecta un problema durante la implementación de una actualización de calidad para el primer grupo, a continuación, las implementaciones de actualización primero, Fast y amplia se todos los pondrá en pausa hasta que se resuelve el problema.
    - Problemas de compatibilidad se pueden informar al archivar un vale en el portal de administración de TI administrado de escritorio de Microsoft.
- Actualizaciones de característica y calidad están en pausa por separado. Pausa está en vigor para 35 días de forma predeterminada, pero puede reducirse o extendida dependiendo de si se corrigió el problema.
- Una vez que los grupos están reactivar en pausa, se reanuda la implementación según la programación que aparece a continuación.
- Este proceso de implementación se aplica a las actualizaciones de la característica y calidad, aunque la escala de tiempo varía para cada uno.

<table>
<tr><th colspan="5">Actualización de la configuración de implementación</th></tr>
<tr><th>Tipo de actualización</th><th>Prueba</th><th>Primera</th><th>Rápido</th><th>Amplia</th></tr>
<tr><td>Actualizaciones de calidad de sistema operativo</td><td>0 días</td><td>0 días</td><td>0 días</td><td>3 días</td></tr>
<tr><td>Actualizaciones de la característica de sistema operativo</td><td>0 días</td><td>30 días</td><td>60 días</td><td>90 días</td></tr>
<tr><td>Controladores/firmware</td><td colspan="4">Sigue la programación para actualizaciones de calidad</td></tr>
<tr><td>Definición del antivirus</td><td colspan="4">Se actualizó con cada examen</td></tr>
</table>

Estos períodos de aplazamiento intencionadamente están diseñados para garantizar la seguridad alta y los estándares de rendimiento para todos los usuarios. Además, en función de los datos recopilados a través de todos los dispositivos de escritorio administrado de Microsoft y en el ámbito de variables y el impacto de las actualizaciones, escritorio administrado de Microsoft se reserva flexibilidad para modificar la longitud de los períodos de aplazamiento anterior para grupos de cualquier implementación en un anuncio hoc base.

## <a name="windows-insider-program"></a>Programa de información confidencial de Windows

Escritorio administrado de Microsoft no es compatible con los dispositivos que forman parte del programa de especialista en Windows. El programa de información confidencial de Windows se usa para validar las versiones preliminares de software de Windows y está pensado para que no sean de misión críticos dispositivos. Aunque esto es una iniciativa importante de Microsoft, no está pensada para una amplia implementación de entornos de producción. 

Todos los dispositivos que se encuentra con compilaciones de información confidencial de Windows se colocarán en el grupo de prueba y no se incluye para actualización de contratos de nivel de servicio (SLA.

## <a name="bandwidth-management"></a>Administración de ancho de banda

Optimización de entrega se usa para operativas todas las actualizaciones del sistema y el controlador. Minimiza el tamaño de descarga del servicio Windows Update (WU) de forma que busquen actualizaciones de elementos del mismo nivel dentro de la red corporativa.


