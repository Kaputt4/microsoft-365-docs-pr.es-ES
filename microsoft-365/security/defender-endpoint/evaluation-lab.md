---
title: laboratorio de evaluación de Microsoft Defender para punto de conexión
description: Obtenga información sobre las funcionalidades de Microsoft Defender para punto de conexión, ejecute simulaciones de ataque y vea cómo impide, detecta y corrige las amenazas.
keywords: evaluate Microsoft Defender para punto de conexión, evaluation, lab, simulation, windows 10, windows server 2019, evaluation lab
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.service: microsoft-365-security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-evalutatemtp
- highpri
ms.topic: article
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 2920bd6c5d8c9426bf33a17e574fe2c08b82f468
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67693001"
---
# <a name="microsoft-defender-for-endpoint-evaluation-lab"></a>laboratorio de evaluación de Microsoft Defender para punto de conexión

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-enablesiem-abovefoldlink)

La realización de una evaluación completa de productos de seguridad puede ser un proceso complejo que requiere una configuración de entorno y dispositivo complicada antes de que se pueda realizar realmente una simulación de ataque de un extremo a otro. Agregar a la complejidad es el desafío del seguimiento en el que las actividades de simulación, las alertas y los resultados se reflejan durante la evaluación.

El laboratorio de evaluación de Microsoft Defender para punto de conexión está diseñado para eliminar las complejidades de la configuración de dispositivos y entornos para que pueda centrarse en evaluar las funcionalidades de la plataforma, ejecutar simulaciones y ver las características de prevención, detección y corrección en acción.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4qLUM]

Con la experiencia de configuración simplificada, puede centrarse en la ejecución de sus propios escenarios de prueba y en las simulaciones creadas previamente para ver cómo funciona Defender para punto de conexión.

Tendrá acceso completo a las eficaces funcionalidades de la plataforma, como investigaciones automatizadas, búsqueda avanzada y análisis de amenazas, lo que le permite probar la pila de protección completa que Ofrece Defender para punto de conexión.

Puede agregar dispositivos Windows 10, Windows 11, Windows Server 2019, Windows Server 2016 y Linux (Ubuntu) preconfigurados para tener instaladas las versiones más recientes del sistema operativo y los componentes de seguridad adecuados, así como Office 2019 Standard.

También puede instalar simuladores de amenazas. Defender for Endpoint se ha asociado con plataformas de simulación de amenazas líderes del sector para ayudarle a probar las funcionalidades de Defender para punto de conexión sin tener que salir del portal.

Instale su simulador preferido, ejecute escenarios en el laboratorio de evaluación y vea al instante cómo funciona la plataforma, todo ello convenientemente disponible sin costo adicional para usted. También tendrá acceso cómodo a una amplia matriz de simulaciones a las que puede acceder y ejecutar desde el catálogo de simulaciones.

## <a name="before-you-begin"></a>Antes de empezar

Deberá cumplir los [requisitos de licencia](minimum-requirements.md#licensing-requirements) o tener acceso de prueba a Microsoft Defender para punto de conexión para acceder al laboratorio de evaluación.

Debe tener permisos **de administración de la configuración de seguridad** para:

- Creación del laboratorio
- Creación de dispositivos
- Restablecer contraseña
- Creación de simulaciones

Si ha habilitado el control de acceso basado en rol (RBAC) y ha creado al menos un grupo de máquinas, los usuarios deben tener acceso a Todos los grupos de máquinas.

Para obtener más información, consulte [Creación y administración de roles](user-roles.md).

¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-main-abovefoldlink)

## <a name="get-started-with-the-lab"></a>Introducción al laboratorio

Puede acceder al laboratorio desde el menú. En el menú de navegación, seleccione **Evaluación y tutoriales > laboratorio de evaluación**.

> [!NOTE]
>
> - Dependiendo del tipo de estructura de entorno que seleccione, los dispositivos estarán disponibles para el número especificado de horas desde el día de activación.
> - Cada entorno se aprovisiona con un conjunto limitado de dispositivos de prueba. Cuando haya usado los dispositivos aprovisionados y los haya eliminado, puede solicitar más dispositivos.
> - Puede solicitar recursos de laboratorio una vez al mes.

¿Ya tienes un laboratorio? Asegúrese de habilitar los nuevos simuladores de amenazas y de tener dispositivos activos.

## <a name="setup-the-evaluation-lab"></a>Configuración del laboratorio de evaluación

1. En el panel de navegación, seleccione **Evaluación & tutoriales** \> **Laboratorio de evaluación** y, a continuación, seleccione **Laboratorio de configuración**.

   :::image type="content" source="../../media/evaluationtutormenu.png" alt-text="Página de bienvenida del laboratorio de evaluación" lightbox="../../media/evaluationtutormenu.png":::

