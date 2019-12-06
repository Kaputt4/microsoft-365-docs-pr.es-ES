---
title: Configurar la configuración S/MIME en Exchange Online para Outlook en la web
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c7dee22c-9b5b-425c-91a9-d093204ff84e
ms.collection:
- M365-security-compliance
description: Breve descripción de lo que los administradores de Exchange Online deben hacer para ver y configurar la configuración S/MIME en Outlook en la web en Exchange Online.
ms.openlocfilehash: 759e48544e9c9dedca15500edb56e9111987bf93
ms.sourcegitcommit: ba223b4fd069fc6fd09c2a2e34c770a18bc7b2a2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2019
ms.locfileid: "39866342"
---
# <a name="configure-smime-settings-in-exchange-online-for-outlook-on-the-web"></a>Configurar la configuración S/MIME en Exchange Online para Outlook en la web

Como administrador de Exchange Online, puede configurar Outlook en la web (anteriormente conocido como Outlook Web App) para permitir el envío y la recepción de mensajes protegidos por S/MIME. Use los cmdlets **Get-SmimeConfig** y **set-SmimeConfig** para ver y administrar esta característica en Exchange Online PowerShell. Para conectarse al PowerShell de Exchange Online, consulte [Conectarse al PowerShell de Exchange Online](https://go.microsoft.com/fwlink/p/?linkid=396554).

Para obtener información más detallada acerca de la sintaxis y los parámetros, consulte [Get-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/get-smimeconfig) y [set-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/set-smimeconfig).

## <a name="considerations-for-chrome"></a>Consideraciones sobre Chrome

Para usar S/MIME en Outlook en la web en el explorador web Google Chrome, usted (u otro administrador) debe establecer y configurar la Directiva de cromo denominada **ExtensionInstallForcelist** para instalar la extensión S/MIME de Microsoft en Chrome. El valor de la `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`Directiva es. Además, tenga en cuenta que la aplicación de esta directiva requiere equipos Unidos a un dominio, por lo que el uso de S/MIME en Chrome requiere equipos Unidos a un dominio de manera eficaz.

Para obtener más información sobre la directiva **ExtensionInstallForcelist** , consulte [ExtensionInstallForcelist](https://dev.chromium.org/administrators/policy-list-3#ExtensionInstallForcelist).

Este paso es un requisito previo para usar Chrome; no reemplaza el control S/MIME instalado por los usuarios. Se pide a los usuarios que descarguen e instalen el control S/MIME en Outlook en la web durante su primer uso de S/MIME. O bien, los usuarios pueden ir de forma proactiva a **S/MIME** en su configuración de Outlook en la web para obtener el vínculo de descarga del control.

## <a name="for-more-information"></a>Más información

[S/MIME para la firma y el cifrado de mensajes](s-mime-for-message-signing-and-encryption.md)
