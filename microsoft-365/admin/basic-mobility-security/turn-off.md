---
title: Desactivar Movilidad y seguridad básicas
f1.keywords: NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- Tier3
- scotvorg
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
description: Quite grupos o directivas para desactivar Basic Mobility and Security.
ms.openlocfilehash: fe2e0fe8ba8a38890441316454a5b8ac4f6603ba
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "68719082"
---
# <a name="turn-off-basic-mobility-and-security"></a>Desactivar Movilidad y seguridad básicas

Para desactivar de forma eficaz La movilidad y la seguridad básicas, se quitan los grupos de personas definidos por los grupos de seguridad de las directivas de administración de dispositivos o se quitan las propias directivas.

- Quite grupos de usuarios quitando los grupos de seguridad de usuario de las directivas de dispositivo que ha creado.

- Deshabilite La movilidad y la seguridad básicas para todos quitando todas las directivas de dispositivos de movilidad y seguridad básicas.

Estas opciones quitan la aplicación básica de movilidad y seguridad para los dispositivos de la organización. Desafortunadamente, no puede simplemente "desaprovisionar" la movilidad y la seguridad básicas después de configurarla.

> [!IMPORTANT]
> Tenga en cuenta el impacto en los dispositivos de los usuarios al quitar los grupos de seguridad de usuarios de las directivas o quitar las propias directivas. Por ejemplo, es posible que se quiten los perfiles de correo electrónico y los correos electrónicos almacenados en caché, en función del dispositivo. Para obtener más información, consulte [¿Qué ocurre al eliminar una directiva o quitar un usuario de la directiva?](../../admin/basic-mobility-security/create-device-security-policies.md)

## <a name="remove-user-security-groups-from-basic-mobility-and-security-device-policies"></a>Eliminación de grupos de seguridad de usuarios de las directivas de dispositivos básicos de movilidad y seguridad

1. En el explorador, escriba: [https://compliance.microsoft.com/basicmobilityandsecurity](https://compliance.microsoft.com/basicmobilityandsecurity).

2. Seleccione una directiva de dispositivo y seleccione **Editar directiva**.

3. En la página **Implementación** , seleccione **Quitar**.

4. En **Grupos**, seleccione un grupo de seguridad.

5. Seleccione **Quitar** y seleccione **Guardar**.

## <a name="remove-basic-mobility-and-security-device-policies"></a>Eliminación de directivas de dispositivos básicos de movilidad y seguridad

1. En el explorador, escriba: [https://compliance.microsoft.com/basicmobilityandsecurity](https://compliance.microsoft.com/basicmobilityandsecurity).

2. Seleccione una directiva de dispositivo y, a continuación, seleccione **Eliminar directiva**.

3. En el cuadro de diálogo Advertencia, seleccione **Sí**.

> [!NOTE]
> Para obtener más pasos para desbloquear dispositivos si los dispositivos de la organización siguen en un estado bloqueado, consulte la entrada de blog [Eliminación de Access Control de Administración de dispositivos móviles para Office 365](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Removing-Access-Control-from-Mobile-Device-Management-for-Office/ba-p/279934).
