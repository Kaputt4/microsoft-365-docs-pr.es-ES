---
title: Exclusiones de detección de identidades de Microsoft Defender en Microsoft 365 Defender
description: Obtenga información sobre cómo configurar Microsoft Defender para exclusiones de detección de identidad en Microsoft 365 Defender.
ms.date: 11/02/2021
ms.topic: how-to
author: dcurwin
ms.author: dacurwin
ms.service: microsoft-defender-for-identity
manager: raynew
ms.collection: M365-security-compliance
ms.openlocfilehash: e2df92e44b323bd0555407d72ebd48a7e050c9a5
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2022
ms.locfileid: "64473923"
---
# <a name="configure-defender-for-identity-detection-exclusions-in-microsoft-365-defender"></a>Configurar Defender para exclusiones de detección de identidad en Microsoft 365 Defender

**Se aplica a:**

- Microsoft 365 Defender
- Defender for Identity

En este artículo se explica cómo configurar [Microsoft Defender para exclusiones de](/defender-for-identity) detección de identidad en [Microsoft 365 Defender](/microsoft-365/security/defender/overview-security-center).

> [!IMPORTANT]
> Como parte de la convergencia con Microsoft 365 Defender, algunas opciones y detalles han cambiado desde su ubicación en el portal de Defender for Identity. Lea los detalles siguientes para descubrir dónde encontrar las características conocidas y las nuevas.

[!INCLUDE [Product long](includes/product-long.md)] permite la exclusión de direcciones IP, equipos, dominios o usuarios específicos de varias detecciones.

Por ejemplo, un **escáner** de seguridad que usa DNS como mecanismo de análisis podría desencadenar una alerta de reconocimiento dns. La creación de una exclusión ayuda a Defender for Identity a ignorar dichos escáneres y reducir los falsos positivos.

