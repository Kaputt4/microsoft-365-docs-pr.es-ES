---
title: Configuración de la cuenta de Servicios de directorio en Microsoft Defender for Identity
description: Obtenga información sobre cómo configurar la cuenta de Microsoft Defender for Identity Directory Services en Microsoft 365 Defender
ms.date: 08/15/2021
ms.topic: how-to
author: dcurwin
ms.author: dacurwin
ms.service: microsoft-defender-for-identity
ms.custom: admindeeplinkDEFENDER
manager: raynew
ms.collection: m365-security
search.appverid: met150
ms.openlocfilehash: ea7195943dcfb24bd021930f4013263fc15e62cc
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68080467"
---
# <a name="microsoft-defender-for-identity-directory-services-account-in-microsoft-365-defender"></a>Microsoft Defender for Identity cuenta de Directory Services en Microsoft 365 Defender

**Se aplica a:**

- Microsoft 365 Defender
- Defender for Identity

En este artículo se explica cómo configurar la cuenta [de Microsoft Defender for Identity](/defender-for-identity) Directory Services en [Microsoft 365 Defender](/microsoft-365/security/defender/overview-security-center).

>[!IMPORTANT]
>Como parte de la convergencia con Microsoft 365 Defender, algunas opciones y detalles han cambiado desde su ubicación en el portal de Defender for Identity. Lea los detalles siguientes para descubrir dónde encontrar las características conocidas y nuevas.

## <a name="configure-directory-services-account"></a>Configuración de la cuenta de Servicios de directorio

Para conectar el [sensor](sensor-health.md#add-a-sensor) con los dominios de Active Directory, deberá configurar cuentas de Servicios de directorio.

1. En <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a>, vaya a **Configuración** y, a continuación, **Identidades**.

   :::image type="content" source="../../media/defender-identity/settings-identities.png" alt-text="La opción Identidades en la página Configuración" lightbox="../../media/defender-identity/settings-identities.png":::


1. Seleccione **Cuentas de servicio de directorio**. Verá qué cuentas están asociadas a qué dominios.

   :::image type="content" source="../../media/defender-identity/directory-service-accounts.png" alt-text="Elemento de menú Cuentas de servicio de directorio" lightbox="../../media/defender-identity/directory-service-accounts.png":::

1. Si selecciona una cuenta, se abrirá un panel con la configuración de esa cuenta.

   :::image type="content" source="../../media/defender-identity/account-settings.png" alt-text="Página Configuración de la cuenta" lightbox="../../media/defender-identity/account-settings.png":::

1. Para agregar una nueva cuenta de Servicios de directorio, seleccione **Crear nueva cuenta** y rellene el nombre de la **cuenta**, **el dominio** y la **contraseña**. También puede elegir si es una **cuenta de servicio administrada por grupo** (gMSA) y si pertenece a un **dominio de etiqueta única**.

   :::image type="content" source="../../media/defender-identity/new-directory-service-account.png" alt-text="La opción Crear nueva cuenta" lightbox="../../media/defender-identity/new-directory-service-account.png":::

1. Seleccione **Guardar**.

## <a name="see-also"></a>Vea también

- [Microsoft Defender for Identity estado y configuración del sensor](sensor-health.md)
