---
title: Instalar portal de empresa de Intune Microsoft Managed Desktop Devices
description: Información sobre la instalación de la aplicación del portal de empresa en dispositivos de escritorio administrados de Microsoft
keywords: Escritorio administrado de Microsoft, Microsoft 365, portal de la compañía
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 03/08/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: a9ce2b2455b6036170636ac564c450676473ac48
ms.sourcegitcommit: 427c6459614d58f6ef7c74354ae1816423e22323
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/28/2019
ms.locfileid: "35390707"
---
# <a name="install-intune-company-portal-on-microsoft-managed-desktop-devices"></a>Instalar el portal de empresa de Intune en dispositivos de escritorio administrados por Microsoft

Microsoft Managed Desktop requiere que los administradores de ti instalen el portal de empresa de Intune para sus usuarios con dispositivos de escritorio administrados por Microsoft. Estas son algunas de las ventajas de su organización:
- Los usuarios tienen un solo punto para examinar e instalar las aplicaciones disponibles. 
- Los administradores de TI pueden organizar las aplicaciones por categorías para sus usuarios.  
- Algunas aplicaciones (como Microsoft Project y Microsoft Visio) requieren que el portal de la compañía se implemente con el escritorio administrado de Microsoft.
- Los administradores de TI pueden personalizar el portal de la empresa para su organización. Esto incluye imágenes de marcas, agregación de contactos de soporte locales y mucho más. Para obtener más información, consulte [How to Configure the Microsoft Intune Company Portal App](https://docs.microsoft.com/intune/company-portal-app).   

En este tema se documenta el proceso de implementación del portal de empresa de Intune para los usuarios de escritorio administrados por Microsoft. El proceso general tiene el siguiente aspecto:
1. Comprar portal de empresa de Microsoft Store para empresas y sincronizar con Intune
2. Asignar portal de empresa a los usuarios
3. Comunicar los cambios a los usuarios

## <a name="step-1---purchase-company-portal-from-microsoft-store-for-business-and-sync-with-intune"></a>Paso 1: comprar el portal de empresa de Microsoft Store para empresas y sincronizar con Intune
Para obtener información sobre cómo comprar las aplicaciones y sincronizar con Intune, consulte [Microsoft Store for Business apps](deploy-apps.md#msfb-apps) en *deploy apps to Microsoft Managed Desktop*Devices.

En este tema se proporciona información sobre cómo: 
- Comprar portal de empresa de Microsoft Store para empresas 
- Forzar la sincronización entre Intune y Microsoft Store para empresas
- Comprobar Active Sync entre Intune y Microsoft Store para empresas 

## <a name="step-2---assign-company-portal-to-your-users"></a>Paso 2: asignar el portal de empresa a los usuarios
Envíe una solicitud de soporte técnico a las operaciones de escritorio administradas de Microsoft mediante el portal de administración de escritorio administrado de Microsoft. En la solicitud de soporte, solicite que se asigne el portal de la empresa a sus usuarios. Microsoft Managed Desktop implementará el portal de empresa en su espacio empresarial e instalará la aplicación en los dispositivos de escritorio administrados por Microsoft de su organización.

Para obtener más información sobre el envío de solicitudes de soporte con Microsoft Managed Desktop, consulte [soporte de administración para escritorio administrado de Microsoft](../working-with-managed-desktop/admin-support.md).

## <a name="step-3---communicate-change-to-your-users"></a>Paso 3: comunicar cambios a los usuarios
Como administrador de TI de su organización, es importante que los usuarios sepan cómo usar portal de empresa en su organización. Microsoft Managed Desktop recomienda:
- Pasos para instalar aplicaciones desde el portal de empresa. Para obtener más información, vea [instalar y compartir aplicaciones en el dispositivo](https://docs.microsoft.com/intune-user-help/install-apps-cpapp-windows).
- Cómo enviar solicitudes a los administradores de TI para las aplicaciones que no están disponibles actualmente.
