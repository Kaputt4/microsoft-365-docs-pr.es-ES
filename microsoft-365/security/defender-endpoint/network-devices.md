---
title: Detección de dispositivos de red y administración de vulnerabilidades
description: Las recomendaciones de seguridad y la detección de vulnerabilidades ya están disponibles para sistemas operativos de conmutadores, enrutadores, controladores WLAN y firewalls.
keywords: dispositivos de red, detección de vulnerabilidades de dispositivos de red, sistemas operativos de conmutadores, enrutadores, controladores WLAN y firewalls
ms.prod: m365-security
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
ms.technology: mde
ms.openlocfilehash: 2affbe19484348a511487930d034da6799ca348c
ms.sourcegitcommit: 282f3a58b8e11615b3e53328e6b89a6ac52008e9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/17/2021
ms.locfileid: "61560235"
---
# <a name="network-device-discovery-and-vulnerability-management"></a>Detección de dispositivos de red y administración de vulnerabilidades

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Administración de amenazas y vulnerabilidades](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-portaloverview-abovefoldlink)

> [!NOTE]
> El Blog sobre detección de [dispositivos](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/network-device-discovery-and-vulnerability-assessments/ba-p/2267548) de red y evaluaciones de vulnerabilidad publicado \( el 04-13-2021 proporciona información sobre las nuevas capacidades de detección de dispositivos de red en \) Defender para endpoint.  En este artículo se proporciona  información general sobre el desafío que la detección de dispositivos de red está diseñada para abordar e información detallada sobre cómo empezar a usar estas nuevas funcionalidades.

Las funcionalidades de detección de red están disponibles en la sección **Inventario** de dispositivos del <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">portal de</a> Microsoft 365 Defender y Microsoft 365 Defender consolas.

Se usará un dispositivo designado de Microsoft Defender para endpoint en cada segmento de red para realizar exámenes periódicos autenticados de dispositivos de red preconfigurados. Una vez descubierto, las capacidades de Defender for Endpoint Administración de amenazas y vulnerabilidades proporcionan flujos de trabajo integrados para proteger conmutadores detectados, enrutadores, controladores WLAN, firewalls y puertas de enlace VPN.

Una vez detectados y clasificados los dispositivos de red, los administradores de seguridad podrán recibir las recomendaciones de seguridad más recientes y revisar las vulnerabilidades detectadas recientemente en los dispositivos de red implementados en sus organizaciones.

## <a name="approach"></a>Enfoque

Los dispositivos de red no se administran como puntos de conexión estándar, ya que Defender for Endpoint no tiene un sensor integrado en los propios dispositivos de red. Estos tipos de dispositivos requieren un enfoque sin agente donde un examen remoto obtendrá la información necesaria de los dispositivos. Según la topología y las características de red, un solo dispositivo o algunos dispositivos incorporados a Microsoft Defender para Endpoint realizarán exámenes autenticados de dispositivos de red mediante SNMP (solo lectura).

Habrá dos tipos de dispositivos a tener en cuenta:

- **Dispositivo de evaluación:** un dispositivo que ya está incorporado y que usarás para examinar los dispositivos de red.
- **Dispositivos de** red: los dispositivos de red que tiene previsto examinar e incorporar.

### <a name="vulnerability-management-for-network-devices"></a>Administración de vulnerabilidades para dispositivos de red

Una vez detectados y clasificados los dispositivos de red, los administradores de seguridad podrán recibir las recomendaciones de seguridad más recientes y revisar las vulnerabilidades detectadas recientemente en los dispositivos de red implementados en sus organizaciones.

## <a name="operating-systems-that-are-supported"></a>Sistemas operativos compatibles

Actualmente se admiten los siguientes sistemas operativos:

- Cisco IOS, IOS-XE, NX-OS
- Juniper JUNOS
- HPE ArubaOS, Software de conmutador procurve
- Palo Alto Networks PAN-OS

Se agregarán más proveedores de redes y sos con el tiempo, en función de los datos recopilados por el uso del cliente. Por lo tanto, se recomienda configurar todos los dispositivos de red, incluso si no están especificados en esta lista.

## <a name="how-to-get-started"></a>Como empezar

El primer paso es seleccionar un dispositivo que realizará los exámenes de red autenticados.

1. Decide un dispositivo integrado de Defender for Endpoint (cliente o servidor) que tenga una conexión de red al puerto de administración de los dispositivos de red que planeas examinar.

