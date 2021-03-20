---
title: 'Configuración de S/MIME: Exchange Online para Outlook en la web'
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c7dee22c-9b5b-425c-91a9-d093204ff84e
ms.collection:
- M365-security-compliance
description: Breve descripción de lo que deben hacer los administradores de Exchange Online para ver y configurar la configuración de S/MIME en Outlook en la web en Exchange Online.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6ab1aaabf0e7651a5a84642c178c28961430eea0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50906485"
---
# <a name="configure-smime-settings-in-exchange-online-for-outlook-on-the-web"></a>Configurar la configuración de S/MIME en Exchange Online para Outlook en la web

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Como administrador de Exchange Online, puede configurar Outlook en la web (anteriormente conocido como Outlook Web App) para permitir el envío y recepción de mensajes protegidos por S/MIME. Use los cmdlets **Get-SmimeConfig** y **Set-SmimeConfig** para ver y administrar esta característica en PowerShell de Exchange Online. Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

Para obtener información detallada acerca de la sintaxis y los parámetros, [vea Get-SmimeConfig](/powershell/module/exchange/get-smimeconfig) y [Set-SmimeConfig](/powershell/module/exchange/set-smimeconfig).

## <a name="considerations-for-new-microsoft-edge-chromium-based"></a>Consideraciones para el nuevo Microsoft Edge (basado en Chromium)

Para usar S/MIME en Outlook en la web en el nuevo explorador web [de Microsoft Edge,](https://www.microsoft.com/windows/microsoft-edge) usted (u otro administrador) debe establecer y configurar la directiva de explorador de Microsoft Edge denominada **ExtensionInstallForcelist** para instalar la extensión Microsoft S/MIME en el nuevo Microsoft Edge. El valor de la directiva es `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` . Y tenga en cuenta que la aplicación de esta directiva requiere dispositivos unidos a un dominio o unidos a Azure AD, por lo que el uso de S/MIME en el nuevo explorador de Microsoft Edge requiere dispositivos unidos a un dominio o unidos a Azure AD.

Para obtener más información **acerca de la directiva ExtensionInstallForcelist,** vea [ExtensionInstallForcelist](/DeployEdge/microsoft-edge-policies#extensioninstallforcelist).

Este paso es un requisito previo para usar nuevo Microsoft Edge; no reemplaza el control S/MIME instalado por los usuarios. Se pide a los usuarios que descarguen e instalen el control S/MIME en Outlook en la web durante el primer uso de S/MIME. O bien, los usuarios pueden ir proactivamente a **S/MIME** en su configuración de Outlook en la web para obtener el vínculo de descarga del control.

## <a name="considerations-for-chrome"></a>Consideraciones para Chrome

Para usar S/MIME en Outlook en la web en el explorador web de Google Chrome, usted (u otro administrador) debe establecer y configurar la directiva Chromium denominada **ExtensionInstallForcelist** para instalar la extensión Microsoft S/MIME en Chrome. El valor de la directiva es `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` . Y tenga en cuenta que la aplicación de esta directiva requiere equipos unidos a un dominio, por lo que el uso de S/MIME en Chrome requiere equipos unidos a un dominio.

Para obtener más información **acerca de la directiva ExtensionInstallForcelist,** vea [ExtensionInstallForcelist](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist).

Este paso es un requisito previo para usar Chrome; no reemplaza el control S/MIME instalado por los usuarios. Se pide a los usuarios que descarguen e instalen el control S/MIME en Outlook en la web durante el primer uso de S/MIME. O bien, los usuarios pueden ir proactivamente a **S/MIME** en su configuración de Outlook en la web para obtener el vínculo de descarga del control.

## <a name="for-more-information"></a>Más información

[S/MIME para la firma y el cifrado de mensajes](s-mime-for-message-signing-and-encryption.md)