---
title: Simulador de ataques en Microsoft Defender para Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: da5845db-c578-4a41-b2cb-5a09689a551b
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden aprender a usar Attack Simulator para ejecutar ataques simulados de suplantación de identidad y contraseña en sus organizaciones de Microsoft 365 E5 o Microsoft Defender para Office 365 Plan 2.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7c88a5df6fae61e1ffe70214ad4a73deef4b380e
ms.sourcegitcommit: 6e4ddf35aaf747599f476f9988bcef02cacce1b6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/11/2021
ms.locfileid: "50717607"
---
# <a name="attack-simulator-in-microsoft-defender-for-office-365"></a>Simulador de ataques en Microsoft Defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a** [Microsoft Defender para Office 365 plan 2](office-365-atp.md)

Si su organización tiene Microsoft Defender para Office 365 Plan 2, que incluye capacidades de investigación de amenazas y [respuesta,](office-365-ti.md)puede usar Attack Simulator en el Centro de seguridad & Cumplimiento para ejecutar escenarios de ataque realistas en su organización. Estos ataques simulados pueden ayudarte a identificar y encontrar usuarios vulnerables antes de que un ataque real impacte en la línea de fondo. Lea este artículo para obtener más información.

> [!NOTE]
>
> Attack Simulator, tal como se describe en este  artículo, es ahora de solo lectura y ha sido reemplazado por el aprendizaje de simulación de ataque en el nodo de colaboración Email **&** en el Centro de seguridad de [Microsoft 365](https://security.microsoft.com). Para obtener más información, vea [Get started using Attack simulation training](attack-simulation-training-get-started.md).
>
> Se ha deshabilitado la capacidad de iniciar nuevas simulaciones desde esta versión de Attack Simulator. Sin embargo, aún puede acceder a informes durante un máximo de 90 días a partir del 24 de enero de 2021.

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Para abrir el Centro de seguridad y cumplimiento, vaya a <https://protection.office.com/>. El simulador de ataque está disponible en **el simulador de ataque de administración** de \> **amenazas.** Vaya directamente al simulador de ataque, abra <https://protection.office.com/attacksimulator> .

- Para obtener más información sobre la disponibilidad de Attack Simulator en diferentes suscripciones de Microsoft 365, vea Descripción del servicio de [Microsoft Defender para Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).

- Debe ser miembro de los grupos de roles **Administración** de la organización o Administrador **de** seguridad. Para obtener más información acerca de los grupos de roles en el Centro de seguridad y cumplimiento, consulte [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).

- La cuenta debe configurarse para la autenticación multifactor (MFA) para crear y administrar campañas en Attack Simulator. Para obtener instrucciones, vea [Configurar la autenticación multifactor](../../admin/security-and-compliance/set-up-multi-factor-authentication.md).

- Attack Simulator solo funciona en buzones basados en la nube.

- Las campañas de suplantación de identidad recopilarán y procesarán eventos durante 30 días. Los datos históricos de la campaña estarán disponibles hasta 90 días después de iniciar la campaña.

- Los datos relacionados con la simulación de ataques y el aprendizaje se almacenan con otros datos de clientes para los servicios de Microsoft 365. Para obtener más información, [vea Ubicaciones de datos de Microsoft 365](/microsoft-365/enterprise/o365-data-locations).

- No hay cmdlets de PowerShell correspondientes para Attack Simulator.

## <a name="spear-phishing-campaigns"></a>Campañas de suplantación de identidad de lanza

*Phishing* es un término genérico para ataques de correo electrónico que intentan robar información confidencial en mensajes que parecen ser de remitentes legítimos o de confianza. *El phishing* de lanza es un ataque de suplantación de identidad dirigido que usa contenido centrado y personalizado que se adapta específicamente a los destinatarios dirigidos (normalmente, después del reconocimiento de los destinatarios por parte del atacante).

En Attack Simulator, hay disponibles dos tipos diferentes de campañas de suplantación de identidad de lanza:

- **Phishing de lanza (recolección de credenciales):** el ataque intenta convencer a los destinatarios para que haga clic en una dirección URL del mensaje. Si hacen clic en el vínculo, se les pedirá que escriban sus credenciales. Si lo hacen, se les traslada a una de las siguientes ubicaciones:

  - Una página predeterminada que explica que se trataba de una prueba y proporciona sugerencias para reconocer mensajes de suplantación de identidad.

    ![Qué ven los usuarios si hacen clic en el vínculo de suplantación de identidad (phishing) y escriben sus credenciales](../../media/attack-simulator-phishing-result.png)

  - Una página personalizada (DIRECCIÓN URL) que especifique.

- **Phishing de lanza (datos adjuntos):** el ataque intenta convencer a los destinatarios para que abran un archivo adjunto .docx o .pdf en el mensaje. Los datos adjuntos contienen el mismo contenido del vínculo de suplantación de identidad predeterminado, pero la primera oración comienza por " , estás viendo este mensaje como un mensaje de correo electrónico reciente \<Display Name\> que has abierto...".

> [!NOTE]
> Actualmente, las campañas de suplantación de identidad de lanza en Attack Simulator no expiran.

### <a name="create-a-spear-phishing-campaign"></a>Crear una campaña de suplantación de identidad

Una parte importante de cualquier campaña de suplantación de identidad de lanza es la apariencia del mensaje de correo electrónico que se envía a los destinatarios de destino. Para crear y configurar el mensaje de correo electrónico, tiene estas opciones:

- **Use una plantilla de correo electrónico integrada:** hay disponibles dos plantillas integradas: **Entrega** de premios y **Actualización de nómina.** Puedes personalizar aún más algunas, todas o ninguna de las propiedades de correo electrónico de la plantilla al crear e iniciar la campaña.

- **Crear una plantilla de correo electrónico** reutilizable: después de crear y guardar la plantilla de correo electrónico, puede usarla de nuevo en futuras campañas de suplantación de identidad de lanza. Puedes personalizar aún más algunas, todas o ninguna de las propiedades de correo electrónico de la plantilla al crear e iniciar la campaña.

- **Cree el mensaje de correo electrónico en el** asistente: puede crear el mensaje de correo electrónico directamente en el asistente al crear e iniciar la campaña de suplantación de identidad de lanza.

#### <a name="step-1-optional-create-a-custom-email-template"></a>Paso 1 (opcional): crear una plantilla de correo electrónico personalizada

Si va a usar una de las plantillas integradas o crear el mensaje de correo electrónico directamente en el asistente, puede omitir este paso.

1. En el Centro de seguridad & cumplimiento, vaya al Simulador **de ataques de administración** de \> **amenazas.**

2. En la **página Simular** ataques, en las secciones **Phishing de lanza (recolección** de credenciales) o Phishing de lanza **(datos** adjuntos), haga clic en **Detalles de ataque**.

   No importa dónde cree la plantilla. Las opciones disponibles en la plantilla son las mismas para ambos tipos de ataques de suplantación de identidad.

3. En la página **Detalles de** ataque que se abre, en la sección Plantillas **de** suplantación de identidad, en el área Crear plantillas, haga clic **en Nueva plantilla**. 

4. El **Asistente para configurar plantilla de suplantación** de identidad comienza en un nuevo control desplegable. En el **paso Inicio,** escriba un nombre para mostrar único para la plantilla y, a continuación, haga clic **en Siguiente**.

5. En el **paso Configurar detalles de correo** electrónico, configure las siguientes opciones:

   - **From (Name):** el nombre para mostrar que se usa para el remitente del mensaje.

   - **From (Email):** la dirección de correo electrónico del remitente.

   - Dirección URL del servidor de inicio de sesión **de phishing:** haga clic en la lista desplegable y seleccione una de las direcciones URL disponibles de la lista. Esta es la dirección URL en la que los usuarios tendrán la tentación de hacer clic. Las opciones son:

     - <http://portal.docdeliveryapp.com>
     - <http://portal.docdeliveryapp.net>
     - <http://portal.docstoreinternal.com>
     - <http://portal.docstoreinternal.net>
     - <http://portal.hardwarecheck.net>
     - <http://portal.hrsupportint.com>
     - <http://portal.payrolltooling.com>
     - <http://portal.payrolltooling.net>
     - <http://portal.prizegiveaway.net>
     - <http://portal.prizesforall.com>
     - <http://portal.salarytoolint.com>
     - <http://portal.salarytoolint.net>

     > [!NOTE]
     >
     > Un servicio de reputación de direcciones URL puede identificar una o varias de estas direcciones URL como no seguras. Compruebe la disponibilidad de la dirección URL en los exploradores web compatibles antes de usar la dirección URL en una campaña de suplantación de identidad.

   - **Dirección URL de página de aterrizaje** personalizada: escriba una página de aterrizaje opcional en la que los usuarios se toman si hacen clic en el vínculo de suplantación de identidad y escriben sus credenciales. Este vínculo reemplaza la página de aterrizaje predeterminada. Por ejemplo, si tiene formación de reconocimiento interno, puede especificar esa dirección URL aquí.

   - **Categoría:** actualmente, esta configuración no se usa (se omite cualquier cosa que escriba).

   - **Asunto:** el **campo Asunto** del mensaje de correo electrónico.

   Cuando termine, haga clic en **Siguiente**.

6. En el **paso Redacción de correo** electrónico, cree el cuerpo del mensaje de correo electrónico. Puede usar la pestaña **Correo** electrónico (un editor HTML enriquecido) o la **pestaña** Origen (código HTML sin formato).

   El formato HTML puede ser tan simple o complejo como sea necesario. Puede insertar imágenes y texto para mejorar la fiabilidad del mensaje en el cliente de correo electrónico del destinatario.

   - `${username}` inserta el nombre del destinatario.

   - `${loginserverurl}` inserta el valor de la dirección URL del servidor de inicio de **sesión de phishing** del paso anterior.

   Cuando termine, haga clic en **Siguiente**.

7. En el **paso Confirmar,** haga clic **en Finalizar**.

#### <a name="step-2-create-and-launch-the-spear-phishing-campaign"></a>Paso 2: Crear e iniciar la campaña de suplantación de identidad

1. En el Centro de seguridad & cumplimiento, vaya al Simulador **de ataques de administración** de \> **amenazas.**

2. En la **página Simular ataques,** realice una de las siguientes selecciones en función del tipo de campaña que desee crear:

   - En la **sección Phishing de lanza (recolección** de credenciales), haga clic **en Iniciar ataque** o haga clic en Ataque de inicio **detalles** de \> **ataque.**

   - En la sección Phishing de lanza **(datos adjuntos),** haga clic **en Iniciar ataque** o haga clic en **Detalles de** ataque \> **Iniciar ataque**.

3. El **Asistente para configurar ataques de** suplantación de identidad comienza en un nuevo flyout. En el **paso** Inicio, siga uno de los pasos siguientes:

   - En el **cuadro** Nombre, escriba un nombre para mostrar único para la campaña. No haga clic en **Usar plantilla**, porque creará el mensaje de correo electrónico más adelante en el asistente.

   - Haga **clic en Usar plantilla** y seleccione una plantilla de correo electrónico integrada o personalizada. Después de seleccionar la plantilla, **el** cuadro Nombre se rellena automáticamente en función de la plantilla, pero puede cambiar el nombre.

   > [!div class="mx-imgBorder"]
   > ![Página de inicio de phishing](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)

   Cuando termine, haga clic en **Siguiente**.

4. En el **paso Destinatarios de** destino, siga uno de estos pasos:

   - Haga **clic en Libreta de** direcciones para seleccionar los destinatarios (usuarios o grupos) de la campaña. Cada destinatario de destino debe tener un buzón de Exchange Online. Si hace clic **en Filtrar y** **aplicar** sin especificar un criterio de búsqueda, todos los destinatarios se devuelven y se agregan a la campaña.

   - Haga **clic en** Importar **y,** a continuación, en Importar archivo para importar un valor separado por comas (CSV) o un archivo de direcciones de correo electrónico separados por líneas. Cada línea debe contener la dirección de correo electrónico del destinatario.

   Cuando termine, haga clic en **Siguiente**.

5. En el **paso Configurar detalles de correo** electrónico, configure las siguientes opciones:

   Si seleccionó una plantilla en el paso **Inicio,** la mayoría de estos valores ya están configurados, pero puede cambiarlos.

   - **From (Name):** el nombre para mostrar que se usa para el remitente del mensaje.

   - **From (Email):** la dirección de correo electrónico del remitente. Puede escribir una dirección de correo electrónico real o falsa desde el dominio de correo electrónico de su organización o puede escribir una dirección de correo electrónico externa real o falsa. Una dirección de correo electrónico del remitente válida de su organización se resolverá realmente en el cliente de correo electrónico del destinatario.

   - Dirección URL del servidor de inicio de sesión **de phishing:** haga clic en la lista desplegable y seleccione una de las direcciones URL disponibles de la lista. Esta es la dirección URL en la que los usuarios tendrán la tentación de hacer clic. Las opciones son:

     - <http://portal.docdeliveryapp.com>
     - <http://portal.docdeliveryapp.net>
     - <http://portal.docstoreinternal.com>
     - <http://portal.docstoreinternal.net>
     - <http://portal.hardwarecheck.net>
     - <http://portal.hrsupportint.com>
     - <http://portal.payrolltooling.com>
     - <http://portal.payrolltooling.net>
     - <http://portal.prizegiveaway.net>
     - <http://portal.prizesforall.com>
     - <http://portal.salarytoolint.com>
     - <http://portal.salarytoolint.net>

     > [!NOTE]
     >
     > - Todas las direcciones URL son http intencionadamente, no https.
     >
     > - Un servicio de reputación de direcciones URL puede identificar una o varias de estas direcciones URL como no seguras. Compruebe la disponibilidad de la dirección URL en los exploradores web compatibles antes de usar la dirección URL en una campaña de suplantación de identidad.
     >
     > - Es necesario seleccionar una dirección URL. En el caso de las campañas de **phishing (datos adjuntos),** puedes quitar el vínculo del  cuerpo del mensaje en el siguiente paso (de lo contrario, el mensaje contendrá un vínculo y un archivo adjunto).

   - **Tipo de datos adjuntos:** esta configuración solo está disponible en campañas **de phishing de** lanza (datos adjuntos). Haga clic en la lista desplegable y seleccione **. DOCX** o **. PDF** de la lista.

   - **Nombre de datos adjuntos:** esta configuración solo está disponible en campañas **de phishing (datos adjuntos)** de Lanza. Escriba un nombre de archivo para los datos adjuntos .docx o .pdf.

   - **Dirección URL de página de aterrizaje** personalizada: escriba una página de aterrizaje opcional en la que los usuarios se toman si hacen clic en el vínculo de suplantación de identidad y escriben sus credenciales. Este vínculo reemplaza la página de aterrizaje predeterminada. Por ejemplo, si tiene formación de reconocimiento interno, puede especificar esa dirección URL aquí.

   - **Asunto:** el **campo Asunto** del mensaje de correo electrónico.

   Cuando termine, haga clic en **Siguiente**.

6. En el **paso Redacción de correo** electrónico, cree el cuerpo del mensaje de correo electrónico. Si seleccionó una plantilla en el paso **Inicio,** el cuerpo del mensaje ya está configurado, pero puede personalizarlo. Puede usar la pestaña **Correo** electrónico (un editor HTML enriquecido) o la **pestaña** Origen (código HTML sin formato).

   El formato HTML puede ser tan simple o complejo como sea necesario. Puede insertar imágenes y texto para mejorar la fiabilidad del mensaje en el cliente de correo electrónico del destinatario.

   - `${username}` inserta el nombre del destinatario.

   - `${loginserverurl}`inserta el valor **de la dirección URL del servidor de inicio de sesión de phishing.**

   Para las campañas de suplantación de identidad **(datos adjuntos),** debes quitar el vínculo  del cuerpo del mensaje (de lo contrario, el mensaje contendrá un vínculo y un archivo adjunto, y los clics de vínculo no se realizarán en una campaña de datos adjuntos).

   > [!div class="mx-imgBorder"]
   > ![Redacción del cuerpo del correo electrónico](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)

   Cuando termine, haga clic en **Siguiente**.

7. En el **paso Confirmar,** haga clic **en Finalizar** para iniciar la campaña. El mensaje de suplantación de identidad se entrega a los destinatarios de destino.

## <a name="password-attack-campaigns"></a>Campañas de ataque con contraseña

Un *ataque de contraseña* intenta adivinar las contraseñas de las cuentas de usuario de una organización, normalmente después de que el atacante haya identificado una o más cuentas de usuario válidas.

En Attack Simulator, hay dos tipos diferentes de campañas de ataque con contraseña disponibles para probar la complejidad de las contraseñas de los usuarios:

- Contraseña de fuerza bruta (ataque  de **diccionario):** una fuerza bruta o un ataque de diccionario usa un archivo de diccionario grande de contraseñas en una cuenta de usuario con la esperanza de que una de ellas funcione (muchas contraseñas en una cuenta).  Los bloqueos incorrectos de contraseñas ayudan a disuadir los ataques de contraseña de fuerza bruta.

  Para el ataque de diccionario, puede especificar una o varias contraseñas para probar (introducidas manualmente o en un archivo cargado) y puede especificar uno o varios usuarios.

- **Ataque de spray de contraseña:** un ataque de *spray* de contraseña usa la misma contraseña cuidadosamente considerada en una lista de cuentas de usuario (una contraseña en muchas cuentas). Los ataques de spray de contraseñas son más difíciles de detectar que los ataques de contraseña de fuerza bruta (la probabilidad de éxito aumenta cuando un atacante intenta una contraseña en decenas o cientos de cuentas sin el riesgo de que se bloquee la contraseña incorrecta del usuario).

  Para el ataque de spray de contraseña, solo puede especificar una contraseña para probar y puede especificar uno o varios usuarios.

> [!NOTE]
> Los ataques de contraseña en Attack Simulator pasan solicitudes de autenticación básicas de nombre de usuario y contraseña a un punto de conexión, por lo que también funcionan con otros métodos de autenticación (AD FS, sincronización de hash de contraseña, paso a través, PingFederate, etc.). Para los usuarios que tienen MFA habilitado, incluso si el ataque de contraseña intenta su contraseña real, el  intento siempre se registrará como un error (es decir, los usuarios de MFA nunca aparecerán en el recuento de intentos correctos de la campaña). Este es el resultado esperado. MFA es un método principal para ayudar a proteger contra ataques de contraseña.

### <a name="create-and-launch-a-password-attack-campaign"></a>Crear e iniciar una campaña de ataque de contraseña

1. En el Centro de seguridad & cumplimiento, vaya al Simulador **de ataques de administración** de \> **amenazas.**

2. En la **página Simular ataques,** realice una de las siguientes selecciones en función del tipo de campaña que desee crear:

   - En la sección Contraseña de fuerza bruta **(ataque** de diccionario), haga clic **en Iniciar ataque** o haga clic en **Detalles** de ataque \> **Iniciar ataque**.

   - en la **sección Ataque de spray de contraseña,** haga clic en Iniciar **ataque** o haga clic en **Detalles de** ataque Iniciar \> **ataque**.

3. El **Asistente para configurar ataque de** contraseña comienza en un nuevo menú desplegable. En el **paso Inicio,** escriba un nombre para mostrar único para la campaña y, a continuación, haga clic **en Siguiente**.

4. En el **paso Usuarios de** destino, siga uno de estos pasos:

   - Haga **clic en Libreta de** direcciones para seleccionar los destinatarios (usuarios o grupos) de la campaña. Cada destinatario de destino debe tener un buzón de Exchange Online. Si hace clic **en Filtrar y** **aplicar** sin especificar un criterio de búsqueda, todos los destinatarios se devuelven y se agregan a la campaña.

   - Haga **clic en** Importar **y,** a continuación, en Importar archivo para importar un valor separado por comas (CSV) o un archivo de direcciones de correo electrónico separados por líneas. Cada línea debe contener la dirección de correo electrónico del destinatario.

   Cuando termine, haga clic en **Siguiente**.

5. En el **paso Elegir configuración de** ataque, elija qué hacer en función del tipo de campaña:

   - **Contraseña de fuerza bruta (ataque de diccionario):** realice uno de los pasos siguientes:

     - **Escribir contraseñas manualmente:** en el **cuadro Presione entrar para agregar** una contraseña, escriba una contraseña y, a continuación, presione ENTRAR. Repita este paso tantas veces como sea necesario.

     - **Cargar contraseñas desde un archivo de diccionario:** haga **clic** en Cargar para importar un archivo de texto existente que contenga una contraseña en cada línea y una última línea en blanco. El archivo de texto debe tener 10 MB o menos de tamaño y no puede contener más de 30000 contraseñas.

   - **Ataque de spray de** contraseña: en **las contraseñas que** se deben usar en el cuadro de ataque, escriba una contraseña.

   Cuando termine, haga clic en **Siguiente**.

6. En el **paso Confirmar,** haga clic **en Finalizar** para iniciar la campaña. Las contraseñas que especificó se probarán en los usuarios que especificó.

## <a name="view-campaign-results"></a>Ver los resultados de la campaña

Después de iniciar una campaña, puedes comprobar el progreso y los resultados en la página **principal Simular ataques.**

Las campañas activas mostrarán una barra de estado, un valor de porcentaje completado y el recuento "(usuarios completados) de (usuarios totales)". Al hacer clic **en el** botón Actualizar se actualizará el progreso de las campañas activas. También puedes hacer clic en **Finalizar** para detener una campaña activa.

Una vez finalizada la campaña, el estado cambia a **Ataque completado.** Para ver los resultados de la campaña, haga una de las siguientes acciones:

- En la página **principal Simular ataques,** haga clic en **Ver informe** bajo el nombre de la campaña.

- En la página **principal Simular ataques,** haga clic **en Detalles de** ataque en la sección para el tipo de ataque. En la **página Detalles de** ataque que se abre, selecciona la campaña en la sección Historial **de** ataques.

Cualquiera de las acciones anteriores te llevará a una página denominada **Detalles de ataque.** La información disponible en esta página para cada tipo de campaña se describe en las secciones siguientes.

### <a name="spear-phishing-credentials-harvest-campaign-results"></a>Resultados de campaña de phishing de lanza (recolección de credenciales)

La siguiente información está disponible en la página **Detalles de ataque** para cada campaña:

- Duración (fecha/hora de inicio y fecha/hora de finalización) de la campaña.

- **Total de usuarios dirigidos**

- **Intentos correctos:** el número de usuarios que hicieron clic en el **vínculo** e introdujeron sus credenciales *(cualquier valor* de nombre de usuario y contraseña).

- **Tasa de éxito general:** porcentaje calculado por **intentos correctos**  /  **Los usuarios totales destinados** a .

- **Haga clic más** rápido: cuánto tiempo tardó el primer usuario en hacer clic en el vínculo después de iniciar la campaña.

- **Promedio de clic:** la suma de cuánto tiempo tardó todo el mundo en hacer clic en el vínculo dividido por el número de usuarios que hicieron clic en el vínculo.

- **Haga clic en Tasa de** éxito: porcentaje calculado por (número de usuarios que han hecho clic en el vínculo) / Total de usuarios **dirigidos**.

- **Credenciales más rápidas:** cuánto tiempo tardó el primer usuario en escribir sus credenciales después de iniciar la campaña.

- **Promedio de credenciales:** la suma del tiempo que todos tardaron en escribir sus credenciales divididas por el número de usuarios que introdujeron sus credenciales.

- **Tasa de éxito de credenciales:** porcentaje calculado por (número de usuarios que especificaron sus credenciales) / **Total de usuarios dirigidos**.

- Gráfico de barras que muestra los números **de vínculos y** **credenciales proporcionados** por día.

- Gráfico de círculo que muestra los **porcentajes Vínculo hecho clic,** **Credencial** suministrada y **Ninguno** para la campaña.

- En **la sección Usuarios comprometidos** se enumeran los detalles de los usuarios que han hecho clic en el vínculo:

  - La dirección de correo electrónico del usuario

  - La fecha y hora en que hicieron clic en el vínculo.

  - Dirección IP del cliente.

  - Detalles sobre la versión del usuario de Windows y el explorador web.

  Puede hacer clic **en Exportar** para exportar los resultados a un archivo CSV.

### <a name="spear-phishing-attachment-campaign-results"></a>Resultados de campaña de phishing (datos adjuntos) de Spear

La siguiente información está disponible en la página **Detalles de ataque** para cada campaña:

- Duración (fecha/hora de inicio y fecha/hora de finalización) de la campaña.

- **Total de usuarios dirigidos**

- **Intentos correctos:** el número de usuarios que abrieron o descargaron y abrieron los datos adjuntos (la vista previa no cuenta).

- **Tasa de éxito general:** porcentaje calculado por **intentos correctos**  /  **Los usuarios totales destinados** a .

- **Tiempo de apertura de datos adjuntos más** rápido: cuánto tiempo tardó el primer usuario en abrir los datos adjuntos después de iniciar la campaña.

- **Tiempo medio de apertura de** datos adjuntos: la suma de cuánto tiempo tardó todo el mundo en abrir los datos adjuntos dividido por el número de usuarios que abrieron los datos adjuntos.

- **Tasa de éxito de** apertura de datos adjuntos: porcentaje calculado por (número de usuarios que abrieron los datos adjuntos) / **Total de usuarios dirigidos**.

### <a name="brute-force-password-dictionary-attack-campaign-results"></a>Resultados de la campaña Fuerza bruta de contraseña (ataque de diccionario)

La siguiente información está disponible en la página **Detalles de ataque** para cada campaña:

- Duración (fecha/hora de inicio y fecha/hora de finalización) de la campaña.

- **Total de usuarios dirigidos**

- **Intentos correctos:** el número de usuarios que se encontró que estaban usando una de las contraseñas especificadas.

- **Tasa de éxito general:** porcentaje calculado por **intentos correctos**  /  **Los usuarios totales destinados** a .

- La **sección Usuarios en peligro** enumera las direcciones de correo electrónico de los usuarios afectados. Puede hacer clic **en Exportar** para exportar los resultados a un archivo CSV.

### <a name="password-spray-attack-campaign-results"></a>Resultados de la campaña de ataque por spray de contraseña

La siguiente información está disponible en la página **Detalles de ataque** para cada campaña:

- Duración (fecha/hora de inicio y fecha/hora de finalización) de la campaña.

- **Total de usuarios dirigidos**

- **Intentos correctos:** el número de usuarios que se encontró que estaban usando la contraseña especificada.

- **Tasa de éxito general:** porcentaje calculado por **intentos correctos**  /  **Los usuarios totales destinados** a .
