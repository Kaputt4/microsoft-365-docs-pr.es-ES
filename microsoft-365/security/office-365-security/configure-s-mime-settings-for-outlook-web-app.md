---
title: 'Configurar las opciones de S/MIME: Exchange Online para Outlook en la web'
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c7dee22c-9b5b-425c-91a9-d093204ff84e
ms.collection:
- M365-security-compliance
description: Breve descripción de lo que los administradores de Exchange Online deben hacer para ver y configurar la configuración S/MIME en Outlook en la web en Exchange Online.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9acd7d4523754c1e07ece8fb0344d9f888c0ee3d
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825706"
---
# <a name="configure-smime-settings-in-exchange-online-for-outlook-on-the-web"></a>Configurar la configuración S/MIME en Exchange Online para Outlook en la web

Como administrador de Exchange Online, puede configurar Outlook en la web (anteriormente conocido como Outlook Web App) para permitir el envío y la recepción de mensajes protegidos por S/MIME. Use los cmdlets **Get-SmimeConfig** y **set-SmimeConfig** para ver y administrar esta característica en Exchange Online PowerShell. Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

Para obtener información más detallada acerca de la sintaxis y los parámetros, consulte [Get-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/get-smimeconfig) y [set-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/set-smimeconfig).

## <a name="considerations-for-new-microsoft-edge-chromium-based"></a>Consideraciones para el nuevo Microsoft Edge (con cromo)

Para usar S/MIME en Outlook en la web en el nuevo explorador Web de [Microsoft Edge](https://www.microsoft.com/windows/microsoft-edge) , usted (u otro administrador) debe establecer y configurar la Directiva de explorador Microsoft Edge llamada **ExtensionInstallForcelist** para instalar la extensión S/MIME de Microsoft en el nuevo Microsoft Edge. El valor de la Directiva es `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` . Además, tenga en cuenta que la aplicación de esta directiva requiere dispositivos Unidos a un dominio o de Azure AD, por lo que el uso de S/MIME en el nuevo explorador Microsoft Edge requiere de forma eficaz los dispositivos Unidos a un dominio o de Azure AD.

Para obtener más información sobre la directiva **ExtensionInstallForcelist** , consulte [ExtensionInstallForcelist](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#extensioninstallforcelist).

Este paso es un requisito previo para usar Microsoft Edge nuevo; no reemplaza el control S/MIME instalado por los usuarios. Se pide a los usuarios que descarguen e instalen el control S/MIME en Outlook en la web durante su primer uso de S/MIME. O bien, los usuarios pueden ir de forma proactiva a **S/MIME** en su configuración de Outlook en la web para obtener el vínculo de descarga del control.

## <a name="considerations-for-chrome"></a>Consideraciones sobre Chrome

Para usar S/MIME en Outlook en la web en el explorador web Google Chrome, usted (u otro administrador) debe establecer y configurar la Directiva de cromo denominada **ExtensionInstallForcelist** para instalar la extensión S/MIME de Microsoft en Chrome. El valor de la Directiva es `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` . Además, tenga en cuenta que la aplicación de esta directiva requiere equipos Unidos a un dominio, por lo que el uso de S/MIME en Chrome requiere equipos Unidos a un dominio de manera eficaz.

Para obtener más información sobre la directiva **ExtensionInstallForcelist** , consulte [ExtensionInstallForcelist](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist).

Este paso es un requisito previo para usar Chrome; no reemplaza el control S/MIME instalado por los usuarios. Se pide a los usuarios que descarguen e instalen el control S/MIME en Outlook en la web durante su primer uso de S/MIME. O bien, los usuarios pueden ir de forma proactiva a **S/MIME** en su configuración de Outlook en la web para obtener el vínculo de descarga del control.

## <a name="for-more-information"></a>Más información

[S/MIME para la firma y el cifrado de mensajes](s-mime-for-message-signing-and-encryption.md)
