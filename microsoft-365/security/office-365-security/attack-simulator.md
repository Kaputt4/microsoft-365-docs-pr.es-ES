---
title: Simulador de ataques en Microsoft Defender para Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
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
description: Los administradores pueden aprender a usar el simulador de ataques para ejecutar ataques simulados de suplantación de identidad y contraseña en sus organizaciones de Microsoft 365 E5 o Microsoft Defender para Office 365 Plan 2.
ms.openlocfilehash: 2ffec891f7b1021f3c6c51b003c78aacb0ec0d6a
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794537"
---
# <a name="attack-simulator-in-microsoft-defender-for-office-365"></a>Simulador de ataques en Microsoft Defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

Si su organización tiene Microsoft Defender para Office 365 Plan 2, que incluye capacidades de investigación y respuesta de [amenazas,](office-365-ti.md)puede usar el Simulador de ataques en el Centro de seguridad & Cumplimiento para ejecutar escenarios de ataque realistas en su organización. Estos ataques simulados pueden ayudarte a identificar y encontrar usuarios vulnerables antes de que un ataque real repercuta en la línea inferior. Lea este artículo para obtener más información.

> [!NOTE]
> La simulación de ataques y los datos relacionados con la formación se almacenan con otros datos de clientes para los servicios de Microsoft 365. Para obtener más información, [vea ubicaciones de datos de Microsoft 365.](/microsoft-365/enterprise/o365-data-locations)

> [!TIP]
> La formación de simulación de ataques está disponible para la versión preliminar pública en el Centro de seguridad de Microsoft 365. Consulte [Simular un ataque de suplantación de identidad con Microsoft Defender para Office 365](attack-simulation-training.md) para obtener más información.

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Para abrir el Centro de seguridad y cumplimiento, vaya a <https://protection.office.com/>. El simulador de ataques está disponible en **el simulador de** \> **ataques de administración de amenazas.** Vaya directamente al simulador de ataques, abra <https://protection.office.com/attacksimulator> .

- Para obtener más información sobre la disponibilidad del Simulador de ataques en distintas suscripciones de Microsoft 365, vea la descripción del servicio [de Microsoft Defender para Office 365.](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)

- Debe ser miembro de los grupos de roles **Administración** de la organización o **Administrador de** seguridad. Para obtener más información acerca de los grupos de roles en el Centro de seguridad y cumplimiento, consulte [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).

- Tu cuenta debe configurarse para la autenticación multifactor (MFA) para crear y administrar campañas en el Simulador de ataques. Para obtener instrucciones, [vea Configurar la autenticación multifactor.](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication)

- Las campañas de suplantación de identidad recopilarán y procesarán eventos durante 30 días. Los datos históricos de la campaña estarán disponibles hasta 90 días después de iniciar la campaña.

- No hay ningún cmdlet de PowerShell correspondiente para el Simulador de ataques.

## <a name="spear-phishing-campaigns"></a>Campañas de suplantación de identidad

*La suplantación* de identidad es un término genérico para los ataques de correo electrónico que intentan robar información confidencial en mensajes que parecen ser de remitentes legítimos o de confianza. La suplantación de identidad *(phishing)* es un ataque de suplantación de identidad dirigido que usa contenido centrado y personalizado que se adapta específicamente a los destinatarios de destino (normalmente, después del reconocimiento del atacante a los destinatarios).

En el Simulador de ataques, hay disponibles dos tipos diferentes de campañas de suplantación de identidad de lanza:

- **Phishing de punta (recolección de credenciales):** el ataque intenta convencer a los destinatarios para que haga clic en una dirección URL en el mensaje. Si hacen clic en el vínculo, se les pedirá que escriban sus credenciales. Si lo hacen, se les traslada a una de las siguientes ubicaciones:

  - Una página predeterminada que explica que se trata de una prueba y ofrece sugerencias para reconocer mensajes de suplantación de identidad.

    ![Qué ven los usuarios si hacen clic en el vínculo de suplantación de identidad (phishing) y escriben sus credenciales](../../media/attack-simulator-phishing-result.png)

  - Una página personalizada (URL) que especifique.

