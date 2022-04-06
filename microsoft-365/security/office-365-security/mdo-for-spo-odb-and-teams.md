---
title: Datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.date: ''
ms.topic: conceptual
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: 26261670-db33-4c53-b125-af0662c34607
ms.collection:
- M365-security-compliance
- SPO_Content
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
description: Obtenga información sobre Microsoft Defender para Office 365 archivos en SharePoint Online, OneDrive para la Empresa y Microsoft Teams.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 220bb976ebe701e5db5f03370a1a7c188f197cb1
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2022
ms.locfileid: "64475771"
---
# <a name="safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>Datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Caja fuerte datos adjuntos para SharePoint, OneDrive y Microsoft Teams en [Microsoft Defender para Office 365](whats-new-in-defender-for-office-365.md) proporciona una capa adicional de protección para los archivos que ya han sido examinados asincrónicamente por el motor de detección de [virus común en Microsoft 365](virus-detection-in-spo.md). Caja fuerte datos adjuntos para SharePoint, OneDrive y Microsoft Teams ayuda a detectar y bloquear archivos existentes que se identifican como malintencionados en sitios de grupo y bibliotecas de documentos.

Los datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams no están habilitados de forma predeterminada. Para activarlo, vea Activar Caja fuerte datos adjuntos para SharePoint[, OneDrive y Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md).

## <a name="how-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-works"></a>Cómo Caja fuerte datos adjuntos para SharePoint, OneDrive y Microsoft Teams funciona

Cuando Caja fuerte datos adjuntos de SharePoint, OneDrive y Microsoft Teams está habilitado e identifica un archivo como malintencionado, el archivo se bloquea mediante la integración directa con los almacenes de archivos. La imagen siguiente muestra un ejemplo de un archivo malintencionado detectado en una biblioteca.

:::image type="content" source="../../media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png" alt-text="Los archivos de OneDrive para la Empresa con uno detectado como malintencionado" lightbox="../../media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png":::

Aunque el archivo bloqueado sigue apareciendo en la biblioteca de documentos y en aplicaciones web, móviles o de escritorio, los usuarios no pueden abrir, copiar, mover ni compartir el archivo. Pero pueden eliminar el archivo bloqueado.

Este es un ejemplo del aspecto de un archivo bloqueado en un dispositivo móvil:

:::image type="content" source="../../media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png" alt-text="La opción para eliminar un archivo bloqueado de OneDrive para la Empresa de la aplicación OneDrive móvil" lightbox="../../media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png":::

De forma predeterminada, los usuarios pueden descargar un archivo bloqueado. Este es el aspecto que tiene la descarga de un archivo bloqueado en un dispositivo móvil:

:::image type="content" source="../../media/be288a82-bdd8-4371-93d8-1783db3b61bc.png" alt-text="La opción para descargar un archivo bloqueado en OneDrive para la Empresa" lightbox="../../media/be288a82-bdd8-4371-93d8-1783db3b61bc.png":::

SharePoint los administradores en línea pueden impedir que los usuarios descarguen archivos malintencionados. Para obtener instrucciones, vea [Use SharePoint Online PowerShell to prevent users from downloading malicious files](turn-on-mdo-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).

Para obtener más información acerca de la experiencia del usuario cuando un archivo se ha detectado como malintencionado, vea What [to do when a malicious file is found in SharePoint Online, OneDrive, or Microsoft Teams](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2).

## <a name="view-information-about-malicious-files-detected-by-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>Ver información sobre los archivos malintencionados detectados por Caja fuerte datos adjuntos para SharePoint, OneDrive y Microsoft Teams

Los archivos identificados como malintencionados por Caja fuerte Attachments for SharePoint, OneDrive y Microsoft Teams aparecerán en informes de [Microsoft Defender para Office 365](view-reports-for-mdo.md) y en el Explorador (y detecciones en tiempo [real).](threat-explorer.md).

Cuando un archivo se identifica como malintencionado por Caja fuerte Attachments for SharePoint, OneDrive y Microsoft Teams, el archivo también está disponible en cuarentena, pero solo para los administradores. Para obtener más información, vea [Manage quarantined files in Defender for Office 365](manage-quarantined-messages-and-files.md#use-the-microsoft-365-defender-portal-to-manage-quarantined-files-in-defender-for-office-365).

## <a name="keep-these-points-in-mind"></a>Tenga en cuenta estos puntos

- Defender para Office 365 examinará todos los archivos de SharePoint Online, OneDrive para la Empresa o Microsoft Teams. Esto es así por motivos de diseño. Los archivos se examinan de forma asincrónica. El proceso usa eventos de actividad de invitado y uso compartido junto con heurística inteligente y señales de amenaza para identificar archivos malintencionados.

- Asegúrese de que los SharePoint están configurados para usar la [experiencia moderna](/sharepoint/guide-to-sharepoint-modern-experience). Defender for Office 365 protection se aplica si se usa la experiencia moderna o la vista clásica; sin embargo, los indicadores visuales de que un archivo está bloqueado solo están disponibles en la experiencia moderna.

- Caja fuerte Datos adjuntos de SharePoint, OneDrive y Microsoft Teams forma parte de la estrategia general de protección contra amenazas de su organización, que incluye protección contra correo no deseado y antimalware en Exchange Online Protection (EOP), así como Caja fuerte  Vínculos y Caja fuerte datos adjuntos en Microsoft Defender para Office 365. Para obtener más información, consulte [Protect against threats in Office 365](protect-against-threats.md).