2. Se debe permitir el tráfico SNMP entre el dispositivo de evaluación de Defender para endpoints y los dispositivos de red de destino (por ejemplo, mediante el Firewall).

3. Decida qué dispositivos de red se evaluarán para las vulnerabilidades (por ejemplo: un conmutador cisco o un firewall de Palo Alto Networks).

4. Asegúrese de que SNMP de solo lectura está habilitado en todos los dispositivos de red configurados para permitir que el dispositivo de evaluación de Defender for Endpoint consulte los dispositivos de red configurados. La "escritura SNMP" no es necesaria para la funcionalidad adecuada de esta característica.

5. Obtener las direcciones IP de los dispositivos de red que se van a examinar (o las subredes donde se implementan estos dispositivos).

6. Obtenga las credenciales SNMP de los dispositivos de red (por ejemplo: Community String, noAuthNoPriv, authNoPriv, authPriv). Tendrás que proporcionar las credenciales al configurar un nuevo trabajo de evaluación.

7. Configuración del cliente proxy: no se requiere ninguna configuración adicional que no sea los requisitos de proxy de dispositivo defender para extremo.

8. Para permitir que el escáner de red se autentique y funcione correctamente, es esencial que agregue los siguientes dominios o direcciones URL:

    - login.windows.net
    - \*.security.microsoft.com
    - login.microsoftonline.com
    - \*.blob.core.windows.net/networkscannerstable/\*

    > [!NOTE]
    > No todas las direcciones URL se especifican en la lista documentada Defender for Endpoint de la colección de datos permitida.

## <a name="permissions"></a>Permissions

Para configurar trabajos de evaluación, se requiere la siguiente opción de permiso de usuario: **Administrar la configuración de seguridad en Defender**. Para encontrar el permiso, vaya a **Configuración** \> **Roles**. Para obtener más información, vea [Create and manage roles for role-based access control](user-roles.md).

## <a name="install-the-network-scanner"></a>Instalar el escáner de red

1. Vaya a Microsoft 365 **de Configuración** de evaluación de puntos de conexión \>  \>  \>  (en **Evaluaciones de red).**
    1. En el portal Microsoft 365 Defender, vaya a la página Configuración > trabajos de evaluación.

2. Descargue el escáner de red e instállo en el dispositivo de evaluación de Defender para endpoint designado.

    > [!div class="mx-imgBorder"]
    > ![Botón Descargar escáner.](images/assessment-jobs-download-scanner.png)

## <a name="network-scanner-installation--registration"></a>Instalación del escáner de red & registro

El proceso de inicio de sesión se puede completar en el propio dispositivo de evaluación designado o en cualquier otro dispositivo (por ejemplo, el dispositivo cliente personal).

Para completar el proceso de registro del escáner de red:

1. Copie y siga la dirección URL que aparece en la línea de comandos y use el código de instalación proporcionado para completar el proceso de registro.

    > [!NOTE]
    > Es posible que deba cambiar la configuración del símbolo del sistema para poder copiar la dirección URL.

2. Escriba el código e inicie sesión con una cuenta de Microsoft que tenga el permiso Defender for Endpoint denominado "Administrar la configuración de seguridad en Defender".

3. Cuando haya terminado, debería ver un mensaje que confirme que ha iniciado sesión.

## <a name="configure-a-new-assessment-job"></a>Configurar un nuevo trabajo de evaluación

En la página Trabajos de evaluación **de Configuración**, seleccione Agregar trabajo de evaluación **de red**. Siga el proceso de configuración para elegir los dispositivos de red que se examinarán periódicamente y se agregarán al inventario de dispositivos.

Para evitar la duplicación de dispositivos en el inventario de dispositivos de red, asegúrese de que cada dirección IP esté configurada solo una vez en varios dispositivos de evaluación.

> [!div class="mx-imgBorder"]
> ![Botón Agregar trabajo de evaluación de red.](images/assessment-jobs-add.png)

Adición de pasos de trabajo de evaluación de red:

1. Elige un nombre de "Trabajo de evaluación" y el "Dispositivo de evaluación" en el que se instaló el escáner de red. Este dispositivo realizará los exámenes periódicos autenticados.

2. Agregue las direcciones IP de los dispositivos de red de destino que se van a examinar (o las subredes donde se implementan estos dispositivos).

3. Agregue las credenciales SNMP necesarias de los dispositivos de red de destino.

4. Guarde el trabajo de evaluación de red recién configurado para iniciar el examen periódico de red.

### <a name="scan-and-add-network-devices"></a>Examinar y agregar dispositivos de red