- **Phishing de punta (datos adjuntos):** el ataque intenta convencer a los destinatarios para que abran un archivo adjunto .docx o .pdf en el mensaje. Los datos adjuntos contienen el mismo contenido del vínculo de suplantación de identidad predeterminado, pero la primera oración comienza con " , está viendo este mensaje como un mensaje de correo electrónico reciente que \<Display Name\> abrió...".

> [!NOTE]
> Actualmente, las campañas de suplantación de identidad de lanza en el simulador de ataques no expiran.

### <a name="create-a-spear-phishing-campaign"></a>Crear una campaña de suplantación de identidad

Una parte importante de cualquier campaña de phishing de lanza es la apariencia del mensaje de correo electrónico que se envía a los destinatarios de destino. Para crear y configurar el mensaje de correo electrónico, tiene estas opciones:

- **Use una plantilla de correo electrónico** integrada: hay disponibles dos plantillas integradas: **Giveaway y** Payroll **Update**. Puede personalizar aún más algunas, todas o ninguna de las propiedades de correo electrónico de la plantilla al crear e iniciar la campaña.

- **Cree una plantilla de correo electrónico** reutilizable: después de crear y guardar la plantilla de correo electrónico, puede usarla de nuevo en futuras campañas de suplantación de identidad (phishing). Puede personalizar aún más algunas, todas o ninguna de las propiedades de correo electrónico de la plantilla al crear e iniciar la campaña.

- **Cree el mensaje de correo electrónico en el** asistente: puede crear el mensaje de correo directamente en el asistente mientras crea e inicia la campaña de suplantación de identidad de lanza.

#### <a name="step-1-optional-create-a-custom-email-template"></a>Paso 1 (opcional): Crear una plantilla de correo electrónico personalizada

Si va a usar una de las plantillas integradas o crear el mensaje de correo electrónico directamente en el asistente, puede omitir este paso.

1. En el Centro de seguridad & cumplimiento, vaya al simulador **de** \> **ataques de administración de amenazas.**

2. En la **página Simular** ataques, en las secciones **Phishing (Recolección** de credenciales) o Phishing de lanza **(datos** adjuntos), haga clic en **Detalles de ataques.**

   No importa dónde cree la plantilla. Las opciones disponibles en la plantilla son las mismas para ambos tipos de ataques de suplantación de identidad.

3. En la página **Detalles de** ataques que se  abre, en la sección **Plantillas** de suplantación de identidad, en el área Crear plantillas, haga clic en **Nueva plantilla.**

4. El **Asistente para configurar plantillas de** suplantación de identidad se inicia en un nuevo control desplegable. En el **paso Inicio,** escriba un nombre para mostrar único para la plantilla y, a continuación, haga clic en **Siguiente**.

5. En el paso **Configurar detalles de** correo electrónico, configure las siguientes opciones:

   - **From (Name):** el nombre para mostrar que se usa para el remitente del mensaje.

   - **De (correo electrónico):** la dirección de correo electrónico del remitente.

   - **Dirección URL del servidor de inicio de** sesión de suplantación de identidad : haga clic en la lista desplegable y seleccione una de las direcciones URL disponibles en la lista. Esta es la dirección URL en la que los usuarios estarán tentados a hacer clic. Las opciones son:

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
     > Un servicio de reputación de dirección URL puede identificar una o varias de estas direcciones URL como no seguras. Compruebe la disponibilidad de la dirección URL en los exploradores web compatibles antes de usar la dirección URL en una campaña de suplantación de identidad.

   - **Dirección URL de la página de** aterrizaje personalizada: escriba una página de aterrizaje opcional en la que se toman los usuarios si hacen clic en el vínculo de suplantación de identidad y escriben sus credenciales. Este vínculo reemplaza la página de aterrizaje predeterminada. Por ejemplo, si tiene formación interna de reconocimiento, puede especificar esa dirección URL aquí.

   - **Categoría:** actualmente, no se usa esta configuración (se omite todo lo que escriba).

   - **Asunto:** el **campo Asunto** del mensaje de correo electrónico.

   Cuando termine, haga clic en **Siguiente**.

