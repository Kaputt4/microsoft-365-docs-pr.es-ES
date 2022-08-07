---
title: Uso de Pertahanan Microsoft untuk Office 365 en SharePoint Online
description: Los pasos para asegurarse de que puede usar y obtener el valor de Pertahanan Microsoft untuk Office 365 en SharePoint Online y OneDrive Entreprise
search.product: ''
search.appverid: ''
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTBen
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: m365-guidance-templates
ms.topic: how-to
ms.technology: mdo
ms.openlocfilehash: 63b9a7b4b3e61f6c0bf8e6ce0d5c1f9bc490bbbc
ms.sourcegitcommit: cd9df1a681265905eef99c039f7036b2fa6e8b6d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2022
ms.locfileid: "67277279"
---
# <a name="use-microsoft-defender-for-office-365-with-sharepoint-online"></a>Uso de Pertahanan Microsoft untuk Office 365 con SharePoint Online

Microsoft Office SharePoint Online es una herramienta de colaboración de usuarios y almacenamiento de archivos ampliamente utilizada. Los pasos siguientes ayudan a reducir el área expuesta a ataques en SharePoint Online y ayudan a proteger esta herramienta de colaboración en su organización. Sin embargo, es importante tener en cuenta que hay un equilibrio entre la seguridad y la productividad, y no todos estos pasos pueden ser relevantes para el perfil de riesgo de la organización. Eche un vistazo, pruebe y mantenga ese equilibrio.

## <a name="what-youll-need"></a>Lo que necesitará

- Plan 1 de Microsoft Defender para Office 365
- Permisos suficientes (administrador/administrador de seguridad de SharePoint).
- Microsoft Office SharePoint Online (parte de Microsoft 365).
- De cinco a diez minutos para realizar estos pasos.

## <a name="turn-on-microsoft-defender-for-office-365-in-sharepoint-online"></a>Activar Pertahanan Microsoft untuk Office 365 en SharePoint Online
Si tiene licencia para Pertahanan Microsoft untuk Office 365 **(evaluación gratuita de 90 días disponible en aka.ms/trymdo)** puede garantizar una protección sin problemas contra malware de día cero y la hora de la protección contra clics en Microsoft Teams.

Para obtener más información, lea [Paso 1: Usar el portal de Microsoft 365 Defender para activar Datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams](/microsoft-365/security/office-365-security/turn-on-mdo-for-spo-odb-and-teams#step-1-use-the-microsoft-365-defender-portal-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams).

1.  Inicie sesión en la [página de configuración de datos adjuntos seguros del centro de seguridad](https://security.microsoft.com/safeattachmentv2).
1.  Seleccione **Configuración global**.
1.  Asegúrese de que **Activar Defender pre Office 365 para SharePoint, OneDrive y Microsoft Teams** está establecido **en Activado**.
1.  Vaya a la [página de configuración Vínculos seguros del centro de seguridad](https://security.microsoft.com/safelinksv2).
1.  Haga clic en **Guardar**.

## <a name="stop-infected-file-downloads-from-sharepoint-online"></a>Detener descargas de archivos infectados desde SharePoint Online

De forma predeterminada, los usuarios no pueden abrir, mover, copiar ni compartir archivos malintencionados detectados por datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams. Sin embargo, la opción *Descargar* sigue estando disponible y debe *deshabilitarse*. 

Para obtener más información, lea [Paso 2: (*Recomendado*) Uso de PowerShell de SharePoint Online para evitar que los usuarios descarguen archivos malintencionados](/microsoft-365/security/office-365-security/turn-on-mdo-for-spo-odb-and-teams#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).

1.  Abra y conéctese a [PowerShell de SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).
1.  Ejecute el siguiente comando: **Set-SPOTenant -DisallowInfectedFileDownload $true**.

### <a name="further-reading"></a>Lectura adicional
[Recomendaciones de directiva para proteger archivos y sitios de SharePoint](/microsoft-365/security/office-365-security/sharepoint-file-access-policies)
