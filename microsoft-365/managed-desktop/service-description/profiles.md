---
title: Comprender los perfiles de dispositivo
description: Los distintos perfiles que los administradores pueden asignar a los dispositivos
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 353bda15ee1eb5f50cf5814e06e4ccbb64e1b8d4
ms.sourcegitcommit: b6676f2dd7c42b0b5eb3ca2790b13e10177a5758
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/13/2022
ms.locfileid: "62009026"
---
# <a name="device-profiles"></a>Perfiles de dispositivo

Puedes asignar diferentes configuraciones predefinidas ("perfiles de dispositivo") a dispositivos, cada una optimizada para las necesidades de tipos específicos de usuarios. Hay tres perfiles de dispositivo disponibles:

- Estándar
- Datos confidenciales
- Power user

Puedes pensar que los perfiles de dispositivo forman parte de una jerarquía de opciones de configuración de dispositivos.

:::image type="content" source="../../media/mmd-profile-options-heirarchy.png" alt-text="Configuraciones de dispositivos que se muestran como una pirámide. A continuación se muestra la descripción.":::

Fundamentalmente, todos los dispositivos de Escritorio administrado de Microsoft tienen una base que incluye una línea base de seguridad estándar, directivas de cumplimiento, Windows de actualización y grupos. Para trabajar con Microsoft Managed Desktop, todos los dispositivos deben incluir todos estos elementos, que los administradores no pueden cambiar sin una solicitud a Microsoft Managed Desktop.

Los perfiles de dispositivo aparecen en el siguiente nivel superior. Cada dispositivo de Escritorio administrado de Microsoft debe tener asignado un perfil (y solo uno). Los administradores pueden elegir qué perfil se asigna a un dispositivo.

En un nivel aún superior se encuentran [personalizaciones adicionales](customizing.md). Cada dispositivo puede tener una o varias personalizaciones (o no). Pueden modificar una capa de nivel inferior (perfiles de dispositivo o la configuración básica) o ser una solicitud totalmente nueva que está en capas encima de la configuración estándar.

En la parte superior se encuentran sus propias modificaciones, como los detalles de red o las aplicaciones. Un dispositivo puede tener cualquier número de estas modificaciones, que microsoft Managed Desktop no administra ni bloquea.


## <a name="device-profile-details"></a>Detalles del perfil del dispositivo

En la tabla siguiente se resumen las opciones de configuración y sus valores predeterminados para cada configuración configurada por los perfiles de dispositivo. (En segundo plano, estas opciones se configuran con OMA-URIs mediante perfiles de configuración personalizados en Microsoft Endpoint Manager).

<br>

****

|Característica|Datos confidenciales|Power User|Estándar|
|---|:---:|:---:|:---:|
|**Bloquear Storage**|Sí|Sí|No|
|**[Nivel de bloque de nube](/windows/client-management/mdm/policy-csp-defender#defender-cloudblocklevel)**|Alto|Alto|Alto|
|**Deshabilitar cuentas de Microsoft**|Sí|Sí|No|
|**Deshabilitar las OneDrive**|Sí|Sí|No|
|**[Cambiar a escritorio seguro para elevación](/windows/client-management/mdm/policy-csp-localpoliciessecurityoptions#localpoliciessecurityoptions-useraccountcontrol-switchtothesecuredesktopwhenpromptingforelevation)**|No|Sí|No|
|**Etiqueta de dispositivo de Microsoft Defender para endpoint**|M365Managed-SensitiveData|M365Managed-PowerUser|M365Managed-Standard|
|**¿Administrador en el dispositivo?**|No|Sí|No|
|**Perfil de Autopilot**|MMD Standard|Usuario de MMD Power|MMD Standard|
|**AppLocker**|Sí|No|No|
|**Bloquear el almacén público**|Sí|Sí|No|
|

Cada perfil de dispositivo también implica estos elementos:

- Un grupo de dispositivos Azure Active Directory (AAD) de pertenencia dinámica
- Una pertenencia estática AAD grupo de dispositivos
- Un Microsoft Endpoint Manager de configuración

> [!IMPORTANT]
> No modifique la pertenencia a estos grupos directamente. Use la interfaz tal como se describe [en Reasignar perfiles](../working-with-managed-desktop/change-device-profile.md).

## <a name="limitations"></a>Limitaciones

Puedes solicitar excepciones a los perfiles de dispositivo y sus detalles como lo harías con cualquier otra directiva. Ten en cuenta que solo puedes tener uno de cada perfil de dispositivo en tu Azure Active Directory organización ("inquilino"). Por ejemplo, no puedes solicitar que el perfil de dispositivo de datos confidenciales deshabilite AppLocker solo para algunos de los usuarios. Todos los dispositivos con el perfil de datos confidenciales deben tener la misma configuración.

Cada dispositivo solo puede tener un perfil. Si más de un usuario usa un dispositivo determinado, todos los usuarios de ese dispositivo tendrán la misma configuración.