6. En el **paso Redactar correo** electrónico, cree el cuerpo del mensaje de correo electrónico. Puede usar la pestaña **Correo** electrónico (un editor HTML enriquecido) o la pestaña **Origen** (código HTML sin formato).

   El formato HTML puede ser tan simple o complejo como sea necesario. Puede insertar imágenes y texto para mejorar la fiabilidad del mensaje en el cliente de correo electrónico del destinatario.

   - `${username}` inserta el nombre del destinatario.

   - `${loginserverurl}` inserta el valor de la dirección URL del servidor de inicio de **sesión de suplantación** de identidad del paso anterior.

   Cuando termine, haga clic en **Siguiente**.

7. En el paso **Confirmar,** haga clic **en Finalizar**.

#### <a name="step-2-create-and-launch-the-spear-phishing-campaign"></a>Paso 2: Crear e iniciar la campaña de suplantación de identidad

1. En el Centro de seguridad & cumplimiento, vaya al simulador **de** \> **ataques de administración de amenazas.**

2. En la **página Simular ataques,** realiza una de las siguientes selecciones en función del tipo de campaña que quieras crear:

   - En la sección Phishing de lanza **(recolección** de credenciales), haga clic en **Iniciar** ataque o en Ataque de inicio **de detalles** de \> **ataque.**

   - En la sección Phishing de lanza **(datos adjuntos),** haga clic en **Iniciar** ataque o en Ataque de inicio **de detalles** de \> **ataque.**

3. El **Asistente para configurar ataques de** suplantación de identidad se inicia en un nuevo menú desplegable. En el **paso** Inicio, siga uno de estos pasos:

   - En el **cuadro** Nombre, escriba un nombre para mostrar único para la campaña. No haga clic en **Usar plantilla** porque creará el mensaje de correo electrónico más adelante en el asistente.

   - Haga **clic en Usar plantilla** y seleccione una plantilla de correo electrónico integrada o personalizada. Después de seleccionar la plantilla, **el** cuadro Nombre se rellena automáticamente en función de la plantilla, pero puede cambiar el nombre.

   ![Página de inicio de suplantación de identidad](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)

   Cuando termine, haga clic en **Siguiente**.

4. En el **paso Destinatarios de** destino, siga uno de estos pasos:

   - Haga **clic en Libreta de** direcciones para seleccionar los destinatarios (usuarios o grupos) de la campaña. Cada destinatario de destino debe tener un buzón de Exchange Online. Si hace clic **en Filtrar** y **aplicar** sin especificar criterios de búsqueda, se devolverán todos los destinatarios y se agregarán a la campaña.

   - Haga **clic en** Importar **y,** a continuación, importar archivos para importar un valor separado por comas (CSV) o un archivo de direcciones de correo electrónico separados por líneas. Cada línea debe contener la dirección de correo electrónico del destinatario.

   Cuando termine, haga clic en **Siguiente**.

5. En el paso **Configurar detalles de** correo electrónico, configure las siguientes opciones:

   Si seleccionó una plantilla en el paso **Inicio,** la mayoría de estos valores ya están configurados, pero puede cambiarlos.

   - **From (Name):** el nombre para mostrar que se usa para el remitente del mensaje.

   - **De (correo electrónico):** la dirección de correo electrónico del remitente. Puede escribir una dirección de correo electrónico real o falsa desde el dominio de correo electrónico de su organización o puede escribir una dirección de correo electrónico externa real o falsa. Una dirección de correo electrónico de remitente válida de su organización realmente se resolverá en el cliente de correo electrónico del destinatario.

   - **Dirección URL del servidor de inicio de** sesión de suplantación de identidad : haga clic en la lista desplegable y seleccione una de las direcciones URL disponibles en la lista. Esta es la dirección URL en la que los usuarios estarán tentados a hacer clic. Las opciones son:

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
     > - Un servicio de reputación de dirección URL puede identificar una o varias de estas direcciones URL como no seguras. Compruebe la disponibilidad de la dirección URL en los exploradores web compatibles antes de usar la dirección URL en una campaña de suplantación de identidad.
     >
     > - Debe seleccionar una dirección URL. En el caso de las campañas de **phishing (datos adjuntos),** puede quitar el vínculo del  cuerpo del mensaje en el siguiente paso (de lo contrario, el mensaje contendrá un vínculo y un archivo adjunto).

   - **Tipo de datos** adjuntos: esta configuración solo está disponible en las campañas **de phishing (datos adjuntos).** Haga clic en la lista desplegable y seleccione **. DOCX** o **. PDF** de la lista.

   - **Nombre de los datos** adjuntos: esta configuración solo está disponible en las campañas **de phishing (datos adjuntos).** Escriba un nombre de archivo para los datos adjuntos .docx o .pdf.

   - **Dirección URL de la página de** aterrizaje personalizada: escriba una página de aterrizaje opcional en la que se toman los usuarios si hacen clic en el vínculo de suplantación de identidad y escriben sus credenciales. Este vínculo reemplaza la página de aterrizaje predeterminada. Por ejemplo, si tiene formación interna de reconocimiento, puede especificar esa dirección URL aquí.

   - **Asunto:** el **campo Asunto** del mensaje de correo electrónico.

   Cuando termine, haga clic en **Siguiente**.