>[!NOTE]
>De los dominios más comunes con [comunicación](/defender-for-identity/exfiltration-alerts#suspicious-communication-over-dns-external-id-2031) sospechosa sobre alertas DNS abiertas en ellos, observamos los dominios que los clientes más excluyeron de la alerta. Estos dominios se agregan a la lista de exclusiones de forma predeterminada, pero tiene la opción de quitarlos fácilmente.

## <a name="how-to-add-detection-exclusions"></a>Cómo agregar exclusiones de detección

1. En [Microsoft 365 Defender](https://security.microsoft.com/), vaya a Configuración y, a **continuación**, **Identities**.

   :::image type="content" source="../../media/defender-identity/settings-identities.png" alt-text="La opción Identidades de la columna Nombre" lightbox="../../media/defender-identity/settings-identities.png":::

1. A continuación, verá **Entidades excluidas en** el menú de la izquierda.

   :::image type="content" source="../../media/defender-identity/excluded-entities.png" alt-text="El panel Entidades excluidas" lightbox="../../media/defender-identity/excluded-entities.png":::

A continuación, puede establecer exclusiones mediante dos **métodos: Exclusiones por regla de detección** y **Entidades excluidas globales**.

## <a name="exclusions-by-detection-rule"></a>Exclusiones por regla de detección

1. En el menú de la izquierda, seleccione **Exclusiones por regla de detección**. Verá una lista de reglas de detección.

   :::image type="content" source="../../media/defender-identity/exclusions-by-detection-rule.png" alt-text="La opción Exclusiones por regla de detección del elemento Entidades excluidas del panel izquierdo" lightbox="../../media/defender-identity/exclusions-by-detection-rule.png":::

1. Para cada detección que desee configurar, siga estos pasos:

    1. Seleccione la regla. Puede buscar detecciones mediante la barra de búsqueda. Una vez seleccionado, se abrirá un panel con los detalles de la regla de detección.

       :::image type="content" source="../../media/defender-identity/detection-rule-details.png" alt-text="Detalles de una regla de detección" lightbox="../../media/defender-identity/detection-rule-details.png":::

    1. Para agregar una exclusión, seleccione **el botón Entidades** excluidas y, a continuación, elija el tipo de exclusión. Hay diferentes entidades excluidas disponibles para cada regla. Incluyen usuarios, dispositivos, dominios y direcciones IP. En este ejemplo, las opciones son **Excluir dispositivos** y **Excluir direcciones IP**.

       :::image type="content" source="../../media/defender-identity/exclude-devices-or-ip-addresses.png" alt-text="La opción para excluir dispositivos o direcciones IP" lightbox="../../media/defender-identity/exclude-devices-or-ip-addresses.png":::

    1. Después de elegir el tipo de exclusión, puede agregar la exclusión. En el panel que se abre, seleccione el **+** botón para agregar la exclusión.

       :::image type="content" source="../../media/defender-identity/add-exclusion.png" alt-text="La opción para agregar una exclusión" lightbox="../../media/defender-identity/add-exclusion.png":::

    1. A continuación, agregue la entidad que se va a excluir. Seleccione **+ Agregar** para agregar la entidad a la lista.

       :::image type="content" source="../../media/defender-identity/add-excluded-entity.png" alt-text="La opción para agregar entidad que se va a excluir" lightbox="../../media/defender-identity/add-excluded-entity.png":::

    1. A **continuación, seleccione Excluir direcciones IP** (en este ejemplo) para completar la exclusión.

       :::image type="content" source="../../media/defender-identity/exclude-ip-addresses.png" alt-text="La opción para excluir direcciones IP" lightbox="../../media/defender-identity/exclude-ip-addresses.png":::

    1. Una vez que haya agregado exclusiones, puede exportar la lista o quitar las exclusiones volviendo al **botón Entidades excluidas** . En este ejemplo, hemos vuelto a **Excluir dispositivos**. Para exportar la lista, seleccione el botón de flecha abajo.

       :::image type="content" source="../../media/defender-identity/return-to-exclude-devices.png" alt-text="La opción Volver a excluir dispositivos" lightbox="../../media/defender-identity/return-to-exclude-devices.png":::

    1. Para eliminar una exclusión, seleccione la exclusión y seleccione el icono de papelera.

       :::image type="content" source="../../media/defender-identity/delete-exclusion.png" alt-text="La opción Eliminar una exclusión" lightbox="../../media/defender-identity/delete-exclusion.png":::

## <a name="global-excluded-entities"></a>Entidades excluyedas globales

Ahora también puede configurar exclusiones por **entidades excluidas globales**. Las exclusiones globales permiten definir determinadas entidades (direcciones IP, subredes, dispositivos o dominios) para excluirse en todas las detecciones que tiene Defender for Identity. Por ejemplo, si excluyes un dispositivo, solo se aplicará a aquellas detecciones que tengan identificación de dispositivo como parte de la detección.

1. En el menú de la izquierda, seleccione **Entidades excluyedas globales**. Verá las categorías de entidades que puede excluir.

   :::image type="content" source="../../media/defender-identity/global-excluded-entities.png" alt-text="Elemento de submenú Global excluded entities" lightbox="../../media/defender-identity/global-excluded-entities.png":::

1. Elija un tipo de exclusión. En este ejemplo, seleccionamos **Excluir dominios**.

   :::image type="content" source="../../media/defender-identity/exclude-domains.png" alt-text="La pestaña Dominios" lightbox="../../media/defender-identity/exclude-domains.png":::

1. Se abrirá un panel donde puede agregar un dominio que se va a excluir. Agregue el dominio que desea excluir.

   :::image type="content" source="../../media/defender-identity/add-excluded-domain.png" alt-text="La opción para agregar un dominio que se va a excluir" lightbox="../../media/defender-identity/add-excluded-domain.png":::

1. El dominio se agregará a la lista. Seleccione **Excluir dominios** para completar la exclusión.

   :::image type="content" source="../../media/defender-identity/select-exclude-domains.png" alt-text="La opción Seleccionar dominios que se excluirán" lightbox="../../media/defender-identity/select-exclude-domains.png":::

1. A continuación, verá el dominio en la lista de entidades que se excluirán de todas las reglas de detección. Puede exportar la lista o quitar las entidades seleccionándolos y haciendo clic en **el botón** Quitar.

   :::image type="content" source="../../media/defender-identity/global-excluded-entries-list.png" alt-text="La lista de entradas globales excluidas" lightbox="../../media/defender-identity/global-excluded-entries-list.png":::

## <a name="see-also"></a>Vea también

- [Administrar alertas de seguridad de Defender for Identity](manage-security-alerts.md)
