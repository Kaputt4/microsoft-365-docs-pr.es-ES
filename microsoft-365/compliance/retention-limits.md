---
title: Límites de Microsoft 365 relacionados con las directivas de retención y directivas de etiqueta de retención.
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- purview-compliance
- tier1
- SPO_Content
search.appverid:
- MOE150
- MET150
hideEdit: true
description: Descripción del número máximo de directivas y elementos por directiva para las directivas de retención y directivas de etiquetas de retención de Microsoft 365
ms.openlocfilehash: ca63433629740846824e22abead7e816f47fa6fd
ms.sourcegitcommit: a20d30f4e5027f90d8ea4cde95d1d5bacfdd2b5e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2022
ms.locfileid: "68770053"
---
# <a name="limits-for-retention-policies-and-retention-label-policies"></a>Límites de directivas de retención y directivas de etiqueta de retención.

>*[Instrucciones de licencias de Microsoft 365 para la seguridad y el cumplimiento](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

Al usar [directivas de retención y directivas de etiqueta de retención](retention.md#retention-policies-and-retention-labels) para conservar o eliminar automáticamente datos de su organización, debe conocer ciertos límites.

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="maximum-number-of-retention-labels-per-tenant"></a>Número máximo de etiquetas de retención por espacio empresarial

Se admite un máximo de 1 000 etiquetas de retención por espacio empresarial.

## <a name="maximum-number-of-policies-per-tenant"></a>Número máximo de directivas por espacio empresarial

Un solo espacio empresarial puede tener un máximo de 10 000 directivas (cualquier configuración). Este número máximo incluye las diferentes directivas de retención y otras directivas de cumplimiento, como directivas para DLP, barreras de información, retenciones de eDiscovery, In-Place retenciones y etiquetas de confidencialidad. Sin embargo, este máximo excluye:

- Directivas de etiquetado automático para SharePoint y OneDrive, a menos que sean para datos adjuntos de la nube.
- Directivas de etiquetas publicadas para SharePoint y OneDrive que solo eliminen, en lugar de conservar o retener y luego eliminar.
- Directivas de retención de Exchange desde [la administración de registros de mensajería (MRM)](/exchange/security-and-compliance/messaging-records-management/messaging-records-management).
- Retenciones por litigio

Dentro de este límite de 10 000 directivas, también hay algunos límites en el número máximo de directivas para la retención por carga de trabajo:

- Exchange (cualquier configuración): 1800
  - Por buzón: 25 es el máximo recomendado antes de que el rendimiento pueda verse afectado; 50 es el límite admitido.
- SharePoint o OneDrive (se incluyen automáticamente todos los sitios): 13
- SharePoint o OneDrive (ubicaciones específicas incluidas o excluidas): 2600

> [!NOTE]
> Estos números máximos para Exchange y SharePoint no son exclusivos de la retención, sino que se comparten con otros tipos de directivas de suspensión que incluyen retenciones de eDiscovery y In-Place suspensiones.

Aunque las directivas de retención para Microsoft Teams y Yammer usan buzones para almacenar datos con fines de retención, el número máximo de directivas para Exchange Online excluye las directivas de retención para Teams y Yammer.

## <a name="maximums-for-adaptive-policy-scopes"></a>Valores máximos para ámbitos de directivas adaptables

No existe un límite en el número de [ámbitos de directivas adaptables](retention.md#adaptive-or-static-policy-scopes-for-retention) que puede agregar a una directiva de retención, pero existen algunos límites máximos para la consulta que define cada ámbito adaptable:

- Longitud de cadena para valores de atributo o propiedad: 200
- Número de atributos o propiedades sin grupo o dentro de un grupo: 10
- Número de grupos: 10
- Número de caracteres en una consulta avanzada: 10 000

No se admite la agrupación de atributos o propiedades dentro de un grupo. Por tanto, el número máximo de propiedades o atributos que se admiten en un único ámbito adaptable es 100.

## <a name="maximum-number-of-items-per-policy"></a>Número máximo de elementos por directiva

> [!IMPORTANT]
> Solo se aplica si usa [ámbitos estáticos de directiva en lugar de ámbitos adaptables](retention.md#adaptive-or-static-policy-scopes-for-retention).

Si usa ámbitos estáticos y la configuración opcional para incluir o excluir usuarios específicos, grupos específicos de Microsoft 365 o sitios específicos, hay algunos límites por directiva que debe tener en cuenta.

Número máximo de elementos por directiva para la retención de ámbitos estáticos:

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

Sin embargo, cuantas más directivas, mayor es la sobrecarga administrativa. Considere utilizar ámbitos adaptables en lugar de crear y mantener varias directivas con inclusiones y exclusiones.

### <a name="examples-of-using-multiple-policies-to-avoid-exceeding-maximum-numbers"></a>Ejemplos de uso de varias directivas para evitar superar los límites máximos

Los ejemplos siguientes refieren a ámbitos estáticos y proporcionan algunas soluciones de diseño para cuando no pueda especificar solo la ubicación de una directiva de retención y deba tener en cuenta el máximo número de elementos documentados en la sección anterior.

Ejemplo de Exchange:

- **Requisito**: en una organización con más de 40 000 buzones de usuario, la mayoría de los usuarios debe conservar su correo electrónico durante siete años, pero un subconjunto de usuarios identificados (425) debe conservar su correo electrónico solo durante 5 años.

- **Solución**: cree una directiva de retención para el correo electrónico de Exchange con un período de retención de 7 años y excluya el subconjunto de usuarios. Luego, cree una segunda directiva de retención para el correo electrónico de Exchange con un período de retención de 5 años e incluya el subconjunto de usuarios.

    In both cases, the number included and excluded is below the maximum number of specified mailboxes for a single policy, and the subset of users must be explicitly excluded from the first policy because it has a [longer retention period](retention.md#the-principles-of-retention-or-what-takes-precedence) than the second policy. If the subset of users required a longer retention policy, you wouldn't need to exclude them from the first policy.

    Con esta solución, si alguien nuevo se une a la organización, su buzón se incluirá automáticamente en la primera directiva durante 7 años y no hay ningún impacto en el número máximo de admitidos. Pero los nuevos usuarios que requieran el período de retención de 5 años se agregarán a los números de inclusiones y exclusiones, cuyo límite es 1000.

Ejemplo de SharePoint:

- **Requisito**: una organización tiene varios miles de sitios de SharePoint, pero solo 2000 sitios requieren un período de retención de 10 años, y 8000 requieren un período de retención de 4 años.

- **Solución**: cree 20 directivas de retención para SharePoint con un período de retención de 10 años que incluya 100 sitios específicos y cree 80 directivas de retención para SharePoint con un período de retención de 4 años que incluya 100 sitios específicos.

    Como es necesario retener todos los sitios de SharePoint, debe crear directivas de retención que especifiquen los sitios específicos. Como una directiva de retención no admite más de 100 sitios específicos, debe crear varias directivas para los dos períodos de retención. Estas directivas de retención tienen el número máximo de sitios incluidos, por lo que el siguiente sitio nuevo que necesita retenerse requerirá una nueva directiva de retención, independientemente del periodo de retención.

## <a name="maximum-numbers-for-disposition"></a>Número máximo de eliminación

Para la [eliminación del contenido](disposition.md), hay algunos límites que deben tenerse en cuenta:

- Número máximo por inquilino:
  - 16 000 000 elementos en cualquiera de los siguientes estados de revisión para eliminación: disposición pendiente o disposición aprobada
  - 16 000 000 elementos marcados como registros eliminados automáticamente (sin revisión para eliminación)

- Números máximos para cada etiqueta de retención:
  - 1 000 000 elementos pendientes de eliminación por fase para cada etiqueta de retención
  - Prueba de eliminación hasta siete años después de eliminar el elemento, con un límite de 1 000 000 de elementos por etiqueta de retención para ese período.

    Si necesita una prueba de eliminación superior a ese límite de 1 000 000 para los elementos que se marcan como registros, póngase en contacto con el [Soporte técnico de Microsoft](../admin/get-help-support.md).

- Número máximo de revisores de eliminación:
    - 10 revisores por fase de eliminación en cualquier combinación de usuarios individuales y grupos de seguridad habilitados para correo
    - 200 revisores por inquilino en cualquier combinación de usuarios individuales y grupos de seguridad habilitados para correo. Debido a este límite, se recomienda usar grupos de seguridad habilitados para correo siempre que sea posible para organizaciones más grandes.

