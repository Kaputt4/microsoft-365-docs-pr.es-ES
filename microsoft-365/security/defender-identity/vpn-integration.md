---
title: Microsoft Defender for Identity integración de VPN en Microsoft 365 Defender
description: Obtenga información sobre cómo recopilar información contable mediante la integración de una VPN para Microsoft Defender for Identity en Microsoft 365 Defender
ms.date: 06/07/2021
ms.topic: how-to
author: dcurwin
ms.author: dacurwin
ms.service: microsoft-defender-for-identity
ms.custom: admindeeplinkDEFENDER
manager: raynew
ms.collection: M365-security-compliance
search.appverid: met150
ms.openlocfilehash: 02a0ecf0dea5b4e3fc820280a389c30b79b5fb43
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67682291"
---
# <a name="defender-for-identity-vpn-integration-in-microsoft-365-defender"></a>Integración de VPN de Defender for Identity en Microsoft 365 Defender

**Se aplica a:**

- Microsoft 365 Defender
- Defender for Identity

En este artículo se explica cómo integrar una VPN con [Microsoft Defender for Identity](/defender-for-identity) en [Microsoft 365 Defender](/microsoft-365/security/defender/overview-security-center).

>[!IMPORTANT]
>Como parte de la convergencia con <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a>, algunas opciones y detalles han cambiado desde su ubicación en el portal de Defender for Identity. Lea los detalles siguientes para descubrir dónde encontrar las características conocidas y nuevas.

[!INCLUDE [Product long](includes/product-long.md)] puede recopilar información contable de soluciones VPN. Cuando se configura, en la página de perfil del usuario se incluye información de las conexiones VPN, como las direcciones IP y las ubicaciones donde se originaron las conexiones. Esto complementa el proceso de investigación proporcionando información adicional sobre la actividad de los usuarios, así como una nueva detección de conexiones VPN anormales. La llamada para resolver una dirección IP externa en una ubicación es anónima. No se envía ningún identificador personal en esta llamada.

[!INCLUDE [Product short](includes/product-short.md)] se integra con la solución VPN escuchando los eventos de contabilidad RADIUS reenviados a los [!INCLUDE [Product short](includes/product-short.md)] sensores. Este mecanismo se basa en la contabilidad RADIUS estándar ([RFC 2866](https://tools.ietf.org/html/rfc2866)) y se admiten los siguientes proveedores de VPN:

- Microsoft
- F5
- Check Point
- Cisco ASA

## <a name="prerequisites"></a>Requisitos previos

Para habilitar la integración de VPN, asegúrese de establecer los parámetros siguientes:

- Abra el puerto UDP 1813 en los [!INCLUDE [Product short](includes/product-short.md)] sensores o [!INCLUDE [Product short](includes/product-short.md)] sensores independientes.

> [!NOTE]
>
> - Al habilitar **la contabilidad** radius, el [!INCLUDE [Product short](includes/product-short.md)] sensor habilitará una directiva de firewall de Windows preaprovisionada denominada **[!INCLUDE [Product long](includes/product-long.md)] Sensor** para permitir la contabilidad RADIUS entrante en el puerto UDP 1813.
> - La integración de VPN no se admite en entornos que cumplen los estándares federales de procesamiento de información (FIPS)

En el ejemplo siguiente se usa el servidor de enrutamiento y acceso remoto (RRAS) de Microsoft para describir el proceso de configuración de VPN.

Si usa una solución VPN de terceros, consulte su documentación para obtener instrucciones sobre cómo habilitar la contabilidad RADIUS.

## <a name="configure-radius-accounting-on-the-vpn-system"></a>Configuración de la contabilidad radius en el sistema VPN

Realice los pasos siguientes en el servidor RRAS.

1. Abra la consola **enrutamiento y acceso remoto** .
1. Haga clic con el botón derecho en el nombre del servidor y seleccione **Propiedades**.
1. En la pestaña **Seguridad** , en **Proveedor de contabilidad**, seleccione **Contabilidad RADIUS** y seleccione **Configurar**.

   :::image type="content" source="../../media/defender-identity/radius-setup.png" alt-text="Configuración de RADIUS" lightbox="../../media/defender-identity/radius-setup.png":::

1. En la ventana **Agregar servidor RADIUS** , escriba el **nombre del servidor** del sensor más cercano [!INCLUDE [Product short](includes/product-short.md)] (que tiene conectividad de red). Para lograr alta disponibilidad, puede agregar sensores adicionales [!INCLUDE [Product short](includes/product-short.md)] como servidores RADIUS. En **Puerto**, asegúrese de que el valor predeterminado de 1813 está configurado. Seleccione **Cambiar** y escriba una nueva cadena secreta compartida de caracteres alfanuméricos. Tome nota de la nueva cadena secreta compartida, ya que tendrá que rellenarla más adelante durante [!INCLUDE [Product short](includes/product-short.md)] la configuración. Active la casilla **Enviar mensajes de cuenta RADIUS activada y sin contabilidad** y seleccione **Aceptar** en todos los cuadros de diálogo abiertos.

   :::image type="content" source="../../media/defender-identity/vpn-set-accounting.png" alt-text="Configuración de VPN" lightbox="../../media/defender-identity/vpn-set-accounting.png":::

## <a name="configure-vpn-in-defender-for-identity"></a>Configuración de VPN en Defender for Identity

[!INCLUDE [Product short](includes/product-short.md)] recopila datos de VPN que ayudan a generar perfiles de las ubicaciones desde las que los equipos se conectan a la red y a detectar conexiones VPN sospechosas.

Para configurar los datos de VPN en [!INCLUDE [Product short](includes/product-short.md)] en Microsoft 365 Defender:

1. En <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a>, vaya a **Configuración** y, a continuación, **Identidades**.

   :::image type="content" source="../../media/defender-identity/settings-identities.png" alt-text="La opción Identidades en el elemento de menú configuración" lightbox="../../media/defender-identity/settings-identities.png":::

1. Seleccione **VPN**.
1. Seleccione **Habilitar la contabilidad de radio** y escriba el **secreto compartido** que configuró anteriormente en el servidor VPN de RRAS. Después, seleccione **Guardar**.

   :::image type="content" source="../../media/defender-identity/vpn-integration.png" alt-text="Integración de VPN" lightbox="../../media/defender-identity/vpn-integration.png":::

Una vez habilitado esto, todos los sensores de Defender for Identity escucharán en el puerto 1813 los eventos de contabilidad radius y la configuración de VPN se completa.

Una vez que el sensor de Defender for Identity recibe los eventos vpn y los envía al servicio en la nube de Defender for Identity para su procesamiento, el perfil de entidad indicará las distintas ubicaciones y actividades de VPN a las que se accede en el perfil indicarán las ubicaciones.

## <a name="see-also"></a>Vea también

- [Investigar alertas con Microsoft 365 Defender](../defender/investigate-alerts.md)
