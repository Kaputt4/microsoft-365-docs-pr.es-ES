---
title: Obtener información sobre la directiva de prevención de pérdida de datos predeterminada en Microsoft Teams (versión preliminar)
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
ms.custom: admindeeplinkCOMPLIANCE
search.appverid:
- MET150
description: Obtenga información sobre la directiva de prevención de pérdida de datos predeterminada en Microsoft Teams
ms.openlocfilehash: 61443cdfdc116e9c25d9dad24c968876ae5d0349
ms.sourcegitcommit: db2ed146b46ade9ea62eed9cb8efff5fea7a35e6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2022
ms.locfileid: "64481372"
---
# <a name="learn-about-the-default-data-loss-prevention-policy-in-microsoft-teams-preview"></a>Obtener información sobre la directiva de prevención de pérdida de datos predeterminada en Microsoft Teams (versión preliminar)

[Las capacidades de prevención](dlp-learn-about-dlp.md) de pérdida de datos se han ampliado para incluir Microsoft Teams chat y mensajes de canal, incluidos los mensajes de canal privado. Como parte de esta versión, creamos una directiva DLP predeterminada para Microsoft Teams clientes por primera vez en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Centro de cumplimiento de Microsoft 365</a>.

## <a name="licensing"></a>Licencias

Para obtener información completa sobre las licencias de DLP en Microsoft Teams, vea [Information Protection: Data Loss Prevention for Teams](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection-data-loss-prevention-for-teams).

## <a name="what-does-the-default-policy-do"></a>¿Qué hace la directiva predeterminada?

La directiva DLP predeterminada para Teams realiza un seguimiento de todos los números de tarjeta de crédito compartidos interna y externamente en la organización. Esta directiva está predeterminada para todos los usuarios del espacio empresarial. No genera ninguna sugerencia de directiva para los usuarios finales, pero genera un evento Alert y también desencadena un correo electrónico de baja gravedad para el administrador (agregado en la directiva). El administrador puede ver las actividades y editar los detalles de las directivas iniciando sesión en el Centro de cumplimiento.

Los administradores pueden ver esta directiva en la página [Directivas de prevención](https://compliance.microsoft.com/compliancesettings) > centro de cumplimiento.


> [!div class="mx-imgBorder"]
> ![directiva Teams DLP predeterminada.](../media/default-teams-dlp-policy.png)

## <a name="edit-or-delete-the-default-policy"></a>Editar o eliminar la directiva predeterminada

Para [editar la directiva predeterminada para un mejor rendimiento o eliminarla](create-test-tune-dlp-policy.md#tune-a-dlp-policy), solo tiene que usar una cuenta con permisos de **administración de cumplimiento DLP** . Para obtener más información, vea [Permissions](create-test-tune-dlp-policy.md#permissions).

