---
title: ATP para SharePoint, OneDrive y Microsoft Teams
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.date: ''
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 26261670-db33-4c53-b125-af0662c34607
ms.collection:
- M365-security-compliance
- SPO_Content
- m365-initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
description: Obtenga información sobre la protección contra amenazas avanzada de Office 365 para archivos en SharePoint Online, OneDrive para la empresa y Microsoft Teams.
ms.openlocfilehash: e36efba37ae21ee1e2044d8b631cb14b17fcca55
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2020
ms.locfileid: "48411763"
---
# <a name="atp-for-sharepoint-onedrive-and-microsoft-teams"></a>ATP para SharePoint, OneDrive y Microsoft Teams

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

ATP para SharePoint, OneDrive y Microsoft Teams en [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md) proporciona una capa adicional de protección para los archivos que el [motor de detección de virus Common](virus-detection-in-spo.md)ha examinado en el momento de la carga en Microsoft 365. ATP para SharePoint, OneDrive y Microsoft Teams ayuda a detectar y bloquear los archivos existentes identificados como malintencionados en los sitios de grupo y las bibliotecas de documentos.

ATP para SharePoint, OneDrive y Microsoft Teams no está habilitada de forma predeterminada. Para activarla, consulte [Activar ATP para SharePoint, OneDrive y Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).

## <a name="how-atp-for-sharepoint-onedrive-and-microsoft-teams-works"></a>Cómo funciona ATP para SharePoint, OneDrive y Microsoft Teams

Cuando ATP para SharePoint, OneDrive y Microsoft Teams está habilitado e identifica un archivo como malintencionado, el archivo se bloquea mediante la integración directa con los almacenes de archivos. La imagen siguiente muestra un ejemplo de un archivo malintencionado detectado en una biblioteca.

![Archivos en OneDrive para la empresa con uno detectado como malintencionado](../../media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)

Aunque el archivo bloqueado todavía aparece en la biblioteca de documentos y en las aplicaciones Web, móviles o de escritorio, los usuarios no pueden abrir, copiar, mover ni compartir el archivo. Pero pueden eliminar el archivo bloqueado.

Este es un ejemplo de la apariencia de un archivo bloqueado en un dispositivo móvil:

![Eliminación de un archivo bloqueado de OneDrive para la empresa desde la aplicación móvil de OneDrive](../../media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)

De forma predeterminada, los usuarios pueden descargar un archivo bloqueado. Esto es lo que parece descargar un archivo bloqueado en un dispositivo móvil:

![Descargar un archivo bloqueado en OneDrive para la empresa](../../media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)

Los administradores de SharePoint Online pueden impedir que los usuarios descarguen archivos malintencionados. Para obtener instrucciones, vea [usar SharePoint Online PowerShell para evitar que los usuarios descarguen archivos malintencionados](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).

Para obtener más información acerca de la experiencia del usuario cuando un archivo se ha detectado como malintencionado, consulte [Qué hacer cuando se encuentra un archivo malintencionado en SharePoint Online, en OneDrive o en Microsoft Teams](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2).

## <a name="view-information-about-malicious-files-detected-by-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>Ver información sobre los archivos malintencionados detectados por ATP para SharePoint, OneDrive y Microsoft Teams

Los archivos identificados como malintencionados por ATP se mostrarán en los [informes de la protección contra amenazas avanzada de Office 365](view-reports-for-atp.md) y en [el explorador (y las detecciones en tiempo real)](threat-explorer.md).

A partir del 2018 de mayo, cuando ATP identifica un archivo como malintencionado, el archivo también está disponible en cuarentena. Para obtener más información, consulte [use the Security & Compliance Center para administrar los archivos en cuarentena](manage-quarantined-messages-and-files.md#atp-only-use-the-security--compliance-center-to-manage-quarantined-files).

## <a name="keep-these-points-in-mind"></a>Tenga en cuenta estos puntos

- ATP no examinará cada archivo único en SharePoint Online, OneDrive para la empresa o Microsoft Teams. Esto es así por motivos de diseño. Los archivos se examinan de forma asincrónica. El proceso usa eventos de actividad de uso compartido e invitado junto con heurísticas inteligentes y señales de amenazas para identificar archivos malintencionados.

- Asegúrese de que los sitios de SharePoint están configurados para usar la [experiencia moderna](https://docs.microsoft.com/sharepoint/guide-to-sharepoint-modern-experience). La protección ATP se aplica si se usa la experiencia moderna o la vista clásica; sin embargo, los indicadores visuales que un archivo está bloqueado solo están disponibles en la experiencia moderna.

- ATP para SharePoint, OneDrive y Microsoft Teams forma parte de la estrategia de protección contra amenazas global de su organización, que incluye protección contra correo electrónico no deseado y antimalware en Exchange Online Protection (EOP), así como vínculos seguros y datos adjuntos seguros en Office 365 ATP. Para obtener más información, consulte [proteger contra amenazas en Office 365](protect-against-threats.md).
