---
title: Uso de la protección de red para evitar conexiones de Linux a sitios incorrectos
description: Protección de la red evitando que los usuarios de Linux accedan a direcciones de red malintencionadas y sospechosas conocidas
keywords: Protección de red, vulnerabilidades de seguridad de Linux, sitio web malintencionado, ip, dominio, dominios, comando y control, SmartScreen, notificación del sistema
ms.service: microsoft-365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
audience: ITPro
author: jweston-1
ms.author: v-jweston
ms.reviewer: oogunrinde
manager: dansimp
ms.custom: asr
ms.subservice: mde
ms.topic: overview
ms.collection:
- m365initiative-m365-defender
- M365-security-compliance
ms.date: ''
search.appverid: met150
ms.openlocfilehash: a472fae685503d742a4d8b6cf95dce2f0bb6619c
ms.sourcegitcommit: 2dedd0f594b817779e034afa6c4418def2382a22
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2022
ms.locfileid: "67797921"
---
# <a name="network-protection-for-linux"></a>Protección de red para Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> Parte de la información se refiere a productos preliminares que pueden ser modificados sustancialmente antes de su lanzamiento comercial. Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.

## <a name="overview"></a>Información general

Microsoft está aportando funcionalidad de protección de red a Linux.

La protección de red ayuda a reducir la superficie expuesta a ataques de los dispositivos frente a eventos basados en Internet. Impide que los empleados usen cualquier aplicación para acceder a dominios peligrosos que pueden hospedar:

- estafas de phishing
- Hazañas
- otro contenido malintencionado en Internet

La protección de red amplía el ámbito de [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview.md) de Microsoft Defender para bloquear todo el tráfico HTTP saliente que intenta conectarse a orígenes de baja reputación. Los bloques del tráfico HTTP saliente se basan en el dominio o el nombre de host.

## <a name="web-content-filtering-for-linux"></a>Filtrado de contenido web para Linux

Puede usar el filtrado de contenido web para realizar pruebas con Protección de red para Linux. Consulte [Filtrado de contenido web](web-content-filtering.md).

### <a name="known-issues"></a>Problemas conocidos

- Network Protection se implementa como un túnel de red privada virtual (VPN). Hay disponibles opciones avanzadas de enrutamiento de paquetes mediante scripts nftables/iptables personalizados.
- La experiencia de usuario de bloqueo o advertencia no está disponible
  - Se recopilan comentarios de los clientes para impulsar más mejoras de diseño

> [!NOTE]
> Para evaluar la eficacia de Linux Web Threat Protection, se recomienda usar el explorador Firefox, que es el valor predeterminado para todas las distribuciones.

### <a name="prerequisites"></a>Requisitos previos

