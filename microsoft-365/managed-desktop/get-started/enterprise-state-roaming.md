---
title: Habilitar Enterprise State Roaming
description: En este artículo se describe cómo habilitar la itinerancia de estado de empresa
keywords: 'Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación'
ms.service: m365-md
author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: tiaraquan
manager: dougeby
ms.topic: article
---

# <a name="enable-enterprise-state-roaming"></a>Habilitar Enterprise State Roaming

[Enterprise Roaming de estado permite](/azure/active-directory/devices/enterprise-state-roaming-overview) a los usuarios sincronizar de forma segura los datos de configuración de usuario y aplicación en la nube. Esto significa que tendrán la misma experiencia independientemente Windows dispositivo en el que inicien sesión. Por ejemplo, si reemplazas uno de sus dispositivos de Escritorio administrado de Microsoft por un nuevo dispositivo, se verá y se comportará exactamente igual que el último.

Enterprise State Roaming es una característica opcional para el servicio de Escritorio administrado de Microsoft que puede configurar para los usuarios. No se incluye ni se administra como parte de Microsoft Managed Desktop.

Para habilitar Enterprise itinerancia de estado, siga los pasos [de Enable Enterprise State Roaming in Azure Active Directory](/azure/active-directory/devices/enterprise-state-roaming-enable).

>[!NOTE]
>Si habilitas la Enterprise de estado, la lista de idioma preferido sobrescribirá el idioma seleccionado durante la configuración del dispositivo. Aunque los usuarios pueden solucionar esto fácilmente, podría provocar una experiencia de localización incoherente inicialmente. Determine si Enterprise itinerancia de estado es adecuada para los usuarios antes de configurar dispositivos.

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Pasos para empezar con Microsoft Managed Desktop

1. [Agregar y verificar los contactos de administración en el portal de administrador](add-admin-contacts.md).
2. [Ajustar el acceso condicional](conditional-access.md).
3. [Asignar las licencias](assign-licenses.md).
4. [Implemente Portal de empresa de Intune](company-portal.md).
5. Habilitar Enterprise itinerancia de estado (este tema).
6. [Configurar los dispositivos](set-up-devices.md).
7. [Preparar a los usuarios para que usen los dispositivos](get-started-devices.md).
8. [Implementar las aplicaciones](deploy-apps.md).
