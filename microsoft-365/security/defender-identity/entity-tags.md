---
title: Etiquetas de entidad de Microsoft Defender para identity en Microsoft 365 Defender
description: Obtenga información sobre cómo aplicar etiquetas de entidad de Microsoft Defender para identidad en Microsoft 365 Defender
ms.date: 06/08/2021
ms.topic: how-to
author: dcurwin
ms.author: dacurwin
ms.service: microsoft-defender-for-identity
manager: raynew
ms.openlocfilehash: 2dcb7767be7145420c08161782f27a51ec38727ae5d427459c4af1d9676cd37d
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "53844805"
---
# <a name="defender-for-identity-entity-tags-in-microsoft-365-defender"></a>Etiquetas de entidad Defender for Identity en Microsoft 365 Defender

**Se aplica a:**

- Microsoft 365 Defender
- Defender for Identity

En este artículo se explica cómo aplicar [etiquetas de](/defender-for-identity) entidad de Microsoft Defender para identidad en [Microsoft 365 Defender](/microsoft-365/security/defender/overview-security-center).

>[!IMPORTANT]
>Como parte de la convergencia con Microsoft 365 Defender, algunas opciones y detalles han cambiado desde su ubicación en el portal de Defender for Identity. Lea los detalles siguientes para descubrir dónde encontrar las características conocidas y las nuevas.

## <a name="entity-tags"></a>Etiquetas de entidad

En Microsoft 365 Defender, puede establecer tres tipos de etiquetas de entidad defender para **identidad:** etiquetas confidenciales, etiquetas Desalono y **etiquetas de servidor** Exchange servidor . 

Para establecer estas etiquetas, [en Microsoft 365 Defender](https://security.microsoft.com/), vaya **a Configuración** y, a continuación, **Identities**.

![Vaya a Configuración, a continuación, Identidades](../../media/defender-identity/settings-identities.png)

La configuración de la etiqueta aparecerá en la **Configuración** columna.

![Tipos de configuración de etiquetas](../../media/defender-identity/tag-settings.png)

Para establecer cada tipo de etiqueta, siga las instrucciones siguientes.

## <a name="sensitive--tags"></a>Etiquetas confidenciales

La **etiqueta Confidencial** se usa para identificar activos de alto valor. La ruta de movimiento lateral también se basa en el estado de confidencialidad de una entidad. Defender for Identity considera que algunas entidades son confidenciales automáticamente. Para obtener una lista de esos activos, vea [Entidades confidenciales](/defender-for-identity/manage-sensitive-honeytoken-accounts#sensitive-entities).

También puede etiquetar manualmente usuarios, dispositivos o grupos como confidenciales.

1. Seleccione **Etiqueta confidencial**. A continuación, verá los **usuarios,** **dispositivos** y grupos confidenciales **existentes.**

    ![Entidades confidenciales](../../media/defender-identity/sensitive-entities.png)

1. En cada categoría, seleccione **Etiqueta...** para etiquetar ese tipo de entidad. Por ejemplo, en **Grupos**, seleccione **Grupos de etiquetas.** Se abrirá un panel con los grupos que puede seleccionar para etiquetar. Para buscar un grupo, escriba su nombre en el cuadro de búsqueda.

    ![Agregar grupos](../../media/defender-identity/add-groups.png)

1. Seleccione el grupo y haga clic **en Agregar selección.**

    ![Agregar selección](../../media/defender-identity/add-selection.png)

## <a name="honeytoken-tags"></a>Etiquetas de Honeytoken

Las entidades de Honeytoken se usan como capturas para actores malintencionados. Cualquier autenticación asociada con estas entidades honeytoken desencadena una alerta.

Puede etiquetar usuarios o dispositivos con **la etiqueta Honeytoken** de la misma manera que etiqueta las cuentas confidenciales.

1. Seleccione **Etiqueta de Honeytoken**. A continuación, verá los dispositivos y usuarios de **honeytoken** **existentes.**

    ![Entidades de Honeytoken](../../media/defender-identity/honeytoken-entities.png)

1. En cada categoría, seleccione **Etiqueta...** para etiquetar ese tipo de entidad. Por ejemplo, en **Usuarios**, seleccione **Etiquetar usuarios.** Se abrirá un panel con los grupos que puede seleccionar para etiquetar. Para buscar un grupo, escriba su nombre en el cuadro de búsqueda.

    ![Agregar usuarios](../../media/defender-identity/add-users.png)

1. Seleccione el usuario y haga clic **en Agregar selección.**

    ![Agregar usuario seleccionado](../../media/defender-identity/add-selected-user.png)

## <a name="exchange-server-tags"></a>Exchange de servidor

Defender for Identity considera que Exchange servidores como activos de alto valor y los etiqueta automáticamente como **confidenciales.** También puede etiquetar manualmente los dispositivos como servidores Exchange dispositivos.

1. Seleccione **Exchange de servidor**. A continuación, verá los dispositivos existentes etiquetados con la **etiqueta Exchange de servidor.**

    ![Exchange servidores](../../media/defender-identity/exchange-servers.png)

1. Para etiquetar un dispositivo como servidor Exchange, seleccione **Etiquetar dispositivos**.  Se abrirá un panel con los dispositivos que puede seleccionar para etiquetar. Para buscar un dispositivo, escriba su nombre en el cuadro de búsqueda.

    ![Agregar dispositivos](../../media/defender-identity/add-devices.png)

1. Selecciona el dispositivo y haz clic **en Agregar selección.**

    ![Seleccionar dispositivo](../../media/defender-identity/select-device.png)

## <a name="see-also"></a>Consulte también

- [Administrar alertas de seguridad de Defender for Identity](manage-security-alerts.md)
