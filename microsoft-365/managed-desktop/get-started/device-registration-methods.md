---
title: Métodos de registro de dispositivos en Microsoft Managed Desktop
description: Información sobre los métodos de registro de dispositivos en Microsoft Managed Desktop
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: tiaraquan
ms.author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
manager: dougeby
ms.topic: article
audience: Admin
ms.openlocfilehash: 7d0cabc0a9d11d337e5adabde568bd2a56ceca86
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63319251"
---
# <a name="device-registration-methods"></a>Métodos de registro del dispositivo

Para que Microsoft pueda administrar los dispositivos en Microsoft Managed Desktop, debes tener dispositivos registrados con el servicio.

## <a name="registration-process"></a>Proceso de registro

Microsoft Managed Desktop funciona con el servicio Windows Autopilot para el flujo de trabajo de registro de dispositivos. El registro de dispositivos correcto requiere un proceso de dos pasos:

1. La identidad de hardware única del dispositivo, conocida como hash de hardware, se captura y se carga en el servicio Autopilot.
1. El dispositivo está asociado a un Azure Active Directory de inquilino.

Lo ideal es que ambos pasos los realice el OEM, revendedor o distribuidor donde se compraron los dispositivos. Un OEM u otro proveedor de dispositivos usa el proceso de autorización de registro para realizar el registro del dispositivo en su nombre.

## <a name="registration-methods"></a>Métodos de registro

El registro también se puede realizar dentro de la organización mediante la recopilación de la identidad de hardware de dispositivos nuevos o existentes y la carga manualmente. A continuación se muestran los métodos de registro de dispositivos compatibles con Microsoft Managed Desktop:

- Registros OEM
    - [Uso del portal de partners](partner-registration.md#register-devices-using-the-partner-center)
    - [Uso de API oem](partner-registration.md#register-devices-by-using-the-oem-api)
- [Registro manual](manual-registration.md)
- [Registro manual para dispositivos existentes](manual-registration-existing-devices.md)

## <a name="recommended-resources"></a>Recursos recomendados

- [Introducción a Windows Autopilot](/mem/autopilot/windows-autopilot)
- [Windows introducción al registro de Autopilot](/mem/autopilot/registration-overview)

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Pasos para empezar con Microsoft Managed Desktop

1. Acceder al [portal de administrador](access-admin-portal.md).
1. [Agregar y verificar los contactos de administración en el portal de administrador](add-admin-contacts.md).
1. [Ajustar la configuración después de la inscripción](conditional-access.md).
1. Implementar y asignar el [Portal de empresa de Intune](company-portal.md).
1. [Asignar las licencias](assign-licenses.md).
1. [Implementar las aplicaciones](deploy-apps.md).
1. [Preparar dispositivos](prepare-devices.md).
1. Configurar la [experiencia de primera ejecución con el Autopilot y la página de estado de inscripción](esp-first-run.md).
1. [Habilitar las características de soporte técnico para el usuario](enable-support.md).
1. [Preparar a los usuarios para que usen los dispositivos](get-started-devices.md).
1. [Comenzar a usar el control de aplicaciones](get-started-app-control.md).
