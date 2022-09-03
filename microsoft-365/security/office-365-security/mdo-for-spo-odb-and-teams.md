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
description: Obtenga información sobre Microsoft Defender para Office 365 de archivos en SharePoint Online, OneDrive para la Empresa y Microsoft Teams.
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: 6767abfc3c658675484c05d506ee69ca9d198539
ms.sourcegitcommit: 2b89bcff547e00be3d38dc8d1e6cbcf8f41eba42
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2022
ms.locfileid: "67597512"
---
# <a name="safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>Datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a**
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams en [Microsoft Defender para Office 365](whats-new-in-defender-for-office-365.md) proporciona una capa adicional de protección para los archivos que el [motor de detección de virus común de Microsoft 365](virus-detection-in-spo.md) ya ha examinado de forma asincrónica. Los datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams ayudan a detectar y bloquear los archivos existentes que se identifican como malintencionados en sitios de equipo y bibliotecas de documentos.

Los datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams no están habilitados de forma predeterminada. Para activarlo, consulte [Activar datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md).

## <a name="how-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-works"></a>Funcionamiento de los datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams

Cuando los datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams están habilitados e identifica un archivo como malintencionado, el archivo se bloquea mediante la integración directa con los almacenes de archivos. La imagen siguiente muestra un ejemplo de un archivo malintencionado detectado en una biblioteca.

:::image type="content" source="../../media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png" alt-text="Los archivos de OneDrive para la Empresa con uno detectado como malintencionado" lightbox="../../media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png":::

Aunque el archivo bloqueado sigue apareciendo en la biblioteca de documentos y en aplicaciones web, móviles o de escritorio, los usuarios no pueden abrir, copiar, mover ni compartir el archivo. Pero pueden eliminar el archivo bloqueado.

Este es un ejemplo del aspecto de un archivo bloqueado en un dispositivo móvil:

:::image type="content" source="../../media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png" alt-text="La opción para eliminar un archivo bloqueado de OneDrive para la Empresa desde la aplicación móvil de OneDrive" lightbox="../../media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png":::

De forma predeterminada, los usuarios pueden descargar un archivo bloqueado. Este es el aspecto que tiene la descarga de un archivo bloqueado en un dispositivo móvil:

:::image type="content" source="../../media/be288a82-bdd8-4371-93d8-1783db3b61bc.png" alt-text="La opción para descargar un archivo bloqueado en OneDrive para la Empresa" lightbox="../../media/be288a82-bdd8-4371-93d8-1783db3b61bc.png":::

Los administradores de SharePoint Online pueden impedir que las personas descarguen archivos malintencionados. Para obtener instrucciones, consulte [Uso de PowerShell de SharePoint Online para evitar que los usuarios descarguen archivos malintencionados](turn-on-mdo-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).

Para obtener más información sobre la experiencia del usuario cuando se ha detectado un archivo como malintencionado, consulte [Qué hacer cuando se encuentra un archivo malintencionado en SharePoint Online, OneDrive o Microsoft Teams](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2).

## <a name="view-information-about-malicious-files-detected-by-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>Ver información sobre archivos malintencionados detectados por datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams

Los archivos identificados como malintencionados por datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams se mostrarán en [informes para Microsoft Defender para Office 365](view-reports-for-mdo.md) y en [el Explorador (y detecciones en tiempo real).](threat-explorer.md)

Cuando un archivo se identifica como malintencionado por datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams, el archivo también está disponible en cuarentena, pero solo para los administradores. Para obtener más información, consulte [Administración de archivos en cuarentena en Defender para Office 365](manage-quarantined-messages-and-files.md#use-the-microsoft-365-defender-portal-to-manage-quarantined-files-in-defender-for-office-365).

## <a name="keep-these-points-in-mind"></a>Tenga en cuenta estos puntos

- Defender para Office 365 no examinará todos los archivos de SharePoint Online, OneDrive para la Empresa o Microsoft Teams. Esto es así por motivos de diseño. Los archivos se examinan de forma asincrónica. El proceso usa eventos de actividad de invitado y uso compartido junto con señales de heurística y amenazas inteligentes para identificar archivos malintencionados.

- Asegúrese de que los sitios de SharePoint están configurados para usar la [experiencia moderna](/sharepoint/guide-to-sharepoint-modern-experience). Defender para Office 365 protección se aplica si se usa la experiencia moderna o la vista clásica; sin embargo, los indicadores visuales que bloquean un archivo solo están disponibles en la experiencia moderna.

- Datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams forma parte de la estrategia general de protección contra amenazas de su organización, que incluye protección contra correo no deseado y antimalware en Exchange Online Protection (EOP), así como vínculos seguros y datos adjuntos seguros en Microsoft Defender para Office 365. Para más información, consulte [Protección contra amenazas en Office 365](protect-against-threats.md).