6. En el **paso Redactar correo** electrónico, cree el cuerpo del mensaje de correo electrónico. Si seleccionó una plantilla en el paso **Inicio,** el cuerpo del mensaje ya está configurado, pero puede personalizarlo. Puede usar la pestaña **Correo** electrónico (un editor HTML enriquecido) o la pestaña **Origen** (código HTML sin formato).

   El formato HTML puede ser tan simple o complejo como sea necesario. Puede insertar imágenes y texto para mejorar la fiabilidad del mensaje en el cliente de correo electrónico del destinatario.

   - `${username}` inserta el nombre del destinatario.

   - `${loginserverurl}` inserta el valor de **la dirección URL del servidor de inicio de sesión de suplantación de** identidad .

   En el caso de las campañas de **phishing (datos adjuntos),** debe quitar el  vínculo del cuerpo del mensaje (de lo contrario, el mensaje contendrá un vínculo y datos adjuntos, y los clics de vínculo no se realizarán en una campaña de datos adjuntos).

   ![Cuerpo del correo electrónico de redacción](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)

   Cuando termine, haga clic en **Siguiente**.

7. En el **paso Confirmar,** haz clic **en Finalizar** para iniciar la campaña. El mensaje de suplantación de identidad se entrega a los destinatarios de destino.

## <a name="password-attack-campaigns"></a>Campañas de ataque de contraseña

Un *ataque de contraseña* intenta adivinar las contraseñas de las cuentas de usuario de una organización, normalmente después de que el atacante haya identificado una o más cuentas de usuario válidas.

En el Simulador de ataques, hay dos tipos diferentes de campañas de ataque de contraseñas disponibles para probar la complejidad de las contraseñas de los usuarios:

- Contraseña de fuerza bruta (ataque  de **diccionario):** un ataque de fuerza bruta o diccionario usa un archivo de diccionario grande de contraseñas en una cuenta de usuario con la expectativa de que una de ellas funcione (muchas contraseñas en una cuenta).  Los bloqueos de contraseña incorrectos ayudan a disuadir los ataques de contraseña por fuerza bruta.

  Para el ataque de diccionario, puede especificar una o varias contraseñas para probar (introducidas manualmente o en un archivo cargado) y puede especificar uno o varios usuarios.

- **Ataque de aspersión** de contraseña: un ataque de *aspersión* de contraseña usa la misma contraseña que se considera cuidadosamente en una lista de cuentas de usuario (una contraseña frente a muchas cuentas). Los ataques de distribución de contraseñas son más difíciles de detectar que los ataques de contraseña por fuerza bruta (la probabilidad de éxito aumenta cuando un atacante intenta una contraseña en decenas o cientos de cuentas sin el riesgo de que se desenlace el bloqueo de contraseña incorrecto del usuario).

  Para el ataque de aspersión de contraseña, solo puede especificar una contraseña para probar y puede especificar uno o varios usuarios.

> [!NOTE]
> Los ataques de contraseña en el simulador de ataques pasan solicitudes de autenticación básicas de nombre de usuario y contraseña a un punto de conexión, por lo que también funcionan con otros métodos de autenticación (AD FS, sincronización de hash de contraseña, paso a través, PingFederate, etc.). Para los usuarios que tienen mfa habilitado, incluso si el ataque de contraseña intenta su contraseña real, el  intento siempre se registrará como un error (es decir, los usuarios de MFA nunca aparecerán en el recuento de intentos correctos de la campaña). Este es el resultado esperado. MFA es un método principal para ayudar a proteger contra ataques de contraseña.

