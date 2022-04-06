---
title: Configurar la cuenta de Servicios de directorio en Microsoft Defender para identidad
description: Obtenga información sobre cómo configurar la cuenta de Servicios de directorio de Identidad de Microsoft Defender en Microsoft 365 Defender
ms.date: 08/15/2021
ms.topic: how-to
author: dcurwin
ms.author: dacurwin
ms.service: microsoft-defender-for-identity
ms.custom: admindeeplinkDEFENDER
manager: raynew
ms.collection: M365-security-compliance
ms.openlocfilehash: e31c226037d5d9e945350ba73e1df9abc79571e9
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2022
ms.locfileid: "64470007"
---
# <a name="microsoft-defender-for-identity-directory-services-account-in-microsoft-365-defender"></a>Cuenta de Microsoft Defender para Identity Directory Services en Microsoft 365 Defender

**Se aplica a:**

- Microsoft 365 Defender
- Defender for Identity

En este artículo se explica cómo configurar la cuenta de Servicios de directorio de [identidad de Microsoft Defender](/defender-for-identity) [en Microsoft 365 Defender](/microsoft-365/security/defender/overview-security-center).

>[!IMPORTANT]
>Como parte de la convergencia con Microsoft 365 Defender, algunas opciones y detalles han cambiado desde su ubicación en el portal de Defender for Identity. Lea los detalles siguientes para descubrir dónde encontrar las características conocidas y las nuevas.

## <a name="configure-directory-services-account"></a>Configurar la cuenta de Servicios de directorio

Para conectar el [sensor con](sensor-health.md#add-a-sensor) los dominios de Active Directory, deberá configurar cuentas de Servicios de directorio.

1. En <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a>, vaya a Configuración y, a **continuación**, **Identities**.

   :::image type="content" source="../../media/defender-identity/settings-identities.png" alt-text="La opción Identidades de la Configuración página" lightbox="../../media/defender-identity/settings-identities.png":::


1. Seleccione **Cuentas de servicio de directorio**. Verá qué cuentas están asociadas con qué dominios.

   :::image type="content" source="../../media/defender-identity/directory-service-accounts.png" alt-text="Elemento de menú Cuentas del servicio de directorio" lightbox="../../media/defender-identity/directory-service-accounts.png":::

1. Si selecciona una cuenta, se abrirá un panel con la configuración de esa cuenta.

   :::image type="content" source="../../media/defender-identity/account-settings.png" alt-text="Página Configuración de la cuenta" lightbox="../../media/defender-identity/account-settings.png":::

1. Para agregar una nueva cuenta de Servicios de directorio, seleccione **Crear** nueva cuenta y rellene el nombre de la **cuenta,** **el** dominio y la **contraseña**. También puede elegir si es una cuenta de servicio administrado de **grupo (** gMSA) y si pertenece a un **dominio de etiqueta única**.

   :::image type="content" source="../../media/defender-identity/new-directory-service-account.png" alt-text="La opción Crear nueva cuenta" lightbox="../../media/defender-identity/new-directory-service-account.png":::

1. Haga clic en **Guardar**.

## <a name="see-also"></a>Vea también

- [Configuración y estado del sensor de Identidad de Microsoft Defender para](sensor-health.md)