Durante el proceso de configuración, puede realizar un examen de prueba de una sola vez para comprobar que:

- Hay conectividad entre el dispositivo de evaluación de Defender para endpoints y los dispositivos de red de destino configurados.
- Las credenciales SNMP configuradas son correctas.

Cada dispositivo de evaluación puede admitir hasta 1.500 direcciones IP correctas. Por ejemplo, si analiza 10 subredes diferentes donde solo 100 direcciones IP devuelven resultados correctos, podrá examinar 1.400 direcciones IP adicionales de otras subredes en el mismo dispositivo de evaluación.

Si hay varios intervalos de direcciones IP/subredes que examinar, los resultados del examen de prueba tardarán varios minutos en aparecer. Un examen de prueba estará disponible para hasta 1.024 direcciones.

Una vez que se muestren los resultados, puedes elegir qué dispositivos se incluirán en el examen periódico. Si omites ver los resultados del examen, todas las direcciones IP configuradas se agregarán al trabajo de evaluación de red (independientemente de la respuesta del dispositivo). Los resultados del examen también se pueden exportar.

## <a name="device-inventory"></a>Inventario de dispositivos

Los dispositivos recién detectados se mostrarán en la nueva **pestaña Dispositivos de** red en la **página Inventario de** dispositivos. Puede tardar hasta dos horas después de agregar un trabajo de evaluación hasta que los dispositivos se actualicen.

> [!div class="mx-imgBorder"]
> ![Sección Dispositivos de red en el inventario de dispositivos.](images/assessment-jobs-device-inventory.png)

## <a name="troubleshooting"></a>Solución de problemas

### <a name="network-scanner-installation-has-failed"></a>Error en la instalación del escáner de red

Compruebe que las direcciones URL necesarias se agregan a los dominios permitidos en la configuración del firewall. Además, asegúrate de que las opciones de proxy estén configuradas como se describe en [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md).

### <a name="the-microsoftcomdevicelogin-web-page-did-not-show-up"></a>La Microsoft.com/devicelogin web no se hizo

Compruebe que las direcciones URL necesarias se agregan a los dominios permitidos en el firewall. Además, asegúrate de que las opciones de proxy estén configuradas como se describe en [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md).

### <a name="network-devices-are-not-shown-in-the-device-inventory-after-several-hours"></a>Los dispositivos de red no se muestran en el inventario de dispositivos después de varias horas

Los resultados del examen deben actualizarse unas horas después del examen inicial que se realizó después de completar la configuración del trabajo de evaluación.

Si aún no se muestran dispositivos, compruebe que el servicio 'MdatpNetworkScanService' se está ejecutando en los dispositivos de evaluación, en los que instaló el escáner de red, y realice un "Examen de ejecución" en la configuración del trabajo de evaluación correspondiente.

Si aún no obtiene resultados después de 5 minutos, reinicie el servicio.

### <a name="devices-last-seen-time-is-longer-than-24-hours"></a>El tiempo de vista por última vez de los dispositivos es de más de 24 horas

Valide que el escáner se está ejecutando correctamente. A continuación, vaya a la definición de examen y seleccione "Ejecutar prueba". Compruebe qué mensajes de error devuelven de las direcciones IP relevantes.

### <a name="required-threat-and-vulnerability-management-user-permission"></a>Permiso Administración de amenazas y vulnerabilidades usuario requerido

El registro finalizó con un error: "Parece que no tiene permisos suficientes para agregar un nuevo agente. El permiso requerido es "Administrar la configuración de seguridad en Defender".

Presione cualquier tecla para salir.

Pida al administrador del sistema que le asigne los permisos necesarios. Como alternativa, pida a otro miembro relevante que le ayude con el proceso de inicio de sesión proporcionando el código de inicio de sesión y el vínculo.

### <a name="registration-process-fails-using-provided-link-in-the-command-line-in-registration-process"></a>Error en el proceso de registro mediante el vínculo proporcionado en la línea de comandos en el proceso de registro

Pruebe con otro explorador o copie el vínculo de inicio de sesión y el código en un dispositivo diferente.

### <a name="text-too-small-or-cant-copy-text-from-command-line"></a>Texto demasiado pequeño o no puede copiar texto de la línea de comandos

Cambia la configuración de la línea de comandos en el dispositivo para permitir la copia y el tamaño del texto.

## <a name="related-articles"></a>Artículos relacionados

- [Inventario de dispositivos](machines-view-overview.md)
- [Configurar funciones avanzadas](advanced-features.md)
