---
title: Diagrama de flujo para determinar cuándo se conserva o elimina un elemento
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Usar un diagrama de flujo para determinar el resultado cuando un elemento tenga varias directivas de retención o una etiqueta de retención y directivas de retención
ms.openlocfilehash: 4e5c1cf887144f89764e88a39ba14a95a2df576c
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "66633463"
---
# <a name="flowchart-to-determine-when-an-item-will-be-retained-or-permanently-deleted"></a>Diagrama de flujo para determinar cuándo se conservará o eliminará permanentemente un elemento

>*[Guía de licencias de Microsoft 365 para la seguridad y el cumplimiento](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

Use el siguiente diagrama de flujo para aplicar los [principios de retención](retention.md#the-principles-of-retention-or-what-takes-precedence) para un elemento y así determinar si el sistema lo conservará o lo eliminará permanentemente como resultado de una etiqueta de retención o directiva de retención.

Este flujo lógico se usa para un elemento cuando se aplica cualquiera de las condiciones siguientes:

- Se aplicó más de una directiva de retención
- Hay una etiqueta de retención y una o varias directivas de retención

Cuando un elemento está sujeto a una retención de exhibición de documentos electrónicos (o las tecnologías anteriores de suspensión legal o conservación local), siempre se conservará antes de que la decisión fluya para las directivas de retención y una etiqueta de retención.

Si alguno de los términos usados en este diagrama de flujo no le resulta familiar, consulte [Más información sobre las directivas de retención y las etiquetas de retención](retention.md).


   ![Diagrama de flujo para determinar cuándo se conservará o eliminará permanentemente un elemento.](../media/retention-flowchart.svg)

> [!NOTE]
> Es importante distinguir entre el período de retención más largo para el elemento con respecto al período más largo especificado en una etiqueta o directiva de retención. De forma similar, entre la fecha de expiración más corta para el elemento con respecto al período más corto especificado en una directiva de retención.
> 
> Para obtener más información, vea la explicación después del gráfico en la sección de [principios de retención](retention.md#the-principles-of-retention-or-what-takes-precedence).
