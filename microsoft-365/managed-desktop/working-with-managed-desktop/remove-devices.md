---
title: Quitar dispositivos
description: Quitar dispositivos de Escritorio administrado de Microsoft administración
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
ms.openlocfilehash: fa1cb7307fddd815a2a9249c5a98739d21bd2418
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2021
ms.locfileid: "59215167"
---
# <a name="remove-devices"></a>Quitar dispositivos

Puedes quitar dispositivos de Escritorio administrado de Microsoft administración mediante el portal de administración. Esta acción es permanente, pero puede volver a registrarlas con Escritorio administrado de Microsoft siguiendo los pasos [de registro](../get-started/register-devices-self.md).

Al quitar un dispositivo, se produce lo siguiente:

- Quitamos el dispositivo de Autopilot.
- Quitamos el dispositivo de todos los grupos de dispositivos "Modern Workplace".
- Quitamos el dispositivo de la hoja **Dispositivos** en el portal de administración.

Cuando quitas un dispositivo, también tienes la opción de quitarlo de Azure Active Directory (Azure AD) y Microsoft Intune.
 
> [!CAUTION]
> Quitar los objetos relacionados con un dispositivo de Azure AD y Microsoft Intune es permanente. Si quita los objetos, no podrá ver ni administrar los dispositivos desde Intune y Azure Portals. Los dispositivos no podrán acceder a los recursos corporativos de su empresa. Es posible que los datos de la empresa se eliminen de ellos si los dispositivos intentan iniciar sesión después de eliminarlos.

1. En [Microsoft Endpoint Manager](https://endpoint.microsoft.com/), seleccione **Dispositivos** en el panel de navegación izquierdo.
2. Busque la sección **Escritorio administrado de Microsoft** del menú y seleccione **Dispositivos**.
3. En el área Escritorio administrado de Microsoft de trabajo Dispositivos, seleccione los dispositivos que desea eliminar.
4. Selecciona **Acciones de dispositivo** y, a continuación, selecciona Eliminar **dispositivo** que abre un fly-in para quitar los dispositivos.
5. En el menú desplegable, revise los dispositivos seleccionados y, a continuación, seleccione **Quitar dispositivos**. Si también desea quitar los objetos de Azure AD e Intune al mismo tiempo, active la casilla. La eliminación del dispositivo puede tardar unos minutos en completarse.

> [!NOTE]
> No puedes quitar dispositivos que estén en un **estado de registro** pendiente.