- Licencias: Microsoft Defender para punto de conexión inquilino (puede ser de prueba) y los requisitos específicos de la plataforma que se encuentran en [Microsoft Defender para punto de conexión para plataformas que no son de Windows](non-windows.md#licensing-requirements)
- Máquinas incorporadas:
  - **Versión mínima de Linux**: para obtener una lista de las distribuciones admitidas, consulte [Microsoft Defender para punto de conexión en Linux](microsoft-defender-endpoint-linux.md).
  - **Microsoft Defender para punto de conexión versión de cliente Linux**: 101.78.13 -insiderSlow(Preview)

## <a name="instructions"></a>Instrucciones

Implementación manual de Linux, consulte [Implementación manual de Microsoft Defender para punto de conexión en Linux](linux-install-manually.md)

En el ejemplo siguiente se muestra la secuencia de comandos necesaria para el paquete mdatp en ubuntu 20.04 para el canal insiders-Slow.

```bash
curl -o microsoft.list https://packages.microsoft.com/config/ubuntu/20.04/insiders-slow.list 
sudo mv ./microsoft.list /etc/apt/sources.list.d/microsoft-insiders-slow.list 
sudo apt-get install gpg 
curl https://packages.microsoft.com/keys/microsoft.asc | sudo apt-key add - 
sudo apt-get install apt-transport-https 
sudo apt-get update 
sudo apt install -y mdatp 
```

### <a name="device-onboarding"></a>Incorporación de dispositivos

Para incorporar el dispositivo, debe descargar el paquete de incorporación de Python para el servidor Linux desde Microsoft 365 Defender -> Settings -> Administración de dispositivos -> Onboarding and run:

```bash
sudo python3 MicrosoftDefenderATPOnboardingLinuxServer.py 
```

### <a name="manually-enable-network-protection"></a>Habilitación manual de la protección de red

1. Active la característica "networkProtection", edite "/etc/opt/microsoft/mdatp/wdavcfg" y establezca **networkProtection** **en habilitado**.  
2. Reinicie el servicio mdatp ejecutando el siguiente comando:

```bash
sudo systemctl restart mdatp 
```
> :::image type="content" source="images/network-protection-linux-mdatp-restart.png" alt-text="Muestra el reinicio de mdatp de Linux." lightbox="images/network-protection-linux-mdatp-restart.png":::

### <a name="configure-the-enforcement-level"></a>Configuración del nivel de cumplimiento

La protección de red está deshabilitada de forma predeterminada, pero se puede configurar para ejecutarse en uno de los siguientes modos (también denominados niveles de cumplimiento):

- **Auditoría**: útil para asegurarse de que no afecta a las aplicaciones de línea de negocio ni para hacerse una idea de la frecuencia con la que se producen los bloques
- **Bloquear**: la protección de red impide la conexión a sitios web malintencionados
- **Deshabilitado**: todos los componentes asociados a Network Protection están deshabilitados

```bash
sudo mdatp config network-protection enforcement-level --value block
```

o

```bash
sudo mdatp config network-protection enforcement-level --value audit
```

Para confirmar que Network Protection se ha iniciado correctamente, ejecute el siguiente comando desde el terminal; compruebe que imprime "iniciado":

```bash
mdatp health --field network_protection_status
```

### <a name="validation"></a>Validation

A. Compruebe que La protección de red tiene efecto en sitios siempre bloqueados:

- [http://www.smartscreentestratings2.net](http://www.smartscreentestratings2.net)
- [https://www.smartscreentestratings2.net](https://www.smartscreentestratings2.net)
- [http://malw-090-0-1.phsh-005-0-1.smartscreentestratings.com/](http://malw-090-0-1.phsh-005-0-1.smartscreentestratings.com/)

B. Inspección de registros de diagnóstico

```bash
$ sudo mdatp log level set --level debug 
$ sudo tail -f /var/log/microsoft/mdatp/microsoft_defender_np_ext.log 
```

#### <a name="to-exit-the-validation-mode"></a>Para salir del modo de validación

Deshabilite la protección de red y reinicie la conexión de red:

```bash
$ sudo mdatp config network-protection enforcement-level --value disabled
```

## <a name="advanced-configuration"></a>Configuración avanzada

De forma predeterminada, la protección de red de Linux está activa en la puerta de enlace predeterminada; El enrutamiento y la tunelización están configurados internamente.
Para personalizar las interfaces de red, cambie el parámetro **networkSetupMode** del archivo de configuración **/opt/microsoft/mdatp/conf/**  y reinicie el servicio:

```bash
sudo systemctl restart  mdatp 
```

El archivo de configuración también permite al usuario personalizar:

- Configuración del proxy
- Almacenes de certificados SSL
- nombre del dispositivo de tunelización
- IP
- y más

Los valores predeterminados se probaron para todas las distribuciones, como se describe en [Microsoft Defender para punto de conexión en Linux](microsoft-defender-endpoint-linux.md).

### <a name="microsoft-defender-portal"></a>Portal de Microsoft Defender

Además, asegúrese de que en Las **características avanzadas** de **los** >  puntos de conexión de **Configuración** >  de **Microsoft Defender** >  se _establece la_ alternancia **"Indicadores de red personalizados"** habilitada.

> [!IMPORTANT]
> El botón de alternancia **"Indicadores de red personalizados"** anterior controla la habilitación de **indicadores personalizados** **para todas las plataformas con compatibilidad con protección de red, incluido Windows. Recuerde que, en Windows, para que los indicadores se apliquen también debe tener la protección de red habilitada explícitamente.

>:::image type="content" source="images/network-protection-linux-defender-security-center-advanced-features-settings.png" alt-text="Creación de perfil de MEM" lightbox="images/network-protection-linux-defender-security-center-advanced-features-settings.png":::

## <a name="how-to-explore-the-features"></a>Cómo explorar las características

1. Obtenga información sobre cómo [proteger su organización frente a amenazas web](web-threat-protection.md) mediante la protección contra amenazas web.
   - La protección contra amenazas web forma parte de la protección web en Microsoft Defender para punto de conexión. Usa la protección de red para proteger los dispositivos frente a amenazas web.
2. Ejecute el flujo [Indicadores personalizados de compromiso](indicator-ip-domain.md) para obtener bloques en el tipo indicador personalizado.
3. Explorar el [filtrado de contenido web](web-content-filtering.md).
   > [!NOTE]
   > Si va a quitar una directiva o cambiar grupos de dispositivos al mismo tiempo, esto podría provocar un retraso en la implementación de directivas.
   > Sugerencia profesional: puede implementar una directiva sin seleccionar ninguna categoría en un grupo de dispositivos. Esta acción creará una directiva de solo auditoría para ayudarle a comprender el comportamiento del usuario antes de crear una directiva de bloque.
4. [Integre Microsoft Defender para punto de conexión con Defender for Cloud Apps](/defender-cloud-apps/mde-integration) y los dispositivos macOS habilitados para la protección de red tendrán funcionalidades de cumplimiento de directivas de punto de conexión.
   > [!NOTE]
   > La detección y otras características no se admiten actualmente en estas plataformas.

## <a name="scenarios"></a>Escenarios

Los siguientes escenarios se admiten durante la versión preliminar pública:

### <a name="web-threat-protection"></a>Protección contra amenazas web

La protección contra amenazas web forma parte de la protección web en Microsoft Defender para punto de conexión. Usa la protección de red para proteger los dispositivos frente a amenazas web. Al integrarse con Microsoft Edge y exploradores populares de terceros como Chrome y Firefox, la protección contra amenazas web detiene las amenazas web sin un proxy web. La protección contra amenazas web puede proteger los dispositivos mientras están en el entorno local o fuera de ellos. La protección contra amenazas web detiene el acceso a los siguientes tipos de sitios:

- sitios de phishing
- vectores de malware
- sitios de vulnerabilidades de seguridad
- sitios que no son de confianza o de baja reputación
- sitios que ha bloqueado en la lista de indicadores personalizados

>:::image type="content" source="images/network-protection-reports-web-protection.png" alt-text="Web Protection notifica detecciones de amenazas web." lightbox="images/network-protection-reports-web-protection.png":::

Para obtener más información, consulte [Protección de su organización frente a amenazas web](web-threat-protection.md).

#### <a name="custom-indicators-of-compromise"></a>Indicadores personalizados de peligro  

El indicador de coincidencia de peligro (IoC) es una característica esencial en todas las soluciones de Endpoint Protection. Esta funcionalidad ofrece a SecOps la capacidad de establecer una lista de indicadores para la detección y el bloqueo (prevención y respuesta).

Cree indicadores que definan la detección, prevención y exclusión de entidades. Puede definir la acción que se va a realizar, así como la duración de la aplicación de la acción y el ámbito del grupo de dispositivos al que se va a aplicar.

Los orígenes admitidos actualmente son el motor de detección en la nube de Defender para punto de conexión, el motor de investigación y corrección automatizado y el motor de prevención de puntos de conexión (Antivirus de Microsoft Defender).

>:::image type="content" source ="images/network-protection-add-url-domain-indicator.png" alt-text="Muestra el indicador de adición de dirección URL o dominio de protección de red." lightbox="images/network-protection-add-url-domain-indicator.png":::

Para obtener más información, vea: [Crear indicadores para direcciones IP y direcciones URL/dominios](indicator-ip-domain.md).

### <a name="web-content-filtering"></a>Filtrado de contenido web

El filtrado de contenido web forma parte de las funcionalidades de [protección web](web-protection-overview.md) en Microsoft Defender para punto de conexión y Microsoft Defender para Empresas. El filtrado de contenido web permite a su organización realizar un seguimiento y regular el acceso a sitios web en función de sus categorías de contenido. Muchos de estos sitios web (incluso si no son malintencionados) pueden ser problemáticos debido a las regulaciones de cumplimiento, el uso del ancho de banda u otros problemas.

Configure directivas en los grupos de dispositivos para bloquear determinadas categorías. El bloqueo de una categoría impide que los usuarios de grupos de dispositivos especificados accedan a las direcciones URL asociadas a la categoría. Para cualquier categoría que no esté bloqueada, las direcciones URL se auditan automáticamente. Los usuarios pueden acceder a las direcciones URL sin interrupciones y recopilará estadísticas de acceso para ayudar a crear una decisión de directiva más personalizada. Los usuarios verán una notificación de bloque si un elemento de la página que están viendo realiza llamadas a un recurso bloqueado.

El filtrado de contenido web está disponible en los principales exploradores web, con bloques realizados por Windows Defender SmartScreen (Microsoft Edge) y Network Protection (Chrome, Firefox, Brave y Opera). Para obtener más información sobre la compatibilidad con exploradores, consulte [Requisitos previos](#prerequisites).

> :::image type="content" source="images/network-protection-wcf-add-policy.png" alt-text="Muestra la directiva de adición de filtrado de contenido web de protección de red." lightbox="images/network-protection-wcf-add-policy.png":::

Para obtener más información sobre los informes, vea [Filtrado de contenido web](web-content-filtering.md).

### <a name="microsoft-defender-for-cloud-applications"></a>Aplicaciones de Microsoft Defender para la nube

Microsoft Defender for Cloud Applications/Cloud App Catalog identifica las aplicaciones que desea que se advierta a los usuarios finales al acceder con Microsoft 365 Defender para punto de conexión y las marque como _Supervisadas_. Los dominios enumerados en aplicaciones supervisadas se sincronizarán más adelante con Microsoft 365 Defender para punto de conexión:

> :::image type="content" source="images/network-protection-macos-mcas-monitored-apps.png" alt-text="Muestra las aplicaciones supervisadas de mcas de protección de red." lightbox="images/network-protection-macos-mcas-monitored-apps.png":::

En un plazo de entre 10 y 15 minutos, estos dominios se mostrarán en Microsoft 365 Defender para Endpoint Security Center en Indicadores > direcciones URL o dominios con Action=Warn. Dentro del acuerdo de nivel de servicio de cumplimiento (consulte los detalles al final de este artículo).

> :::image type="content" source="images/network-protection-macos-mcas-cloud-app-security.png" alt-text="Muestra la seguridad de aplicaciones en la nube de mcas de protección de red." lightbox="images/network-protection-macos-mcas-cloud-app-security.png":::

## <a name="see-also"></a>Vea también

- [Proteger la red](network-protection.md)
- [Habilitar protección de red](enable-network-protection.md)
- [Protección web](web-protection-overview.md)
- [Crear indicadores](manage-indicators.md)
- [Filtrado de contenido web](web-content-filtering.md)
- [Microsoft Defender para punto de conexión en Linux](microsoft-defender-endpoint-linux.md)
