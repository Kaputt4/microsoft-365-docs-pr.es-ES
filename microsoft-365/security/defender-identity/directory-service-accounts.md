---
title: Configurar la cuenta de Servicios de directorio en Microsoft Defender para identidad
description: Obtenga información sobre cómo configurar la cuenta de Servicios de directorio de Identidad de Microsoft Defender en Microsoft 365 Defender
ms.date: 08/15/2021
ms.topic: how-to
author: dcurwin
ms.author: dacurwin
ms.service: microsoft-defender-for-identity
manager: raynew
ms.openlocfilehash: 45cc01103a578f84d49bb293ff8801aae3b4c216
ms.sourcegitcommit: 251551539b1532fdac7b7e3dd2733a75c62e8a54
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/16/2021
ms.locfileid: "58360870"
---
# <a name="microsoft-defender-for-identity-directory-services-account-in-microsoft-365-defender"></a>Cuenta de Microsoft Defender para Servicios de directorio de identidad en Microsoft 365 Defender

**Se aplica a:**

- Microsoft 365 Defender
- Defender for Identity

En este artículo se explica cómo configurar la cuenta de Servicios de directorio de Identidad de [Microsoft Defender](/defender-for-identity) en [Microsoft 365 Defender](/microsoft-365/security/defender/overview-security-center).

>[!IMPORTANT]
>Como parte de la convergencia con Microsoft 365 Defender, algunas opciones y detalles han cambiado desde su ubicación en el portal de Defender for Identity. Lea los detalles siguientes para descubrir dónde encontrar las características conocidas y las nuevas.

## <a name="configure-directory-services-account"></a>Configurar la cuenta de Servicios de directorio

Para conectar el [sensor con](sensor-health.md#add-a-sensor) los dominios de Active Directory, deberá configurar cuentas de Servicios de directorio.

1. En [Microsoft 365 Defender](https://security.microsoft.com/), vaya **a Configuración** y, a continuación, **Identities**.

    ![Vaya a Configuración, a continuación, Identidades](../../media/defender-identity/settings-identities.png)

1. Seleccione **Cuentas del servicio de directorio**. Verá qué cuentas están asociadas con qué dominios.

    ![Cuentas del servicio de directorio](../../media/defender-identity/directory-service-accounts.png)

1. Si selecciona una cuenta, se abrirá un panel con la configuración de esa cuenta.

    ![Configuración de la cuenta](../../media/defender-identity/account-settings.png)

1. Para agregar una nueva cuenta de Servicios de directorio, seleccione **Crear** nueva cuenta y rellene el nombre de cuenta **,** **Dominio** y **Contraseña**. También puede elegir si es  una cuenta de servicio administrado de grupo (gMSA) y si pertenece a un **dominio de etiqueta única**.

    ![Nueva cuenta del servicio de directorio](../../media/defender-identity/new-directory-service-account.png)

1. Seleccione **Guardar**.

## <a name="see-also"></a>Vea también

- [Configuración y estado del sensor de Identidad de Microsoft Defender para](sensor-health.md)
