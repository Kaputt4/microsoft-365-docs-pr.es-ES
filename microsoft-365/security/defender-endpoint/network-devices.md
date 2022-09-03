---
title: Detección de dispositivos de red y administración de vulnerabilidades
description: Las recomendaciones de seguridad y la detección de vulnerabilidades ahora están disponibles para los sistemas operativos de conmutadores, enrutadores, controladores WLAN y firewalls.
keywords: dispositivos de red, detección de vulnerabilidades de dispositivos de red, sistemas operativos de conmutadores, enrutadores, controladores WLAN y firewalls
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: levinec
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.custom: admindeeplinkDEFENDER
ms.topic: conceptual
ms.subservice: mde
ms.openlocfilehash: 3806daf2cc4e0a7dbb277943cf3aa1a3abe70fb9
ms.sourcegitcommit: d3ef9391f621e8f4ca70661184b3bb82c6cbda94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2022
ms.locfileid: "67577219"
---
# <a name="network-device-discovery-and-vulnerability-management"></a>Detección de dispositivos de red y administración de vulnerabilidades

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Administración de vulnerabilidades de Defender](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-portaloverview-abovefoldlink)

> [!NOTE]
> El blog [Detección de dispositivos de red y evaluaciones de vulnerabilidades](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/network-device-discovery-and-vulnerability-assessments/ba-p/2267548) publicado 04-13-2021\) proporciona información sobre las nuevas funcionalidades de **detección de dispositivos de red** en Defender para punto de conexión.\( En este artículo se proporciona información general sobre el desafío que está diseñado para abordar la **detección de dispositivos de red** e información detallada sobre cómo empezar a usar estas nuevas funcionalidades.

Las funcionalidades de detección de red están disponibles en la sección **Inventario** de dispositivos del <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">portal de Microsoft 365 Defender</a> y Microsoft 365 Defender consolas.

Se usará un dispositivo Microsoft Defender para punto de conexión designado en cada segmento de red para realizar exámenes autenticados periódicos de dispositivos de red preconfigurados. Una vez detectado, las funcionalidades de administración de vulnerabilidades de Defender para punto de conexión proporcionan flujos de trabajo integrados para proteger los conmutadores detectados, enrutadores, controladores WLAN, firewalls y puertas de enlace de VPN.

Una vez detectados y clasificados los dispositivos de red, los administradores de seguridad podrán recibir las recomendaciones de seguridad más recientes y revisar las vulnerabilidades detectadas recientemente en los dispositivos de red implementados en sus organizaciones.

## <a name="approach"></a>Enfoque

Los dispositivos de red no se administran como puntos de conexión estándar, ya que Defender para punto de conexión no tiene un sensor integrado en los propios dispositivos de red. Estos tipos de dispositivos requieren un enfoque sin agente donde un examen remoto obtendrá la información necesaria de los dispositivos. En función de la topología de red y las características, un solo dispositivo o algunos dispositivos incorporados a Microsoft Defender para punto de conexión realizarán exámenes autenticados de los dispositivos de red mediante SNMP (solo lectura).

Habrá dos tipos de dispositivos que debe tener en cuenta:

- **Dispositivo de evaluación**: dispositivo que ya está incorporado y que usará para examinar los dispositivos de red.
- **Dispositivos de red**: los dispositivos de red que tiene previsto examinar e incorporar.

### <a name="vulnerability-management-for-network-devices"></a>Administración de vulnerabilidades para dispositivos de red

Una vez detectados y clasificados los dispositivos de red, los administradores de seguridad podrán recibir las recomendaciones de seguridad más recientes y revisar las vulnerabilidades detectadas recientemente en los dispositivos de red implementados en sus organizaciones.

## <a name="operating-systems-that-are-supported"></a>Sistemas operativos compatibles

Actualmente se admiten los siguientes sistemas operativos:

- Cisco IOS, IOS-XE, NX-OS
- Juniper JUNOS
- HPE ArubaOS, software de conmutador de procurva
- Palo Alto Networks PAN-OS

Con el tiempo se agregarán más proveedores de redes y sistema operativo, en función de los datos recopilados del uso del cliente. Por lo tanto, se recomienda configurar todos los dispositivos de red, incluso si no se especifican en esta lista.

## <a name="how-to-get-started"></a>Como empezar

El primer paso consiste en seleccionar un dispositivo que realizará los exámenes de red autenticados.

1. Decida un dispositivo incorporado de Defender para punto de conexión (cliente o servidor) que tenga una conexión de red al puerto de administración para los dispositivos de red que planea examinar.

2. El tráfico SNMP entre el dispositivo de evaluación de Defender para punto de conexión y los dispositivos de red de destino debe permitirse (por ejemplo, mediante el firewall).

3. Decida qué dispositivos de red se evaluarán en busca de vulnerabilidades (por ejemplo: un conmutador Cisco o un firewall de Palo Alto Networks).

4. Asegúrese de que SNMP de solo lectura está habilitado en todos los dispositivos de red configurados para permitir que el dispositivo de evaluación de Defender para punto de conexión consulte los dispositivos de red configurados. La "escritura SNMP" no es necesaria para la funcionalidad adecuada de esta característica.

5. Obtenga las direcciones IP de los dispositivos de red que se van a examinar (o las subredes donde se implementan estos dispositivos).

6. Obtenga las credenciales snmp de los dispositivos de red (por ejemplo: Community String, noAuthNoPriv, authNoPriv, authPriv). Se le pedirá que proporcione las credenciales al configurar un nuevo trabajo de evaluación.

7. Configuración del cliente proxy: no se requiere ninguna configuración adicional que no sea los requisitos de proxy de dispositivo de Defender para punto de conexión.

8. Para permitir que el analizador de red se autentique y funcione correctamente, es esencial agregar los siguientes dominios o direcciones URL:

    - login.windows.net
    - \*.security.microsoft.com
    - login.microsoftonline.com
    - \*.blob.core.windows.net/networkscannerstable/\*

    > [!NOTE]
    > No todas las direcciones URL se especifican en la lista documentada de Defender para punto de conexión de la recopilación de datos permitida.

## <a name="permissions"></a>Permisos

Para configurar los trabajos de evaluación, se requiere la siguiente opción de permiso de usuario: **Administrar la configuración de seguridad en Defender**. Para encontrar el permiso, vaya a **Roles de configuración**\>. Para obtener más información, vea [Crear y administrar roles para el control de acceso basado en roles](user-roles.md).

## <a name="install-the-network-scanner"></a>Instalación del analizador de red

1. Vaya a Trabajos de **evaluación** de puntos de **conexión** \> de **configuración** \> de seguridad \> de **Microsoft 365** (en **Evaluaciones de red**).
    1. En el portal de Microsoft 365 Defender, vaya a la página Configuración > Trabajos de evaluación.

2. Descargue el escáner de red e instálelo en el dispositivo de evaluación de Defender for Endpoint designado.

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/assessment-jobs-download-scanner.png" alt-text="Botón Descargar escáner" lightbox="images/assessment-jobs-download-scanner.png":::

## <a name="network-scanner-installation--registration"></a>Instalación del escáner de red & registro

El proceso de inicio de sesión se puede completar en el propio dispositivo de evaluación designado o en cualquier otro dispositivo (por ejemplo, el dispositivo cliente personal).

> [!NOTE]
> Tanto la cuenta con la que el usuario inicia sesión como el dispositivo que se usa para completar el proceso de inicio de sesión deben estar en el mismo inquilino donde el dispositivo se incorpora a Microsoft Defender para punto de conexión.

Para completar el proceso de registro del escáner de red:

1. Copie y siga la dirección URL que aparece en la línea de comandos y use el código de instalación proporcionado para completar el proceso de registro.

    > [!NOTE]
    > Es posible que tenga que cambiar la configuración del símbolo del sistema para poder copiar la dirección URL.

2. Escriba el código e inicie sesión con una cuenta de Microsoft que tenga el permiso de Defender para punto de conexión denominado "Administrar la configuración de seguridad en Defender".

3. Cuando haya terminado, verá un mensaje que confirma que ha iniciado sesión.

## <a name="configure-a-new-assessment-job"></a>Configuración de un nuevo trabajo de evaluación

En la página Trabajos de evaluación de **Configuración**, seleccione **Agregar trabajo de evaluación de red**. Siga el proceso de configuración para elegir los dispositivos de red que se examinarán periódicamente y se agregarán al inventario de dispositivos.

Para evitar la duplicación de dispositivos en el inventario de dispositivos de red, asegúrese de que cada dirección IP esté configurada solo una vez en varios dispositivos de evaluación.

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/assessment-jobs-add.png" alt-text="Botón Agregar trabajo de evaluación de red" lightbox="images/assessment-jobs-add.png":::

Adición de pasos de trabajo de evaluación de red:

1. Elija un nombre "Trabajo de evaluación" y el "Dispositivo de evaluación" en el que se instaló el escáner de red. Este dispositivo realizará los exámenes autenticados periódicamente.

2. Agregue direcciones IP de los dispositivos de red de destino que se van a examinar (o las subredes donde se implementan estos dispositivos).

3. Agregue las credenciales SNMP necesarias de los dispositivos de red de destino.

4. Guarde el trabajo de evaluación de red recién configurado para iniciar el examen periódico de red.

### <a name="scan-and-add-network-devices"></a>Examinar y agregar dispositivos de red

Durante el proceso de configuración, puede realizar un examen de prueba de una sola vez para comprobar que:

- Hay conectividad entre el dispositivo de evaluación de Defender para punto de conexión y los dispositivos de red de destino configurados.
- Las credenciales de SNMP configuradas son correctas.

Cada dispositivo de evaluación puede admitir hasta 1500 exámenes correctos de direcciones IP. Por ejemplo, si examina 10 subredes diferentes donde solo 100 direcciones IP devuelven resultados correctos, podrá examinar 1.400 direcciones IP adicionales de otras subredes en el mismo dispositivo de evaluación.

Si hay varios intervalos de direcciones IP o subredes que examinar, los resultados del examen de prueba tardarán varios minutos en aparecer. Un examen de prueba estará disponible para hasta 1024 direcciones.

Una vez que aparezcan los resultados, puede elegir qué dispositivos se incluirán en el examen periódico. Si omite la visualización de los resultados del examen, todas las direcciones IP configuradas se agregarán al trabajo de evaluación de red (independientemente de la respuesta del dispositivo). Los resultados del examen también se pueden exportar.

## <a name="device-inventory"></a>Inventario de dispositivos

Los dispositivos recién detectados se mostrarán en la nueva pestaña **Dispositivos de red** de la página **Inventario de** dispositivos. Puede tardar hasta dos horas después de agregar un trabajo de evaluación hasta que se actualicen los dispositivos.

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/assessment-jobs-device-inventory.png" alt-text="La sección Dispositivos de red del inventario de dispositivos" lightbox="images/assessment-jobs-device-inventory.png":::

## <a name="troubleshooting"></a>Solución de problemas

### <a name="network-scanner-installation-has-failed"></a>Error en la instalación del escáner de red

Compruebe que las direcciones URL necesarias se agregan a los dominios permitidos en la configuración del firewall. Además, asegúrese de que la configuración del proxy esté configurada como se describe en [Configuración del proxy de dispositivo y la conectividad a Internet](configure-proxy-internet.md).

### <a name="the-microsoftcomdevicelogin-web-page-did-not-show-up"></a>La página web de Microsoft.com/devicelogin no se mostró

Compruebe que las direcciones URL necesarias se agregan a los dominios permitidos en el firewall. Además, asegúrese de que la configuración del proxy esté configurada como se describe en [Configuración del proxy de dispositivo y la conectividad a Internet](configure-proxy-internet.md).

### <a name="network-devices-are-not-shown-in-the-device-inventory-after-several-hours"></a>Los dispositivos de red no se muestran en el inventario de dispositivos después de varias horas

Los resultados del examen deben actualizarse unas horas después del examen inicial que tuvo lugar después de completar la configuración del trabajo de evaluación.

Si aún no se muestran los dispositivos, compruebe que el servicio "MdatpNetworkScanService" se está ejecutando en los dispositivos de evaluación, en los que instaló el analizador de red, y realice un "Examen de ejecución" en la configuración del trabajo de evaluación pertinente.

Si sigue sin obtener resultados después de 5 minutos, reinicie el servicio.

### <a name="devices-last-seen-time-is-longer-than-24-hours"></a>El tiempo de la última vez que se ve en los dispositivos es superior a 24 horas

Compruebe que el escáner se ejecuta correctamente. A continuación, vaya a la definición del examen y seleccione "Ejecutar prueba". Compruebe qué mensajes de error se devuelven desde las direcciones IP pertinentes.

### <a name="required-defender-vulnerability-management-user-permission"></a>Permiso de usuario requerido de Administración de vulnerabilidades de Defender

El registro terminó con un error: "Parece que no tiene permisos suficientes para agregar un nuevo agente. El permiso necesario es "Administrar la configuración de seguridad en Defender".

Presione cualquier tecla para salir.

Pida al administrador del sistema que le asigne los permisos necesarios. Como alternativa, pida a otro miembro relevante que le ayude con el proceso de inicio de sesión proporcionándole el código y el vínculo de inicio de sesión.

### <a name="registration-process-fails-using-provided-link-in-the-command-line-in-registration-process"></a>Error en el proceso de registro mediante el vínculo proporcionado en la línea de comandos en el proceso de registro

Pruebe con otro explorador o copie el vínculo de inicio de sesión y el código en otro dispositivo.

### <a name="text-too-small-or-cant-copy-text-from-command-line"></a>Texto demasiado pequeño o no se puede copiar texto desde la línea de comandos

Cambie la configuración de la línea de comandos en el dispositivo para permitir la copia y cambiar el tamaño del texto.

## <a name="related-articles"></a>Artículos relacionados

- [Inventario de dispositivos](machines-view-overview.md)
- [Configurar funciones avanzadas](advanced-features.md)
