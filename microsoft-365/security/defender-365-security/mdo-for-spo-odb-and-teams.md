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
localization_priority: Normal
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
description: Obtenga información sobre Microsoft Defender para Office 365 para archivos en SharePoint Online, OneDrive para la Empresa y Microsoft Teams.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 80e30a52ef77dad32450bdfecc5010752b199b37
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071323"
---
# <a name="safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>Datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams en [Microsoft Defender para Office 365](whats-new-in-defender-for-office-365.md) proporciona una capa adicional de protección para los archivos que ya han sido examinados en el momento de la carga por el motor de detección de virus común en Microsoft [365](virus-detection-in-spo.md). Datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams ayuda a detectar y bloquear archivos existentes que se identifican como malintencionados en sitios de grupo y bibliotecas de documentos.

Los datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams no están habilitados de forma predeterminada. Para activarlo, vea [Activar datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md).

## <a name="how-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-works"></a>Cómo funcionan los datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams

Cuando los datos adjuntos seguros de SharePoint, OneDrive y Microsoft Teams están habilitados e identifican un archivo como malintencionado, el archivo se bloquea mediante la integración directa con los almacenes de archivos. En la siguiente imagen se muestra un ejemplo de un archivo malintencionado detectado en una biblioteca.

![Archivos en OneDrive para la Empresa con uno detectado como malintencionado](../../media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)

Aunque el archivo bloqueado todavía se muestra en la biblioteca de documentos y en aplicaciones web, móviles o de escritorio, las personas no pueden abrir, copiar, mover o compartir el archivo. Pero pueden eliminar el archivo bloqueado.

Este es un ejemplo de cómo es un archivo bloqueado en un dispositivo móvil:

![Eliminación de un archivo bloqueado de OneDrive para la Empresa desde la aplicación móvil de OneDrive](../../media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)

De forma predeterminada, los usuarios pueden descargar un archivo bloqueado. Este es el aspecto que tiene la descarga de un archivo bloqueado en un dispositivo móvil:

![Descargar un archivo bloqueado en OneDrive para la Empresa](../../media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)

Los administradores de SharePoint Online pueden impedir que los usuarios descarguen archivos malintencionados. Para obtener instrucciones, [vea Use SharePoint Online PowerShell to prevent users from downloading malicious files](turn-on-mdo-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).

Para obtener más información sobre la experiencia del usuario cuando un archivo se ha detectado como malintencionado, vea [What to do when a malicious file is found in SharePoint Online, OneDrive, or Microsoft Teams](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2).

## <a name="view-information-about-malicious-files-detected-by-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>Ver información sobre los archivos malintencionados detectados por datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams

Los archivos identificados como malintencionados por Microsoft Defender para Office 365 se mostrarán en informes de [Microsoft Defender para Office 365](view-reports-for-mdo.md) y en el Explorador (y detecciones en tiempo [real).](threat-explorer.md)

A partir de mayo de 2018, cuando Microsoft Defender para Office 365 identifica un archivo como malintencionado, el archivo también está disponible en cuarentena. Para obtener más información, vea [Use the Security & Compliance Center to manage quarantined files](manage-quarantined-messages-and-files.md#microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files).

## <a name="keep-these-points-in-mind"></a>Tenga en cuenta estos puntos

- Defender para Office 365 no examinará todos los archivos de SharePoint Online, OneDrive para la Empresa o Microsoft Teams. Esto es así por motivos de diseño. Los archivos se examinan de forma asincrónica. El proceso usa eventos de actividad de invitado y uso compartido junto con heurística inteligente y señales de amenaza para identificar archivos malintencionados.

- Asegúrese de que los sitios de SharePoint están configurados para usar la [experiencia moderna](/sharepoint/guide-to-sharepoint-modern-experience). La protección de Defender para Office 365 se aplica tanto si se usa la experiencia moderna como la vista clásica; sin embargo, los indicadores visuales de que un archivo está bloqueado solo están disponibles en la experiencia moderna.

- Datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams forma parte de la estrategia general de protección contra amenazas de su organización, que incluye protección contra correo no deseado y antimalware en Exchange Online Protection (EOP), así como vínculos seguros y datos adjuntos seguros en Microsoft Defender para Office 365. Para obtener más información, vea [Protect against threats in Office 365](protect-against-threats.md).