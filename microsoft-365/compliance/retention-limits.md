---
title: Límites de directivas de retención y directivas de etiqueta de retención.
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
hideEdit: true
description: Obtener información sobre el número máximo de directivas y elementos por directiva para directivas de retención y directivas de etiquetas de retención
ms.openlocfilehash: 92647911cfc3435c2d88ce5caa0624a34467a60f
ms.sourcegitcommit: 3e197d1ff7d8100faeaf1f5a33f1ad4ed2f72e99
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/11/2021
ms.locfileid: "52908106"
---
# <a name="limits-for-retention-policies-and-retention-label-policies"></a>Límites de directivas de retención y directivas de etiqueta de retención.

>*[Instrucciones de licencias de Microsoft 365 para la seguridad y el cumplimiento](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

Al usar [directivas de retención y directivas de etiqueta de retención](retention.md#retention-policies-and-retention-labels) para conservar o eliminar automáticamente datos de su organización, debe conocer ciertos límites.

## <a name="maximum-number-of-policies-per-tenant"></a>Número máximo de directivas por espacio empresarial

Un solo espacio empresarial puede tener un máximo de 10 000 directivas (cualquier configuración). Este número máximo incluye las diferentes directivas de retención y otras directivas de cumplimiento como directivas para DLP, barreras de información, retenciones de eDiscovery y etiquetas de confidencialidad.

Dentro de este límite de 10 000 directivas, también hay algunos límites en el número máximo de directivas para la retención por carga de trabajo:

- Exchange (cualquier configuración): 1800
- SharePoint o OneDrive (se incluyen automáticamente todos los sitios): 13
- SharePoint o OneDrive (ubicaciones específicas incluidas o excluidas): 2600

Aunque las directivas de retención para Microsoft Teams y Yammer usan buzones para almacenar datos con fines de retención, el número máximo de directivas para Exchange Online excluye las directivas de retención para Teams y Yammer.

## <a name="maximum-number-of-items-per-policy"></a>Número máximo de elementos por directiva

Deben tenerse en cuenta ciertos límites por directiva si usa la configuración opcional para definir el ámbito de la configuración de retención para usuarios específicos, grupos específicos de Microsoft 365 o determinados sitios: 

Número máximo de elementos por directiva para la retención:

- Buzones de Exchange: 1000
- Grupos de Microsoft 365: 1000
- Mensajes de canal de Teams: 1000
- Chats de Teams: 1000
- Mensajes de la comunidad de Yammer: 1000
- Mensajes del usuario de Yammer: 1000
- Sitios de SharePoint: 100
- Cuentas de OneDrive: 100

Skype Empresarial debe limitarse a usuarios específicos y el número máximo admitido por directiva es 1000.

Estas limitaciones son por directiva, por lo que si necesita usar inclusiones o exclusiones específicas por las que se superan estos números, puede crear otras directivas de retención con la misma configuración de retención. Vea la siguiente sección con [algunos escenarios de ejemplo y soluciones](#examples-of-using-multiple-policies-to-avoid-exceeding-maximum-numbers) que usan varias directivas de retención por este motivo.

Sin embargo, tener varias directivas generan más sobrecargas administrativas, por lo que siempre debe confirmar si necesita realmente inclusiones y exclusiones. Recuerde que la configuración predeterminada que se aplica a toda la ubicación no tiene ninguna limitación y esta opción de configuración puede ser una solución mejor que la creación y el mantenimiento de varias directivas.

> [!TIP]
> Si necesita crear y mantener varias directivas para este escenario, plantéese usar [PowerShell](retention.md#powershell-cmdlets-for-retention-policies-and-retention-labels) para una configuración más eficaz.

### <a name="examples-of-using-multiple-policies-to-avoid-exceeding-maximum-numbers"></a>Ejemplos de uso de varias directivas para evitar superar los límites máximos

Los ejemplos siguientes proporcionan algunas soluciones de diseño para cuando no pueda especificar solo la ubicación de una directiva de retención y debe tener en cuenta el máximo número de elementos documentados en la sección anterior.

Ejemplo de Exchange:

- **Requisito**: en una organización con más de 40.000 buzones de usuario, la mayoría de los usuarios deben tener su correo electrónico retenido durante 7 años, pero un subconjunto de usuarios identificados (425) debe tener su correo electrónico retenido solo durante 5 años.

- **Solución**: cree una directiva de retención para el correo electrónico de Exchange con un período de retención de 7 años y excluya el subconjunto de usuarios. Luego, cree una segunda directiva de retención para el correo electrónico de Exchange con un período de retención de 5 años e incluya el subconjunto de usuarios. 
    
    En ambos casos, el número de inclusiones y exclusiones se encuentra por debajo del número máximo de buzones especificados para una sola directiva, y el subconjunto de usuarios tiene que excluirse explícitamente de la primera directiva, ya que tiene un período de retención [más largo](retention.md#the-principles-of-retention-or-what-takes-precedence) que la segunda directiva. Si el subconjunto de usuarios necesita una directiva de retención más larga, no tendrá que excluirlos de la primera directiva.
     
    Con esta solución, si alguien nuevo se une a la organización, su buzón se incluirá automáticamente en la primera directiva durante 7 años y no hay ningún impacto en el número máximo de admitidos. Pero los nuevos usuarios que requieran el período de retención de 5 años se agregarán a los números de inclusiones y exclusiones, cuyo límite es 1000.

Ejemplo de SharePoint:

- **Requisito**: una organización tiene varios miles de sitios de SharePoint, pero solo 2000 sitios requieren un período de retención de 10 años y 8000 requieren un período de retención de 4 años.

- **Solución**: cree 20 directivas de retención para SharePoint con un período de retención de 10 años que incluya 100 sitios específicos y cree 80 directivas de retención para SharePoint con un período de retención de 4 años que incluya 100 sitios específicos.
    
    Como es necesario retener todos los sitios de SharePoint, debe crear directivas de retención que especifiquen los sitios específicos. Como una directiva de retención no admite más de 100 sitios específicos, debe crear varias directivas para los dos períodos de retención. Estas directivas de retención tienen el número máximo de sitios incluidos, por lo que el siguiente sitio nuevo que necesita retenerse requerirá una nueva directiva de retención, independientemente del periodo de retención.

## <a name="maximum-number-of-items-for-disposition"></a>Número máximo de elementos para eliminar

Para la [eliminación del contenido](disposition.md), hay algunos límites que deben tenerse en cuenta:

- 1 000 000 elementos pendientes de eliminación por fase para cada etiqueta de retención

- Prueba de eliminación hasta siete años después de eliminar el elemento, con un límite de 1 000 000 de elementos por etiqueta de retención para ese período. 
    
Si necesita una prueba de eliminación superior a ese límite de 1 000 000 para los elementos que se marcan como registros, póngase en contacto con el [Soporte técnico de Microsoft](../business-video/get-help-support.md).
