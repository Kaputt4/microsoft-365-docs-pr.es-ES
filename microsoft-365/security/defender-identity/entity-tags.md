---
title: Etiquetas de entidad de Microsoft Defender para identity en Microsoft 365 Defender
description: Obtenga información sobre cómo aplicar etiquetas de entidad de Microsoft Defender para identidad en Microsoft 365 Defender
ms.date: 06/08/2021
ms.topic: how-to
author: dcurwin
ms.author: dacurwin
ms.service: microsoft-defender-for-identity
ms.custom: admindeeplinkDEFENDER
manager: raynew
ms.collection: M365-security-compliance
ms.openlocfilehash: c960f0cc1726155e733a0e88386fa7788cfc35e0
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2022
ms.locfileid: "64468069"
---
# <a name="defender-for-identity-entity-tags-in-microsoft-365-defender"></a>Etiquetas de entidad Defender for Identity en Microsoft 365 Defender

**Se aplica a:**

- Microsoft 365 Defender
- Defender for Identity

En este artículo se explica cómo aplicar [etiquetas de entidad de Microsoft Defender para identidad](/defender-for-identity) en [Microsoft 365 Defender](/microsoft-365/security/defender/overview-security-center).

>[!IMPORTANT]
>Como parte de la convergencia con Microsoft 365 Defender, algunas opciones y detalles han cambiado desde su ubicación en el portal de Defender for Identity. Lea los detalles siguientes para descubrir dónde encontrar las características conocidas y las nuevas.

## <a name="entity-tags"></a>Etiquetas de entidad

En Microsoft 365 Defender, puede establecer tres tipos de etiquetas de entidad defender para **identidad:** etiquetas confidenciales, etiquetas Desalonada y **etiquetas Exchange de servidor**. 

Para establecer estas etiquetas, <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">en Microsoft 365 Defender</a>, vaya **a Configuración** y, a continuación, **Identities**.

:::image type="content" source="../../media/defender-identity/settings-identities.png" alt-text="La opción Identidades de la columna Nombre de la Configuración página" lightbox="../../media/defender-identity/settings-identities.png":::

La configuración de la etiqueta aparecerá en **Etiquetas de entidad**.

:::image type="content" source="../../media/defender-identity/tag-settings.png" alt-text="El panel Etiquetas de entidad" lightbox="../../media/defender-identity/tag-settings.png":::

Para establecer cada tipo de etiqueta, siga las instrucciones siguientes.

## <a name="sensitive--tags"></a>Etiquetas confidenciales

La **etiqueta Confidencial** se usa para identificar activos de alto valor. La ruta de movimiento lateral también se basa en el estado de confidencialidad de una entidad. Defender for Identity considera que algunas entidades son confidenciales automáticamente. Para obtener una lista de esos activos, vea [Entidades confidenciales](/defender-for-identity/manage-sensitive-honeytoken-accounts#sensitive-entities).

También puede etiquetar manualmente usuarios, dispositivos o grupos como confidenciales.

1. Seleccione **Confidencial**. A continuación, verá los **usuarios, dispositivos** y grupos confidenciales **existentes**. 

   :::image type="content" source="../../media/defender-identity/sensitive-entities.png" alt-text="La pestaña Dispositivos del elemento de menú Entidades confidenciales" lightbox="../../media/defender-identity/sensitive-entities.png":::

1. En cada categoría, seleccione **Etiqueta...** para etiquetar ese tipo de entidad. Por ejemplo, en **Grupos**, seleccione **Grupos de etiquetas.** Se abrirá un panel con los grupos que puede seleccionar para etiquetar. Para buscar un grupo, escriba su nombre en el cuadro de búsqueda.

   :::image type="content" source="../../media/defender-identity/add-groups.png" alt-text="La opción para agregar un grupo" lightbox="../../media/defender-identity/add-groups.png":::

1. Seleccione el grupo y haga clic **en Agregar selección.**

   :::image type="content" source="../../media/defender-identity/add-selection.png" alt-text="La opción Agregar selección" lightbox="../../media/defender-identity/add-selection.png":::

## <a name="honeytoken-tags"></a>Etiquetas de Honeytoken

Las entidades de Honeytoken se usan como capturas para actores malintencionados. Cualquier autenticación asociada con estas entidades honeytoken desencadena una alerta.

Puede etiquetar usuarios o dispositivos con **la etiqueta Honeytoken** de la misma manera que etiqueta las cuentas confidenciales.

1. Seleccione **Honeytoken**. A continuación, verá los dispositivos y usuarios de **honeytoken** **existentes**.

    ![Entidades de Honeytoken.](../../media/defender-identity/honeytoken-entities.png)

1. En cada categoría, seleccione **Etiqueta...** para etiquetar ese tipo de entidad. Por ejemplo, en **Usuarios**, seleccione **Etiquetar usuarios.** Se abrirá un panel con los grupos que puede seleccionar para etiquetar. Para buscar un grupo, escriba su nombre en el cuadro de búsqueda.

   :::image type="content" source="../../media/defender-identity/add-users.png" alt-text="La opción para agregar usuarios" lightbox="../../media/defender-identity/add-users.png":::

1. Seleccione el usuario y haga clic **en Agregar selección.**

   :::image type="content" source="../../media/defender-identity/add-selected-user.png" alt-text="La opción para agregar un usuario seleccionado" lightbox="../../media/defender-identity/add-selected-user.png":::

## <a name="exchange-server-tags"></a>Exchange de servidor

Defender for Identity considera que Exchange servidores como activos de alto valor y los etiqueta automáticamente como **confidenciales**. También puede etiquetar manualmente los dispositivos como servidores Exchange dispositivos.

1. Seleccione **Exchange servidor**. A continuación, verá los dispositivos existentes etiquetados con la **Exchange de servidor**.

   :::image type="content" source="../../media/defender-identity/exchange-servers.png" alt-text="El Exchange menú del servidor" lightbox="../../media/defender-identity/exchange-servers.png":::

1. Para etiquetar un dispositivo como servidor Exchange, seleccione **Etiquetar dispositivos**.  Se abrirá un panel con los dispositivos que puede seleccionar para etiquetar. Para buscar un dispositivo, escriba su nombre en el cuadro de búsqueda.

   :::image type="content" source="../../media/defender-identity/add-devices.png" alt-text="La opción para agregar un dispositivo" lightbox="../../media/defender-identity/add-devices.png":::

1. Selecciona el dispositivo y haz clic **en Agregar selección.**

   :::image type="content" source="../../media/defender-identity/select-device.png" alt-text="La selección de un dispositivo" lightbox="../../media/defender-identity/select-device.png":::

## <a name="see-also"></a>Vea también

- [Administrar alertas de seguridad de Defender for Identity](manage-security-alerts.md)
