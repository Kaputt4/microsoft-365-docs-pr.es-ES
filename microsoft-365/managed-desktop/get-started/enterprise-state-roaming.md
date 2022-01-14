---
title: Habilitar Enterprise State Roaming
description: ''
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: tiaraquan
manager: dougeby
ms.topic: article
ms.openlocfilehash: 0050bd38dc62adfd36f7c7f71e47a3a72039f6b0
ms.sourcegitcommit: a6651b841f111ea2776cab88bf2c80f805fa8e09
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/13/2022
ms.locfileid: "62034718"
---
# <a name="enable-enterprise-state-roaming"></a>Habilitar Enterprise State Roaming

[Enterprise State Roaming permite](/azure/active-directory/devices/enterprise-state-roaming-overview) a los usuarios sincronizar de forma segura los datos de configuración de usuario y aplicación en la nube. Esto significa que tendrán la misma experiencia independientemente Windows dispositivo en el que inicien sesión. Por ejemplo, si reemplaza uno de sus dispositivos de Escritorio administrado de Microsoft por uno nuevo, tendrá el mismo aspecto que el último y se comportará exactamente igual que el último. Enterprise State Roaming es una característica opcional para el servicio de Escritorio administrado de Microsoft que puede configurar para los usuarios y que no se incluye ni administra como parte de Microsoft Managed Desktop.

Para habilitar Enterprise itinerancia de estado, siga los pasos descritos en [Enable Enterprise State Roaming in Azure Active Directory](/azure/active-directory/devices/enterprise-state-roaming-enable).

>[!NOTE]
>Si habilitas la Enterprise de estado, la lista de idioma preferido sobrescribirá el idioma seleccionado durante la configuración del dispositivo. Aunque los usuarios pueden solucionar esto fácilmente, podría provocar una experiencia de localización incoherente inicialmente. Determine si Enterprise itinerancia de estado es adecuada para los usuarios antes de configurar dispositivos.

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Pasos para empezar con Microsoft Managed Desktop

1. [Agregar y verificar los contactos de administración en el portal de administración ](add-admin-contacts.md)
2. [Ajustar el acceso condicional](conditional-access.md)
3. [Asignar licencias](assign-licenses.md)
4. [Desplegar el portal de empresa de Intune](company-portal.md)
5. Habilitar Enterprise itinerancia de estado (este tema)
6. [Instalar dispositivos](set-up-devices.md)
7. [Prepare a los usuarios para que usen los dispositivos](get-started-devices.md)
8. [Implementar aplicaciones](deploy-apps.md)