2. En función de las necesidades de evaluación, puede optar por configurar un entorno con menos dispositivos durante un período más largo o más dispositivos durante un período más corto. Seleccione la configuración de laboratorio que prefiera y, a continuación, seleccione **Siguiente**.

    :::image type="content" source="images/lab-creation-page.png" alt-text="Opciones de configuración de laboratorio" lightbox="images/lab-creation-page.png":::

3. (Opcional) Puede optar por instalar simuladores de amenazas en el laboratorio.

    :::image type="content" source="images/install-agent.png" alt-text="Página del agente de instalación de simuladores" lightbox="images/install-agent.png":::

   > [!IMPORTANT]
   > Primero deberá aceptar y dar su consentimiento a los términos y las declaraciones de uso compartido de información.

4. Seleccione el agente de simulación de amenazas que desea usar y escriba los detalles. También puede optar por instalar simuladores de amenazas más adelante. Si decide instalar agentes de simulación de amenazas durante la configuración del laboratorio, disfrutará de la ventaja de que se instalen convenientemente en los dispositivos que agregue.

   :::image type="content" source="images/lab-setup-summary.png" alt-text="Página de resumen" lightbox="images/lab-setup-summary.png":::

5. Revise el resumen y seleccione **Laboratorio de configuración**.

Una vez completado el proceso de instalación del laboratorio, puede agregar dispositivos y ejecutar simulaciones.

## <a name="add-devices"></a>Agregar dispositivos

Al agregar un dispositivo a su entorno, Defender para punto de conexión configura un dispositivo bien configurado con detalles de conexión. Puede agregar Windows 10, Windows 11, Windows Server 2019, Windows Server 2016 y Linux (Ubuntu).

El dispositivo se configurará con la versión más actualizada del sistema operativo y Office 2019 Standard, así como con otras aplicaciones como Java, Python y SysIntenals.

Si decide agregar un simulador de amenazas durante la configuración del laboratorio, todos los dispositivos tendrán instalado el agente del simulador de amenazas en los dispositivos que agregue.

El dispositivo se incorporará automáticamente al inquilino con los componentes de seguridad de Windows recomendados activados y en modo de auditoría, sin ningún esfuerzo por su parte.

Los siguientes componentes de seguridad están preconfigurados en los dispositivos de prueba:

- [Reducción de la superficie expuesta a ataques](attack-surface-reduction.md)
- [Bloqueo a primera vista](configure-block-at-first-sight-microsoft-defender-antivirus.md)
- [Acceso controlado a carpetas](controlled-folders.md)
- [Protección contra vulnerabilidades de seguridad](enable-exploit-protection.md)
- [Protección de red](network-protection.md)
- [Detección de aplicaciones potencialmente no deseadas](detect-block-potentially-unwanted-apps-microsoft-defender-antivirus.md)
- [Protección entregada en la nube](cloud-protection-microsoft-defender-antivirus.md)
- [SmartScreen de Microsoft Defender](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview)

> [!NOTE]
> Antivirus de Microsoft Defender estará activado (no en modo de auditoría). Si Antivirus de Microsoft Defender impide que ejecute la simulación, puede desactivar la protección en tiempo real en el dispositivo a través de Seguridad de Windows. Para obtener más información, vea [Configurar la protección always-on](configure-real-time-protection-microsoft-defender-antivirus.md).

La configuración de investigación automatizada dependerá de la configuración del inquilino. Se configurará para que esté semiauto automatizado de forma predeterminada. Para obtener más información, consulte [Introducción a las investigaciones automatizadas](automated-investigations.md).

> [!NOTE]
> La conexión a los dispositivos de prueba se realiza mediante RDP. Asegúrese de que la configuración del firewall permite conexiones RDP.

1. En el panel, seleccione **Agregar dispositivo**.

2. Elija el tipo de dispositivo que se va a agregar. Puede elegir agregar Windows 10, Windows 11, Windows Server 2019, Windows Server 2016 y Linux (Ubuntu).

   :::image type="content" source="../../media/add-machine-optionsnew.png" alt-text="Configuración del laboratorio con opciones de dispositivo" lightbox="../../media/add-machine-optionsnew.png":::

   > [!NOTE]
   > Si algo va mal con el proceso de creación de dispositivos, se le notificará y tendrá que enviar una nueva solicitud. Si se produce un error en la creación del dispositivo, no se contará con la cuota total permitida.

3. Se muestran los detalles de conexión. Seleccione **Copiar** para guardar la contraseña del dispositivo.

   > [!NOTE]
   > La contraseña solo se muestra una vez. Asegúrese de guardarlo para su uso posterior.

    :::image type="content" source="../../media/add-machine-eval-lab-new.png" alt-text="El dispositivo agregado con detalles de conexión" lightbox="../../media/add-machine-eval-lab-new.png":::

