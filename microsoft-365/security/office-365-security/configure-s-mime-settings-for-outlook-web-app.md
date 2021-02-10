---
title: 'Configuración de S/MIME: Exchange Online para Outlook en la Web'
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
description: Breve descripción de lo que los administradores de Exchange Online deben hacer para ver y configurar la configuración de S/MIME en Outlook en la Web en Exchange Online.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a81db5ec933f1d0d6e2944103be53c0169dde62f
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165684"
---
# <a name="configure-smime-settings-in-exchange-online-for-outlook-on-the-web"></a>Configurar las opciones de S/MIME en Exchange Online para Outlook en la Web

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Como administrador de Exchange Online, puede configurar Outlook en la Web (anteriormente conocido como Outlook Web App) para permitir el envío y recepción de mensajes protegidos por S/MIME. Use los cmdlets **Get-SmimeConfig** y **Set-SmimeConfig** para ver y administrar esta característica en Exchange Online PowerShell. Para conectarse al PowerShell de Exchange Online, consulte [Conectarse a PowerShell de Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Get-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/get-smimeconfig) y [Set-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/set-smimeconfig).

## <a name="considerations-for-new-microsoft-edge-chromium-based"></a>Consideraciones para el nuevo Microsoft Edge (basado en Chromium)

Para usar S/MIME en Outlook en la web en el nuevo explorador web [de Microsoft Edge,](https://www.microsoft.com/windows/microsoft-edge) usted (u otro administrador) debe establecer y configurar la directiva de explorador de Microsoft Edge denominada **ExtensionInstallForcelist** para instalar la extensión Microsoft S/MIME en el nuevo Microsoft Edge. El valor de directiva es `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` . Además, tenga en cuenta que la aplicación de esta directiva requiere dispositivos unidos a un dominio o unidos a Azure AD, por lo que el uso de S/MIME en el nuevo explorador Microsoft Edge requiere efectivamente dispositivos unidos a un dominio o unidos a Azure AD.

Para obtener más información **acerca de la directiva ExtensionInstallForcelist,** vea [ExtensionInstallForcelist](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#extensioninstallforcelist).

Este paso es un requisito previo para usar el nuevo Microsoft Edge; no reemplaza el control S/MIME que instalan los usuarios. Se pide a los usuarios que descarguen e instalen el control S/MIME en Outlook en la Web durante el primer uso de S/MIME. O bien, los usuarios pueden ir de forma proactiva a **S/MIME** en su configuración de Outlook en la web para obtener el vínculo de descarga para el control.

## <a name="considerations-for-chrome"></a>Consideraciones para Chrome

Para usar S/MIME en Outlook en la Web en el explorador web Google Chrome, usted (u otro administrador) debe establecer y configurar la directiva chromium denominada **ExtensionInstallForcelist** para instalar la extensión Microsoft S/MIME en Chrome. El valor de directiva es `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` . Además, tenga en cuenta que la aplicación de esta directiva requiere equipos unidos a un dominio, por lo que el uso de S/MIME en Chrome requiere equipos unidos a un dominio.

Para obtener más información **acerca de la directiva ExtensionInstallForcelist,** vea [ExtensionInstallForcelist](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist).

Este paso es un requisito previo para usar Chrome; no reemplaza el control S/MIME que instalan los usuarios. Se pide a los usuarios que descarguen e instalen el control S/MIME en Outlook en la Web durante el primer uso de S/MIME. O bien, los usuarios pueden ir de forma proactiva a **S/MIME** en su configuración de Outlook en la web para obtener el vínculo de descarga para el control.

## <a name="for-more-information"></a>Más información

[S/MIME para la firma y el cifrado de mensajes](s-mime-for-message-signing-and-encryption.md)
