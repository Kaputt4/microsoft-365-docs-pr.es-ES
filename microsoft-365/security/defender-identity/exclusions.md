---
title: Exclusiones de detección de identidades de Microsoft Defender en Microsoft 365 Defender
description: Obtenga información sobre cómo configurar Microsoft Defender para exclusiones de detección de identidad en Microsoft 365 Defender.
ms.date: 11/02/2021
ms.topic: how-to
author: dcurwin
ms.author: dacurwin
ms.service: microsoft-defender-for-identity
manager: raynew
ms.openlocfilehash: d4a8fb5cb8677acaf574eb25df6e8e32720e4628
ms.sourcegitcommit: ab5368888876d8796da7640553fc8426d040f470
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2021
ms.locfileid: "60787864"
---
# <a name="configure-defender-for-identity-detection-exclusions-in-microsoft-365-defender-preview"></a>Configurar Defender para exclusiones de detección de identidad en Microsoft 365 Defender (versión preliminar)

**Se aplica a:**

- Microsoft 365 Defender
- Defender for Identity

En este artículo se explica cómo configurar [Microsoft Defender para exclusiones de](/defender-for-identity) detección de identidad en [Microsoft 365 Defender](/microsoft-365/security/defender/overview-security-center).

> [!IMPORTANT]
> Como parte de la convergencia con Microsoft 365 Defender, algunas opciones y detalles han cambiado desde su ubicación en el portal de Defender for Identity. Lea los detalles siguientes para descubrir dónde encontrar las características conocidas y las nuevas.

[!INCLUDE [Product long](includes/product-long.md)] permite la exclusión de direcciones IP, equipos, dominios o usuarios específicos de varias detecciones.

Por ejemplo, un **escáner** de seguridad que usa DNS como mecanismo de análisis podría desencadenar una alerta de reconocimiento dns. La creación de una exclusión ayuda a Defender for Identity a ignorar dichos escáneres y reducir los falsos positivos.

>[!NOTE]
>De los dominios más comunes con comunicación sospechosa sobre alertas [DNS](/defender-for-identity/exfiltration-alerts#suspicious-communication-over-dns-external-id-2031) abiertas en ellos, observamos los dominios que los clientes más excluyeron de la alerta. Estos dominios se agregan a la lista de exclusiones de forma predeterminada, pero tiene la opción de quitarlos fácilmente.

## <a name="how-to-add-detection-exclusions"></a>Cómo agregar exclusiones de detección

1. En [Microsoft 365 Defender](https://security.microsoft.com/), vaya **a Configuración** y, a continuación, **Identities**.

    ![Vaya a Configuración y, a continuación, Identities.](../../media/defender-identity/settings-identities.png)

1. A continuación, verá **Entidades excluidas en** el menú de la izquierda.

    ![Entidades excluidas.](../../media/defender-identity/excluded-entities.png)

A continuación, puede establecer exclusiones mediante dos **métodos: Exclusiones por regla de detección** y **Entidades excluidas globales.**

## <a name="exclusions-by-detection-rule"></a>Exclusiones por regla de detección

1. En el menú de la izquierda, seleccione **Exclusiones por regla de detección**. Verá una lista de reglas de detección.

    ![Exclusiones por regla de detección.](../../media/defender-identity/exclusions-by-detection-rule.png)

1. Para cada detección que desee configurar, siga estos pasos:

    1. Seleccione la regla. Puede buscar detecciones mediante la barra de búsqueda. Una vez seleccionado, se abrirá un panel con los detalles de la regla de detección.

        ![Detalles de la regla de detección.](../../media/defender-identity/detection-rule-details.png)

    1. Para agregar una exclusión, seleccione **el botón Entidades** excluidas y, a continuación, elija el tipo de exclusión. Hay diferentes entidades excluidas disponibles para cada regla. Incluyen usuarios, dispositivos, dominios y direcciones IP. En este ejemplo, las opciones son **Excluir dispositivos** y **Excluir direcciones IP.**

        ![Excluir dispositivos o direcciones IP.](../../media/defender-identity/exclude-devices-or-ip-addresses.png)

    1. Después de elegir el tipo de exclusión, puede agregar la exclusión. En el panel que se abre, seleccione el **+** botón para agregar la exclusión.

        ![Agregue una exclusión.](../../media/defender-identity/add-exclusion.png)

    1. A continuación, agregue la entidad que se va a excluir. Seleccione **+ Agregar** para agregar la entidad a la lista.

        ![Agregue una entidad que se va a excluir.](../../media/defender-identity/add-excluded-entity.png)

    1. A **continuación, seleccione Excluir direcciones IP** (en este ejemplo) para completar la exclusión.

        ![Excluir direcciones IP.](../../media/defender-identity/exclude-ip-addresses.png)

    1. Una vez que haya agregado exclusiones, puede exportar la lista o quitar las exclusiones volviendo al **botón Entidades excluidas.** En este ejemplo, hemos devuelto a **Excluir dispositivos**. Para exportar la lista, seleccione el botón de flecha abajo.

        ![Vuelva a Excluir dispositivos.](../../media/defender-identity/return-to-exclude-devices.png)

    1. Para eliminar una exclusión, seleccione la exclusión y seleccione el icono de papelera.

        ![Eliminar una exclusión.](../../media/defender-identity/delete-exclusion.png)

## <a name="global-excluded-entities"></a>Entidades excluyedas globales

Ahora también puede configurar exclusiones por **entidades excluidas globales.** Las exclusiones globales permiten definir determinadas entidades (direcciones IP, subredes, dispositivos o dominios) para excluirse en todas las detecciones que tiene Defender for Identity. Por ejemplo, si excluyes un dispositivo, solo se aplicará a aquellas detecciones que tengan identificación de dispositivo como parte de la detección.

1. En el menú de la izquierda, **seleccione Global excluded entities**. Verá las categorías de entidades que puede excluir.

    ![Entidades globales excluidas.](../../media/defender-identity/global-excluded-entities.png)

1. Elija un tipo de exclusión. En este ejemplo, seleccionamos **Excluir dominios**.

    ![Excluir dominios.](../../media/defender-identity/exclude-domains.png)

1. Se abrirá un panel donde puede agregar un dominio que se va a excluir. Agregue el dominio que desea excluir.

    ![Agregue un dominio que se va a excluir.](../../media/defender-identity/add-excluded-domain.png)

1. El dominio se agregará a la lista. Seleccione **Excluir dominios** para completar la exclusión.

    ![Seleccione excluir dominios.](../../media/defender-identity/select-exclude-domains.png)

1. A continuación, verá el dominio en la lista de entidades que se excluirán de todas las reglas de detección. Puede exportar la lista o quitar las entidades seleccionándolos y haciendo clic en **el botón** Quitar.

    ![Lista de entradas globales excluidas.](../../media/defender-identity/global-excluded-entries-list.png)

## <a name="see-also"></a>Consulte también

- [Administrar alertas de seguridad de Defender for Identity](manage-security-alerts.md)