4. Comienza la configuración del dispositivo. Esto puede tardar aproximadamente 30 minutos.

5. Para ver el estado de los dispositivos de prueba, los niveles de riesgo y exposición, y el estado de las instalaciones del simulador, seleccione la pestaña **Dispositivos** .

   :::image type="content" source="images/machines-tab.png" alt-text="Pestaña Dispositivos" lightbox="images/machines-tab.png":::
    

   > [!TIP]
   > En la columna **Estado del simulador** , puede mantener el puntero sobre el icono de información para conocer el estado de instalación de un agente.


## <a name="add-a-domain-controller"></a>Agregar un controlador de dominio 

Agregue un controlador de dominio para ejecutar escenarios complejos, como movimiento lateral y ataques de varias fases en varios dispositivos.


>[!NOTE]
>La compatibilidad con dominios solo está disponible en el portal de Microsoft 365 Defender (security.microsoft.com).

1. En el panel, seleccione **Agregar dispositivo**.

2. Seleccione **Windows Server 2019** y, a continuación, seleccione **Establecer como controlador de dominio**. 

3. Cuando se haya aprovisionado el controlador de dominio, podrá crear dispositivos unidos a un dominio haciendo clic en **Agregar dispositivo**. A continuación, seleccione Windows 10/Windows 11 y seleccione **Unirse al dominio**. 

>[!NOTE]
>Solo se puede vivir un controlador de dominio a la vez. El dispositivo de controlador de dominio permanecerá en directo siempre y cuando haya un dispositivo en directo conectado a él.



## <a name="request-for-more-devices"></a>Solicitud de más dispositivos

Cuando se usan y eliminan todos los dispositivos existentes, puede solicitar más dispositivos. Puede solicitar recursos de laboratorio una vez al mes.

1. En el panel del laboratorio de evaluación, seleccione **Solicitar más dispositivos**.

   :::image type="content" source="images/request-more-devices.png" alt-text="Opción de solicitud para más dispositivos" lightbox="images/request-more-devices.png":::

2. Elija la configuración.
3. Envíe la solicitud.

Cuando la solicitud se envíe correctamente, verá un banner de confirmación verde y la fecha del último envío.

Puede encontrar el estado de la solicitud en la pestaña **Acciones del usuario** , que se aprobará en cuestión de horas.

Cuando se aprueben, los dispositivos solicitados se agregarán a la configuración del laboratorio y podrá crear más dispositivos.

> [!TIP]
> Para sacar más partido del laboratorio, no olvide consultar nuestra biblioteca de simulaciones.

## <a name="simulate-attack-scenarios"></a>Simulación de escenarios de ataque

Use los dispositivos de prueba para ejecutar sus propias simulaciones de ataque conectándose a ellos.

Puede simular escenarios de ataque mediante:

