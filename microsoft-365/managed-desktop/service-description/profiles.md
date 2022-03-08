---
title: Comprender los perfiles de dispositivo
description: Los distintos perfiles que los administradores pueden asignar a los dispositivos
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: tiaraquan
f1.keywords:
- NOCSH
ms.author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
manager: dougeby
ms.topic: article
audience: Admin
ms.openlocfilehash: d12a197db8dbcb6356882082c212754fef726d4e
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63320835"
---
# <a name="device-profiles"></a>Perfiles de dispositivo

Puedes pensar que los perfiles de dispositivo forman parte de una jerarquía de opciones de configuración de dispositivos.

:::image type="content" source="../../media/mmd-profile-options-heirarchy.png" alt-text="Configuraciones de dispositivos que se muestran como una pirámide. A continuación se muestra la descripción.":::

| Opciones de configuración de dispositivos | Descripción
| ----- | ----- |
| Las configuraciones | En la parte superior se encuentran sus propias configuraciones, como los detalles de red o las aplicaciones. Un dispositivo puede tener cualquier número de estas configuraciones, que microsoft Managed Desktop no administra ni bloquea. |
| Personalizaciones | El siguiente nivel superior son [personalizaciones adicionales](customizing.md). Cada dispositivo puede tener una o varias personalizaciones (o no). Las personalizaciones pueden modificar una capa de nivel inferior (perfiles de dispositivo o la configuración básica) o ser una solicitud totalmente nueva que está en capas encima de la configuración estándar. |
| Perfiles de dispositivo | Cada dispositivo de Escritorio administrado de Microsoft debe tener asignado un perfil y solo uno. Los administradores pueden seleccionar el perfil que se asigna a un dispositivo.<br><br>Puedes asignar diferentes perfiles predefinidos a dispositivos. Cada perfil está optimizado para las necesidades de tipos específicos de usuarios. Hay tres perfiles de dispositivo disponibles:<ul><li>Estándar</li><li>Datos confidenciales</li><li>Power user</li> |
| Foundation | Fundamentalmente, todos los dispositivos de Escritorio administrado de Microsoft tienen una base que incluye:<br><ul><li>Línea base de seguridad estándar</li><li>Directivas de cumplimiento</li><li>Windows de actualización</li><li>Grupos</li></ul><br>Para trabajar con Microsoft Managed Desktop, todos los dispositivos deben incluir todos estos elementos. Los administradores no pueden cambiar estos elementos. Debe enviar una solicitud a Microsoft Managed Desktop. |

## <a name="device-profile-details"></a>Detalles del perfil del dispositivo

En la tabla siguiente se resumen las opciones de configuración y sus valores predeterminados para cada configuración configurada por los perfiles de dispositivo. En segundo plano, estas opciones se configuran con OMA-URIs mediante perfiles de configuración personalizados en Microsoft Endpoint Manager.

<br>

****

| Característica | Datos confidenciales | Power User | Estándar |
| ----- | :-----: | :-----: | :-----: |
|**Bloquear el Storage**| Sí | Sí | No |
|**[Nivel de bloque de nube](/windows/client-management/mdm/policy-csp-defender#defender-cloudblocklevel)**| Alto | Alto | Alto |
|**Deshabilitar cuentas de Microsoft**| Sí | Sí | No |
|**Deshabilitar las OneDrive**| Sí | Sí | No |
|**[Cambiar a escritorio seguro para elevación](/windows/client-management/mdm/policy-csp-localpoliciessecurityoptions#localpoliciessecurityoptions-useraccountcontrol-switchtothesecuredesktopwhenpromptingforelevation)**| No | Sí | No |
|**Etiqueta de dispositivo de Microsoft Defender para endpoint**| M365Managed-SensitiveData | M365Managed-PowerUser | M365Managed-Standard |
|**¿Administrador en el dispositivo?**| No | Sí | No |
|**Perfil de Autopilot**| MMD Standard | Usuario de MMD Power | MMD Standard |
|**AppLocker**| Sí | No | No |
|**Bloquear el almacén público**| Sí | Sí | No |
|

Cada perfil de dispositivo también implica estos elementos:

- Una pertenencia dinámica Azure Active Directory grupo de dispositivos.
- Una pertenencia estática Azure Active Directory grupo de dispositivos.
- Un Microsoft Endpoint Manager de configuración.

> [!IMPORTANT]
> No modifique la pertenencia a estos grupos directamente. Use la interfaz tal como se describe en [Reasignar perfiles](../working-with-managed-desktop/change-device-profile.md).

## <a name="limitations"></a>Limitaciones

Puedes solicitar excepciones a los perfiles de dispositivo y sus detalles como lo harías con cualquier otra directiva.

Ten en cuenta que solo puedes tener uno de cada perfil de dispositivo en tu Azure Active Directory organización ("inquilino"). Por ejemplo, no puedes solicitar que el perfil de dispositivo de datos confidenciales deshabilite AppLocker solo para algunos de los usuarios. Todos los dispositivos con el perfil de dispositivo de datos confidenciales deben tener la misma configuración.

Cada dispositivo solo puede tener un perfil. Si más de un usuario usa un dispositivo determinado, todos los usuarios de ese dispositivo tendrán la misma configuración.
