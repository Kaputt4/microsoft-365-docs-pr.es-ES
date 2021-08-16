---
title: Habilitar Enterprise State Roaming
description: ''
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: e2269135cc24cc63e20d0c5d768da3a7576547aa63155ead5fa7a6490738e347
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "53898676"
---
# <a name="enable-enterprise-state-roaming"></a>Habilitar Enterprise State Roaming

[Enterprise State Roaming permite](/azure/active-directory/devices/enterprise-state-roaming-overview) a los usuarios sincronizar de forma segura los datos de configuración de usuario y aplicación en la nube. Esto significa que tendrán la misma experiencia independientemente Windows dispositivo en el que inicien sesión. Por ejemplo, si reemplaza uno de sus dispositivos Escritorio administrado de Microsoft por uno nuevo, se verá y se comportará exactamente igual que el último. Enterprise La itinerancia de estado es una característica opcional para el servicio de Escritorio administrado de Microsoft que puede configurar para los usuarios y que no se incluye ni administra como parte de Escritorio administrado de Microsoft.

Para habilitar Enterprise itinerancia de estado, siga los pasos descritos en [Enable Enterprise State Roaming in Azure Active Directory](/azure/active-directory/devices/enterprise-state-roaming-enable).

>[!NOTE]
>Si habilitas la Enterprise de estado, la lista de idioma preferido sobrescribirá el idioma seleccionado durante la configuración del dispositivo. Aunque los usuarios pueden solucionar esto fácilmente, podría provocar una experiencia de localización incoherente inicialmente. Determine si Enterprise itinerancia de estado es adecuada para los usuarios antes de configurar dispositivos.

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Pasos para empezar con Escritorio administrado de Microsoft

1. [Agregar y verificar los contactos de administración en el portal de administración ](add-admin-contacts.md)
2. [Ajustar el acceso condicional](conditional-access.md)
3. [Asignar licencias](assign-licenses.md)
4. [Desplegar el portal de empresa de Intune](company-portal.md)
5. Habilitar Enterprise itinerancia de estado (este tema)
6. [Instalar dispositivos](set-up-devices.md)
7. [Prepare a los usuarios para que usen los dispositivos](get-started-devices.md)
8. [Implementar aplicaciones](deploy-apps.md)
