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
ms.openlocfilehash: 640867cb38dab650bca990fe36c0b7cea7f6a0d8
ms.sourcegitcommit: 3dc795ea862b180484f76b3eb5d046e74041252b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/10/2021
ms.locfileid: "50175732"
---
# <a name="safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>Datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams en Microsoft Defender para [Office 365](office-365-atp.md) proporciona una capa adicional de protección para los archivos que el motor de detección de virus común de [Microsoft 365](virus-detection-in-spo.md)ya ha analizado durante la carga. Datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams ayuda a detectar y bloquear archivos existentes identificados como malintencionados en sitios de grupo y bibliotecas de documentos.

Datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams no está habilitado de forma predeterminada. Para activarlo, vea [Activar datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams.](turn-on-atp-for-spo-odb-and-teams.md)

## <a name="how-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-works"></a>Cómo funcionan los datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams

Cuando se habilitan datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams e identifica un archivo como malintencionado, el archivo se bloquea mediante la integración directa con los almacenes de archivos. La siguiente imagen muestra un ejemplo de un archivo malintencionado detectado en una biblioteca.

![Archivos en OneDrive para la Empresa con uno detectado como malintencionado](../../media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)

Aunque el archivo bloqueado aún aparece en la biblioteca de documentos y en aplicaciones web, móviles o de escritorio, los usuarios no pueden abrir, copiar, mover ni compartir el archivo. Pero pueden eliminar el archivo bloqueado.

Este es un ejemplo del aspecto de un archivo bloqueado en un dispositivo móvil:

![Eliminar un archivo bloqueado de OneDrive para la Empresa desde la aplicación móvil de OneDrive](../../media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)

De forma predeterminada, los usuarios pueden descargar un archivo bloqueado. Este es el aspecto que tiene la descarga de un archivo bloqueado en un dispositivo móvil:

![Descargar un archivo bloqueado en OneDrive para la Empresa](../../media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)

Los administradores de SharePoint Online pueden impedir que los usuarios descarguen archivos malintencionados. Para obtener instrucciones, [vea Usar SharePoint Online PowerShell para evitar que los usuarios descarguen archivos malintencionados.](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files)

Para obtener más información sobre la experiencia del usuario cuando un archivo se ha detectado como malintencionado, vea Qué hacer cuando se encuentra un archivo malintencionado en [SharePoint Online, OneDrive](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)o Microsoft Teams.

## <a name="view-information-about-malicious-files-detected-by-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>Ver información sobre archivos malintencionados detectados por datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams

Los archivos identificados como malintencionados por Microsoft Defender para Office 365 se mostrarán en informes de Microsoft Defender para [Office 365](view-reports-for-atp.md) y en [el Explorador (y](threat-explorer.md)detecciones en tiempo real).

A partir de mayo de 2018, cuando Microsoft Defender para Office 365 identifica un archivo como malintencionado, el archivo también está disponible en cuarentena. Para obtener más información, vea El Centro de [seguridad & cumplimiento para administrar archivos en cuarentena.](manage-quarantined-messages-and-files.md#microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files)

## <a name="keep-these-points-in-mind"></a>Ten en cuenta estos puntos

- Defender para Office 365 no examinará todos los archivos de SharePoint Online, OneDrive para la Empresa o Microsoft Teams. Esto es así por motivos de diseño. Los archivos se examinan asincrónicamente. El proceso usa eventos de actividad de invitado y uso compartido junto con heurística inteligente y señales de amenaza para identificar archivos malintencionados.

- Asegúrese de que los sitios de SharePoint están configurados para usar la [experiencia moderna.](https://docs.microsoft.com/sharepoint/guide-to-sharepoint-modern-experience) La protección de Defender para Office 365 se aplica tanto si se usa la experiencia moderna como la vista clásica; sin embargo, los indicadores visuales de que un archivo está bloqueado solo están disponibles en la experiencia moderna.

- Datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams forma parte de la estrategia general de protección contra amenazas de su organización, que incluye protección contra correo no deseado y antimalware en Exchange Online Protection (EOP), así como vínculos seguros y datos adjuntos seguros en Microsoft Defender para Office 365. Para obtener más información, vea [Proteger contra amenazas en Office 365.](protect-against-threats.md)
