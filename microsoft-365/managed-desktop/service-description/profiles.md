---
title: Comprender los perfiles de dispositivo
description: Los distintos perfiles que los administradores pueden asignar a los dispositivos
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: e6b0c96d4e145a2e5df7c7555e262aefe891e483
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691279"
---
# <a name="device-profiles"></a>Perfiles de dispositivo

Puedes asignar diferentes configuraciones predefinidas ("perfiles de dispositivo") a dispositivos, cada una optimizada para las necesidades de tipos específicos de usuarios. Hay tres perfiles de dispositivo disponibles:

- Estándar
- Datos confidenciales
- Power user

Puedes pensar que los perfiles de dispositivo forman parte de una jerarquía de opciones de configuración de dispositivos.

:::image type="content" source="../../media/mmd-profile-options-heirarchy.png" alt-text="Configuraciones de dispositivos que se muestran como una pirámide. Descripción siguiente":::

Fundamentalmente, cada dispositivo de Escritorio administrado de Microsoft tiene una base que incluye una línea base de seguridad estándar, directivas de cumplimiento, configuración de Windows Update y grupos. Para trabajar con Microsoft Managed Desktop, todos los dispositivos deben incluir todos estos elementos, que los administradores no pueden cambiar sin una solicitud a Microsoft Managed Desktop.

Los perfiles de dispositivo aparecen en el siguiente nivel superior. Cada dispositivo de Escritorio administrado de Microsoft debe tener asignado un perfil (y solo uno). Los administradores pueden elegir qué perfil se asigna a un dispositivo.

En un nivel aún superior se encuentran [personalizaciones adicionales](customizing.md). Cada dispositivo puede tener una o varias personalizaciones (o no). Pueden modificar una capa de nivel inferior (perfiles de dispositivo o la configuración básica) o ser una solicitud totalmente nueva que está en capas encima de la configuración estándar.

En la parte superior se encuentran sus propias modificaciones, como los detalles de red o las aplicaciones. Un dispositivo puede tener cualquier número de estas modificaciones, que microsoft Managed Desktop no administra ni bloquea.


## <a name="device-profile-details"></a>Detalles del perfil del dispositivo

En la tabla siguiente se resumen las opciones de configuración y sus valores predeterminados para cada configuración configurada por los perfiles de dispositivo. (En segundo plano, estas opciones se configuran con OMA-URIs mediante perfiles de configuración personalizados en Microsoft Endpoint Manager).

| Característica | Datos confidenciales | Power User | Estándar |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------|------------------------|-----------------------|
| **Bloquear almacenamiento externo**                                                                                                                               | Sí                       | Sí                   | No                   |
| **[Nivel de bloque de nube](https://docs.microsoft.com/graph/api/resources/intune-deviceconfig-defendercloudblockleveltype)** | Alto                      | Alto                  | Alto                 |
| **Deshabilitar cuentas de Microsoft**                                                                                                                           | Sí                       | Sí                   | No                   |
| **Deshabilitar OneDrive personal**                                                                                                                            | Sí                       | Sí                   | No                   |
| **Cambiar a escritorio seguro para elevación**                                                                                                               | No                        | Sí                   | No                   |
| **Etiqueta de dispositivo de Microsoft Defender para endpoint**                                                                                                           | M365Managed-SensitiveData | M365Managed-PowerUser | M365Managed-Standard |
| **¿Administrador en el dispositivo?**                                                                                                                                 | No                        | Sí                   | No                   |
| **Perfil de Autopilot**                                                                                                                                     | MMD Standard               | Usuario de MMD Power         | MMD Standard          |
| **AppLocker**                                                                                                                                            | Sí                       | No                    | No                   |
| **Bloquear el almacén público**                                                                                                                                   | Sí                       | Sí                   | No                   |

Cada perfil de dispositivo también implica estos elementos:

- Un grupo de dispositivos de Azure Active Directory (AAD) de pertenencia dinámica
- Un grupo de dispositivos AAD de pertenencia estática
- Perfil de configuración de Microsoft Endpoint Manager

> [!IMPORTANT]
> No modifique la pertenencia a estos grupos directamente. Use la interfaz tal como se describe [en Reasignar perfiles](../working-with-managed-desktop/change-device-profile.md).

## <a name="limitations"></a>Limitaciones

Puedes solicitar excepciones a los perfiles de dispositivo y sus detalles como lo harías con cualquier otra directiva. Tenga en cuenta que solo puede tener uno de cada perfil de dispositivo en su organización de Azure Active Directory ("inquilino"). Por ejemplo, no puedes solicitar que el perfil de dispositivo de datos confidenciales deshabilite AppLocker solo para algunos de los usuarios. Todos los dispositivos con el perfil de datos confidenciales deben tener la misma configuración.

Cada dispositivo solo puede tener un perfil. Si más de un usuario usa un dispositivo determinado, todos los usuarios de ese dispositivo tendrán la misma configuración.
