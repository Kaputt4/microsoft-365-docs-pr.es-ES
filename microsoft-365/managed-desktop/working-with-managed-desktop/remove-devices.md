---
title: Quitar dispositivos
description: Quitar dispositivos de la administración de Escritorio administrado de Microsoft
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
ms.openlocfilehash: c4be03b7ba86449a875e268adbbdfbf1d4625aab
ms.sourcegitcommit: af73b93a904ce8604be319e8dc7cadaf65d50534
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/31/2022
ms.locfileid: "62281404"
---
# <a name="remove-devices"></a>Quitar dispositivos

Puede quitar dispositivos de la administración de Escritorio administrado de Microsoft mediante el portal de administración. Esta acción es permanente, pero puede registrarlas de nuevo en Microsoft Managed Desktop siguiendo los pasos [de registro](../get-started/register-devices-self.md).

Al quitar un dispositivo, se produce lo siguiente:

- Quitamos el dispositivo de Autopilot.
- Quitamos el dispositivo de todos los grupos de dispositivos "Modern Workplace".
- Quitamos el dispositivo de la hoja **Dispositivos** en el portal de administración.

Cuando quitas un dispositivo, también puedes quitarlo de Azure Active Directory (Azure AD) y Microsoft Intune.
  
> [!CAUTION]
> Quitar los objetos relacionados con un dispositivo de Azure AD y Microsoft Intune es permanente. Si quita los objetos, no podrá ver ni administrar los dispositivos desde Intune y Azure Portals. Los dispositivos no podrán acceder a los recursos corporativos de su empresa. Es posible que los datos de la empresa se eliminen de ellos si los dispositivos intentan iniciar sesión después de eliminarlos.

**Para quitar un dispositivo:**

1. En [Microsoft Endpoint Manager](https://endpoint.microsoft.com/), seleccione **Dispositivos** en el panel de navegación izquierdo.
2. En la **sección Escritorio administrado de Microsoft** , seleccione **Dispositivos**.
3. En el área **de trabajo Dispositivos de escritorio administrados de Microsoft**, seleccione los dispositivos que desea eliminar.
4. Selecciona **Acciones de dispositivo** y, a continuación, **selecciona Eliminar dispositivo** que abre un fly-in para quitar los dispositivos.
5. En el fly-in, revisa los dispositivos seleccionados y, a continuación, selecciona **Quitar dispositivos**. Si también quieres quitar los objetos Azure AD Intune al mismo tiempo, selecciona la casilla. La eliminación del dispositivo puede tardar unos minutos en completarse.

> [!NOTE]
> No puedes quitar dispositivos que estén en un **estado de registro** pendiente.