### <a name="create-and-launch-a-password-attack-campaign"></a>Crear e iniciar una campaña de ataque de contraseña

1. En el Centro de seguridad & cumplimiento, vaya al simulador **de** \> **ataques de administración de amenazas.**

2. En la **página Simular ataques,** realiza una de las siguientes selecciones en función del tipo de campaña que quieras crear:

   - En la sección Contraseña de fuerza bruta **(ataque** de diccionario), haga clic en **Iniciar** ataque o en Ataque de inicio **de detalles** \> **del ataque.**

   - en la sección **Ataque de lanzamiento de contraseña,** haga clic en **Iniciar** ataque o en Ataque de inicio **de detalles** de \> **ataque.**

3. El **Asistente para configurar ataques de** contraseña se inicia en un nuevo menú desplegable. En el **paso Inicio,** escriba un nombre para mostrar único para la campaña y, a continuación, haga clic en **Siguiente.**

4. En el **paso Usuarios de** destino, siga uno de estos pasos:

   - Haga **clic en Libreta de** direcciones para seleccionar los destinatarios (usuarios o grupos) de la campaña. Cada destinatario de destino debe tener un buzón de Exchange Online. Si hace clic **en Filtrar** y **aplicar** sin especificar criterios de búsqueda, se devolverán todos los destinatarios y se agregarán a la campaña.

   - Haga **clic en** Importar **y,** a continuación, importar archivos para importar un valor separado por comas (CSV) o un archivo de direcciones de correo electrónico separados por líneas. Cada línea debe contener la dirección de correo electrónico del destinatario.

   Cuando termine, haga clic en **Siguiente**.

5. En el paso **Elegir configuración de** ataque, elige qué hacer en función del tipo de campaña:

   - **Contraseña de fuerza bruta (ataque de diccionario):** siga uno de estos pasos:

     - **Escriba contraseñas manualmente:** en el cuadro **Presione Entrar** para agregar una contraseña, escriba una contraseña y, a continuación, presione ENTRAR. Repita este paso tantas veces como sea necesario.

     - **Cargar contraseñas desde un archivo de diccionario:** haga clic en Cargar para importar un archivo de texto existente que contenga una contraseña en cada línea y una última línea en blanco.  El archivo de texto debe tener un tamaño de 10 MB o menos y no puede contener más de 30000 contraseñas.

   - **Ataque de aspersión** de contraseña: en las **contraseñas que se usarán en** el cuadro de ataque, escriba una contraseña.

   Cuando termine, haga clic en **Siguiente**.

6. En el **paso Confirmar,** haz clic **en Finalizar** para iniciar la campaña. Las contraseñas que especificó se probarán en los usuarios especificados.

## <a name="view-campaign-results"></a>Ver los resultados de la campaña

Después de iniciar una campaña, puedes comprobar el progreso y los resultados en la página principal **simular ataques.**

Las campañas activas mostrarán una barra de estado, un valor de porcentaje completado y el recuento "(usuarios completados) de (total de usuarios)". Al hacer **clic en el** botón Actualizar se actualizará el progreso de las campañas activas. También puedes hacer clic en **Finalizar** para detener una campaña activa.

Cuando finaliza la campaña, el estado cambia a **Ataque completado.** Puedes ver los resultados de la campaña mediante cualquiera de las siguientes acciones:

- En la página **principal Simular ataques,** haz clic **en Ver informe** bajo el nombre de la campaña.

- En la página **principal Simular ataques,** haz clic **en Detalles de** ataque en la sección para el tipo de ataque. En la **página Detalles de** ataque que se abre, selecciona la campaña en la sección Historial **de** ataques.

Cualquiera de las acciones anteriores te llevará a una página denominada **Detalles de ataque.** La información disponible en esta página para cada tipo de campaña se describe en las secciones siguientes.

### <a name="spear-phishing-credentials-harvest-campaign-results"></a>Resultados de la campaña de phishing (recolección de credenciales)

La siguiente información está disponible en la página Detalles **de ataques** de cada campaña:

- Duración (fecha/hora de inicio y fecha/hora de finalización) de la campaña.

- **Total de usuarios dirigidos**

- **Intentos correctos:** el número de usuarios que han hecho clic en el vínculo y han **escrito** sus credenciales (cualquier *valor* de nombre de usuario y contraseña).

