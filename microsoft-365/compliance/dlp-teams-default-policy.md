---
title: Más información sobre la directiva DLP predeterminada en Microsoft Teams (versión preliminar)
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
description: Más información sobre la directiva de prevención de pérdida de datos predeterminada en Microsoft Teams
ms.openlocfilehash: 5c3a5a116da90a41abcc459808e83176dc750fe1
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "66624231"
---
# <a name="learn-about-the-default-data-loss-prevention-policy-in-microsoft-teams-preview"></a>Obtener información sobre la directiva de prevención de pérdida de datos predeterminada en Microsoft Teams (versión preliminar)

[Prevención de pérdida de datos de Microsoft Purview](dlp-learn-about-dlp.md) funcionalidades se han ampliado para incluir mensajes de chat y canales de Microsoft Teams, incluidos los mensajes de canal privado. Como parte de esta versión, creamos una directiva DLP predeterminada para Microsoft Teams para los clientes por primera vez a la <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">portal de cumplimiento Microsoft Purview</a>.

## <a name="licensing"></a>Licencias

Para obtener información completa sobre las licencias para DLP en Microsoft Teams, consulte [Information Protection: Prevención de pérdida de datos para Teams](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection-data-loss-prevention-for-teams).

## <a name="what-does-the-default-policy-do"></a>¿Qué hace la directiva predeterminada?

La directiva DLP predeterminada para Teams realiza un seguimiento de todos los números de tarjeta de crédito compartidos interna y externamente con la organización. Esta directiva está activada de forma predeterminada para todos los usuarios del inquilino. No genera ninguna sugerencia de directiva para los usuarios finales, pero genera un evento alert y también desencadena un correo electrónico de gravedad baja al administrador (agregado en la directiva). El administrador puede ver las actividades y editar los detalles de las directivas iniciando sesión en el Centro de cumplimiento.

Los administradores pueden ver esta directiva en la [página directivas de](https://compliance.microsoft.com/compliancesettings) prevención de pérdida de datos portal de cumplimiento Microsoft Purview >.


> [!div class="mx-imgBorder"]
> ![directiva DLP predeterminada de Teams.](../media/default-teams-dlp-policy.png)

## <a name="edit-or-delete-the-default-policy"></a>Editar o eliminar la directiva predeterminada

Para [editar la directiva predeterminada para mejorar el rendimiento o eliminarla](create-test-tune-dlp-policy.md#tune-a-dlp-policy), solo tiene que usar una cuenta con permisos **de administración de cumplimiento DLP** . Para obtener más información, vea [Permisos](create-test-tune-dlp-policy.md#permissions).

