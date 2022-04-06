---
title: Integración de VPN de Microsoft Defender para la identidad en Microsoft 365 Defender
description: Obtenga información sobre cómo recopilar información de contabilidad integrando una VPN para Microsoft Defender for Identity en Microsoft 365 Defender
ms.date: 06/07/2021
ms.topic: how-to
author: dcurwin
ms.author: dacurwin
ms.service: microsoft-defender-for-identity
ms.custom: admindeeplinkDEFENDER
manager: raynew
ms.collection: M365-security-compliance
ms.openlocfilehash: a5c45ecda43b32e37f7309b9a2de33810d60bd15
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2022
ms.locfileid: "64469171"
---
# <a name="defender-for-identity-vpn-integration-in-microsoft-365-defender"></a>Defender para la integración de VPN de identidad en Microsoft 365 Defender

**Se aplica a:**

- Microsoft 365 Defender
- Defender for Identity

En este artículo se explica cómo integrar una VPN con [Microsoft Defender for Identity](/defender-for-identity) en [Microsoft 365 Defender](/microsoft-365/security/defender/overview-security-center).

>[!IMPORTANT]
>Como parte de la convergencia con <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a>, algunas opciones y detalles han cambiado desde su ubicación en el portal de Defender for Identity. Lea los detalles siguientes para descubrir dónde encontrar las características conocidas y las nuevas.

[!INCLUDE [Product long](includes/product-long.md)] puede recopilar información de contabilidad de soluciones VPN. Cuando se configura, en la página de perfil del usuario se incluye información de las conexiones VPN, como las direcciones IP y las ubicaciones donde se originaron las conexiones. Esto complementa el proceso de investigación proporcionando información adicional sobre la actividad de los usuarios, así como una nueva detección de conexiones VPN anormales. La llamada para resolver una dirección IP externa en una ubicación es anónima. No se envía ningún identificador personal en esta llamada.

[!INCLUDE [Product short](includes/product-short.md)] se integra con la solución VPN escuchando los eventos de contabilidad RADIUS reenviados a los sensores [!INCLUDE [Product short](includes/product-short.md)] . Este mecanismo se basa en la contabilidad RADIUS estándar ([RFC 2866](https://tools.ietf.org/html/rfc2866)) y se admiten los siguientes proveedores de VPN:

- Microsoft
- F5
- Punto de comprobación
- Cisco ASA

## <a name="prerequisites"></a>Requisitos previos

Para habilitar la integración de VPN, asegúrese de establecer los siguientes parámetros:

- Abra el puerto UDP 1813 en los sensores [!INCLUDE [Product short](includes/product-short.md)] o sensores [!INCLUDE [Product short](includes/product-short.md)] independientes.

> [!NOTE]
>
> - Al habilitar **la contabilidad** radius, [!INCLUDE [Product short](includes/product-short.md)] el sensor habilitará una directiva de firewall **[!INCLUDE [Product long](includes/product-long.md)]** Windows previamente aprovisionada denominada Sensor para permitir la contabilidad RADIUS entrante en el puerto UDP 1813.
> - La integración de VPN no se admite en entornos que cumplan con los Estándares federales de procesamiento de información (FIPS)

En el ejemplo siguiente se usa Microsoft Routing and Remote Access Server (RRAS) para describir el proceso de configuración de VPN.

Si usa una solución VPN de terceros, consulte su documentación para obtener instrucciones sobre cómo habilitar la contabilidad RADIUS.

## <a name="configure-radius-accounting-on-the-vpn-system"></a>Configurar la contabilidad RADIUS en el sistema VPN

Realice los pasos siguientes en el servidor RRAS.

1. Abra la **consola Enrutamiento y acceso remoto** .
1. Haga clic con el botón secundario en el nombre del servidor y seleccione **Propiedades**.
1. En la **pestaña Seguridad** , en **Proveedor de contabilidad**, seleccione **Contabilidad RADIUS** y **seleccione Configurar**.

   :::image type="content" source="../../media/defender-identity/radius-setup.png" alt-text="Configuración de RADIUS" lightbox="../../media/defender-identity/radius-setup.png":::

1. En la **ventana Agregar servidor RADIUS** , escriba el nombre **del** servidor del [!INCLUDE [Product short](includes/product-short.md)] sensor más cercano (que tiene conectividad de red). Para una alta disponibilidad, puede agregar sensores [!INCLUDE [Product short](includes/product-short.md)] adicionales como servidores RADIUS. En **Puerto**, asegúrese de que el valor predeterminado de 1813 está configurado. Seleccione **Cambiar** y escriba una nueva cadena secreta compartida de caracteres alfanuméricos. Tome nota de la nueva cadena secreta compartida, ya que tendrá que rellenarla más adelante durante la [!INCLUDE [Product short](includes/product-short.md)] configuración. Active el **cuadro Enviar mensajes de cuenta RADIUS y Desasoyéndolo** y seleccione **Aceptar en** todos los cuadros de diálogo abiertos.

   :::image type="content" source="../../media/defender-identity/vpn-set-accounting.png" alt-text="Configuración de VPN" lightbox="../../media/defender-identity/vpn-set-accounting.png":::

## <a name="configure-vpn-in-defender-for-identity"></a>Configurar VPN en Defender for Identity

[!INCLUDE [Product short](includes/product-short.md)] recopila datos de VPN que ayudan a perfilar las ubicaciones desde las que los equipos se conectan a la red y a poder detectar conexiones VPN sospechosas.

Para configurar los datos de VPN en [!INCLUDE [Product short](includes/product-short.md)] Microsoft 365 Defender:

1. En <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a>, vaya a Configuración y, a **continuación**, **Identities**.

   :::image type="content" source="../../media/defender-identity/settings-identities.png" alt-text="La opción Identidades en el elemento de menú configuración" lightbox="../../media/defender-identity/settings-identities.png":::

1. Seleccione **VPN**.
1. Seleccione **Habilitar la contabilidad de** radio y escriba el secreto **compartido** que configuró anteriormente en el servidor VPN de RRAS. Después, seleccione **Guardar**.

   :::image type="content" source="../../media/defender-identity/vpn-integration.png" alt-text="Integración de VPN" lightbox="../../media/defender-identity/vpn-integration.png":::

Una vez habilitado, todos los sensores de Defender for Identity escucharán en el puerto 1813 eventos de contabilidad RADIUS y la configuración de VPN se completará.

Después de que el sensor Defender for Identity reciba los eventos VPN y los envíe al servicio en la nube de Defender for Identity para su procesamiento, el perfil de entidad indicará las distintas ubicaciones y actividades de VPN a las que se accede en el perfil indicará las ubicaciones.

## <a name="see-also"></a>Vea también

- [Investigar alertas con Microsoft 365 Defender](../defender/investigate-alerts.md)