- Los [escenarios de ataque "Do It Yourself"](https://security.microsoft.com/tutorials/all)
- Simuladores de amenazas

También puede usar [la búsqueda avanzada](advanced-hunting-overview.md) para consultar datos y [análisis de amenazas](threat-analytics.md) para ver informes sobre amenazas emergentes.

### <a name="do-it-yourself-attack-scenarios"></a>Escenarios de ataque por sí mismo

Si está buscando una simulación pre-hecha, puede usar nuestros escenarios de [ataque "Do It Yourself"](https://security.microsoft.com/tutorials/all). Estos scripts son seguros, documentados y fáciles de usar. Estos escenarios reflejarán las funcionalidades de Defender para punto de conexión y le guiarán por la experiencia de investigación.

> [!NOTE]
> La conexión a los dispositivos de prueba se realiza mediante RDP. Asegúrese de que la configuración del firewall permite conexiones RDP.

1. Conéctese al dispositivo y ejecute una simulación de ataque seleccionando **Conectar**.

    :::image type="content" source="images/test-machine-table.png" alt-text="Botón Conectar para los dispositivos de prueba" lightbox="images/test-machine-table.png":::


   :::image type="content" source="images/remote-connection.png" alt-text="Pantalla de conexión a Escritorio remoto" lightbox="images/remote-connection.png":::

    Para **dispositivos Linux**: deberá usar un cliente SSH local y el comando proporcionado. 


    > [!NOTE]
    > Si no tiene una copia de la contraseña guardada durante la configuración inicial, puede restablecer la contraseña seleccionando **Restablecer contraseña** en el menú:
    >
    > :::image type="content" source="images/reset-password-test-machine.png" alt-text="La opción Restablecer contraseña" lightbox="images/reset-password-test-machine.png":::
    >
    > El dispositivo cambiará su estado a "Ejecución del restablecimiento de contraseña" y, a continuación, se le presentará la nueva contraseña en unos minutos.

3. Escriba la contraseña que se mostró durante el paso de creación del dispositivo.

   :::image type="content" source="images/enter-password.png" alt-text="Pantalla en la que se escriben las credenciales" lightbox="images/enter-password.png":::

4. Ejecute simulaciones de ataque do-it-yourself en el dispositivo.

### <a name="threat-simulator-scenarios"></a>Escenarios del simulador de amenazas

Si decide instalar cualquiera de los simuladores de amenazas admitidos durante la configuración del laboratorio, puede ejecutar las simulaciones integradas en los dispositivos de laboratorio de evaluación.

La ejecución de simulaciones de amenazas mediante plataformas de terceros es una buena manera de evaluar las capacidades Microsoft Defender para punto de conexión dentro de los límites de un entorno de laboratorio.

> [!NOTE]
>
> Para poder ejecutar simulaciones, asegúrese de que se cumplen los siguientes requisitos:
>
> - Los dispositivos deben agregarse al laboratorio de evaluación
> - Los simuladores de amenazas deben instalarse en el laboratorio de evaluación

1. En el portal, seleccione **Crear simulación**.

2. Seleccione un simulador de amenazas.

   :::image type="content" source="images/select-simulator.png" alt-text="Selección del simulador de amenazas" lightbox="images/select-simulator.png":::

3. Elija una simulación o examine la galería de simulaciones para examinar las simulaciones disponibles.

    Puede llegar a la galería de simulación desde:
    - El panel de evaluación principal del icono **información general sobre simulaciones** o
    - Si navega desde el panel de navegación **Evaluación y tutoriales** \> **Simulación & tutoriales**, seleccione **Catálogo de simulaciones**.

4. Seleccione los dispositivos en los que desea ejecutar la simulación.

5. Seleccione **Crear simulación**.

6. Para ver el progreso de una simulación, seleccione la pestaña **Simulaciones** . Vea el estado de la simulación, las alertas activas y otros detalles.

   :::image type="content" source="images/simulations-tab.png" alt-text="Pestaña Simulaciones" lightbox="images/simulations-tab.png":::

Después de ejecutar las simulaciones, le recomendamos que recorra la barra de progreso del laboratorio y explore **Microsoft Defender para punto de conexión desencadenó una investigación y corrección automatizadas**. Consulte las pruebas recopiladas y analizadas por la característica.

Busque pruebas de ataque mediante la búsqueda avanzada mediante el lenguaje de consulta enriquecido y la telemetría sin procesar y consulte algunas amenazas de todo el mundo documentadas en Análisis de amenazas.

## <a name="simulation-gallery"></a>Galería de simulación

Microsoft Defender para punto de conexión se ha asociado con varias plataformas de simulación de amenazas para proporcionarle acceso cómodo para probar las funcionalidades de la plataforma desde el portal.

Para ver todas las simulaciones disponibles, vaya al catálogo  **Simulaciones y tutoriales** \> **Simulaciones**  en el menú.

Se muestra una lista de agentes de simulación de amenazas de terceros compatibles y se proporcionan tipos específicos de simulaciones junto con descripciones detalladas en el catálogo.

Puede ejecutar convenientemente cualquier simulación disponible directamente desde el catálogo.

:::image type="content" source="images/simulations-catalog.png" alt-text="Catálogo de simulaciones" lightbox="images/simulations-catalog.png":::

Cada simulación incluye una descripción detallada del escenario de ataque y referencias como las técnicas de ataque de MITRE usadas y las consultas de búsqueda avanzada de ejemplo que se ejecutan.

**Ejemplos:**

:::image type="content" source="images/simulation-details-aiq.png" alt-text="Ejemplo del panel de detalles de la descripción de la simulación para los métodos de persistencia" lightbox="images/simulation-details-aiq.png":::

:::image type="content" source="images/simulation-details-sb.png" alt-text="Detalles de la descripción de la simulación para APT29" lightbox="images/simulation-details-sb.png":::

## <a name="evaluation-report"></a>Informe de evaluación

Los informes de laboratorio resumen los resultados de las simulaciones realizadas en los dispositivos.

:::image type="content" source="images/eval-report.png" alt-text="Informe de evaluación" lightbox="images/eval-report.png":::

De un vistazo, podrá ver rápidamente lo siguiente:

- Incidentes que se desencadenaron
- Alertas generadas
- Evaluaciones sobre el nivel de exposición
- Categorías de amenazas observadas
- Fuentes de detección
- Investigaciones automatizadas

## <a name="provide-feedback"></a>Enviar comentarios

Sus comentarios nos ayudan a mejorar la protección de su entorno frente a ataques avanzados. Comparta su experiencia e impresiones de las funcionalidades del producto y los resultados de evaluación.

Háganos saber lo que piensa; para ello, seleccione **Proporcionar comentarios**.

:::image type="content" source="images/send-us-feedback-eval-lab.png" alt-text="Página de comentarios" lightbox="images/send-us-feedback-eval-lab.png":::