- **Tasa de éxito general:** porcentaje calculado por **intentos correctos.** Total de usuarios a los que se  /  **ha dirigido .**

- **Clic más rápido:** cuánto tiempo tardó el primer usuario en hacer clic en el vínculo después de iniciar la campaña.

- **Promedio de clic:** la suma del tiempo que tardó todo el mundo en hacer clic en el vínculo dividido por el número de usuarios que hizo clic en el vínculo.

- **Porcentaje de éxito de** clic: porcentaje calculado por (número de usuarios que han hecho clic en el vínculo) / **Total de usuarios a los que se ha dirigido**.

- **Credenciales más rápidas:** cuánto tiempo tardó el primer usuario en escribir sus credenciales después de iniciar la campaña.

- **Credenciales promedio:** la suma del tiempo que todos tardaron en escribir sus credenciales divididas por el número de usuarios que especificaron sus credenciales.

- **Porcentaje de éxito de credenciales:** porcentaje calculado por (número de usuarios que especificaron sus credenciales) / **Total de usuarios a los** que se ha dirigido .

- Gráfico de barras que muestra el vínculo en el que se **hizo** clic y los números proporcionados **por credenciales** por día.

- Gráfico de círculo que muestra los porcentajes Vínculo en el que se **hizo** clic, **Credencial** proporcionada y **Ninguno** para la campaña.

- La **sección Usuarios en peligro** muestra los detalles de los usuarios que han hecho clic en el vínculo:

  - La dirección de correo electrónico del usuario

  - Fecha y hora en que se hizo clic en el vínculo.

  - La dirección IP del cliente.

  - Detalles sobre la versión del usuario de Windows y el explorador web.

  Puede hacer clic **en Exportar** para exportar los resultados a un archivo CSV.

### <a name="spear-phishing-attachment-campaign-results"></a>Resultados de la campaña de phishing (datos adjuntos)

La siguiente información está disponible en la página Detalles **de ataques** de cada campaña:

- Duración (fecha/hora de inicio y fecha/hora de finalización) de la campaña.

- **Total de usuarios dirigidos**

- **Intentos** correctos: el número de usuarios que abrieron, descargaron y abrieron los datos adjuntos (la vista previa no cuenta).

- **Tasa de éxito general:** porcentaje calculado por **intentos correctos.** Total de usuarios a los que se  /  **ha dirigido .**

- **Tiempo de apertura de datos** adjuntos más rápido: cuánto tiempo tardó el primer usuario en abrir los datos adjuntos después de iniciar la campaña.

- **Tiempo medio de** apertura de datos adjuntos: la suma del tiempo que todos tardaron en abrir los datos adjuntos dividido por el número de usuarios que abrieron los datos adjuntos.

- **Tasa de éxito de** apertura de datos adjuntos: porcentaje calculado por (número de usuarios que abrieron los datos adjuntos) / Total de usuarios a los que **se ha dirigido**.

### <a name="brute-force-password-dictionary-attack-campaign-results"></a>Resultados de la campaña de fuerza bruta de contraseña (ataque de diccionario)

La siguiente información está disponible en la página Detalles **de ataques** de cada campaña:

- Duración (fecha/hora de inicio y fecha/hora de finalización) de la campaña.

- **Total de usuarios dirigidos**

- **Intentos** correctos: el número de usuarios que se encontraron con una de las contraseñas especificadas.

- **Tasa de éxito general:** porcentaje calculado por **intentos correctos.** Total de usuarios a los que se  /  **ha dirigido .**

- En **la sección Usuarios comprometidos** se enumeran las direcciones de correo electrónico de los usuarios afectados. Puede hacer clic **en Exportar** para exportar los resultados a un archivo CSV.

### <a name="password-spray-attack-campaign-results"></a>Resultados de la campaña de ataques por aspersión de contraseñas

La siguiente información está disponible en la página Detalles **de ataques** de cada campaña:

- Duración (fecha/hora de inicio y fecha/hora de finalización) de la campaña.

- **Total de usuarios dirigidos**

- **Intentos** correctos: el número de usuarios que se encontraron con la contraseña especificada.

- **Tasa de éxito general:** porcentaje calculado por **intentos correctos.** Total de usuarios a los que se  /  **ha dirigido .**
