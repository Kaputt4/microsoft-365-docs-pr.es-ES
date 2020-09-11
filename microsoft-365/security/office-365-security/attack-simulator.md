---
title: Simulador de ataque en ATP
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
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden aprender a usar simulador de ataques para ejecutar ataques simulados de suplantación de identidad (phishing) y contraseña en sus organizaciones de Microsoft 365 E5 o ATP planeada 2.
ms.openlocfilehash: 9fc28cdecc07f5325918e3d5176e52d1051a626c
ms.sourcegitcommit: 2b8c3fc39a7cbd4ca35e98dca430d2470cd2c925
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2020
ms.locfileid: "47426998"
---
# <a name="attack-simulator-in-atp"></a>Simulador de ataque en ATP

Si su organización tiene el plan 2 de la protección contra amenazas avanzada (ATP) de Office 365, que incluye [capacidades de investigación y respuesta de amenazas](office-365-ti.md), puede usar simulador de ataques en el centro de seguridad & cumplimiento para ejecutar escenarios de ataque realistas en la organización. Estos ataques simulados pueden ayudarle a identificar y encontrar a los usuarios vulnerables antes de que un ataque real afecte a su conclusión. Lea este artículo para obtener más información.

> [!NOTE]
> La simulación de ataques y los datos relacionados con la formación se almacenan con otros datos de clientes para los servicios 365 de Microsoft. Para obtener más información, vea [ubicaciones de datos de Microsoft 365](/microsoft-365/enterprise/o365-data-locations).

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Para abrir el Centro de seguridad y cumplimiento, vaya a <https://protection.office.com/>. El simulador de ataques **Threat management** está disponible en \> **simulador de ataques**de administración de amenazas. Vaya directamente a simulador de ataque, abrir <https://protection.office.com/attacksimulator> .

- Para obtener más información acerca de la disponibilidad de un simulador de ataque en distintas suscripciones de Microsoft 365, consulte [Office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).

- Debe ser miembro de los grupos de roles **Administración** de la organización o **Administrador de seguridad** . Para obtener más información acerca de los grupos de roles en el Centro de seguridad y cumplimiento, consulte [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).

- La cuenta debe estar configurada para la autenticación multifactor (MFA) con el fin de crear y administrar campañas en el simulador de ataques. Para obtener instrucciones, vea [set up multi-factor Authentication](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication).

- Las campañas de suplantación de identidad recopilarán y procesarán eventos durante 30 días. Los datos históricos de la campaña estarán disponibles hasta 90 días después de iniciar la campaña.

- No hay cmdlets de PowerShell correspondientes para el simulador de ataques.

## <a name="spear-phishing-campaigns"></a>Campañas de "Spear phishing"

La *suplantación de identidad (phishing)* es un término genérico para los ataques de correo electrónico que intentan robar información confidencial en los mensajes que parecen ser de remitentes legítimos o de confianza. La *suplantación de identidad (Spear phishing* ) es un ataque de suplantación de identidad (phishing) dirigido que usa contenido centrado y personalizado que está específicamente adaptado a los destinatarios de destino (normalmente, después del reconocimiento de los destinatarios por parte del atacante).

En el simulador de ataque, hay disponibles dos tipos diferentes de campañas de "Spear phishing":

- **Spear phishing (cosecha de credenciales)**: el ataque intenta convencer a los destinatarios para que haga clic en una dirección URL del mensaje. Si hacen clic en el vínculo, se les pedirá que escriban sus credenciales. Si es así, se toman en una de las siguientes ubicaciones:

  - Una página predeterminada que explica que se trataba de una sola prueba y ofrece sugerencias para reconocer los mensajes de suplantación de identidad.

    ![Qué ven los usuarios si hacen clic en el vínculo phishing y escriben sus credenciales](../../media/attack-simulator-phishing-result.png)

  - Una página personalizada (URL) que especifique.

- **Spear phishing (datos adjuntos)**: el ataque intenta convencer a los destinatarios para que abran un archivo adjunto. docx o. pdf en el mensaje. Los datos adjuntos incluyen el mismo contenido del vínculo de suplantación de identidad (phishing) predeterminado, pero la primera frase comienza por " \<Display Name\> , está viendo este mensaje como un mensaje de correo electrónico reciente que ha abierto...".

> [!NOTE]
> Actualmente, las campañas de suplantación de identidad de Spear en el simulador de ataque no expiran.

### <a name="create-a-spear-phishing-campaign"></a>Crear una campaña de "Spear phishing"

Una parte importante de cualquier campaña de "Spear phishing" es la apariencia del mensaje de correo electrónico que se envía a los destinatarios de destino. Para crear y configurar el mensaje de correo electrónico, tiene estas opciones:

- **Usar una plantilla de correo electrónico integrada**: hay disponibles dos plantillas integradas: **Premio regalo** y **actualización de nóminas**. Puede personalizar aún más algunas, todas o ninguna de las propiedades de correo electrónico de la plantilla al crear e iniciar la campaña.

- **Cree una plantilla de correo electrónico reutilizable**: una vez que haya creado y guardado la plantilla de correo electrónico, puede usarla de nuevo en las campañas de suplantación de identidad de Spear futuras. Puede personalizar aún más algunas, todas o ninguna de las propiedades de correo electrónico de la plantilla al crear e iniciar la campaña.

- **Crear el mensaje de correo electrónico en el asistente**: puede crear el mensaje de correo electrónico directamente en el asistente mientras crea e inicia la campaña de Spear phishing.

#### <a name="step-1-optional-create-a-custom-email-template"></a>Paso 1 (opcional): crear una plantilla de correo electrónico personalizada

Si va a utilizar una de las plantillas integradas o va a crear el mensaje de correo electrónico directamente en el asistente, puede omitir este paso.

1. En el centro de seguridad & cumplimiento, vaya **Threat management** a \> **simulador de ataques**de administración de amenazas.

2. En la página **Simulate Attacks** , en las secciones de **Spear phishing (credenciales cosecha)** o **Spear phishing (datos adjuntos)** , haga clic en **detalles de ataque**.

   No importa dónde cree la plantilla. Las opciones disponibles en la plantilla son las mismas para ambos tipos de ataques de suplantación de identidad.

3. En la **página Detalles del ataque** que se abre, en la sección plantillas de **suplantación de identidad** , en el área **crear plantillas** , haga clic en **nueva plantilla**.

4. El Asistente para **Configurar plantillas de suplantación de identidad** se inicia en un nuevo flotante. En el paso **iniciar** , escriba un nombre para mostrar único para la plantilla y, a continuación, haga clic en **siguiente**.

5. En el paso **configurar detalles de correo electrónico** , configure las siguientes opciones:

   - **From (nombre)**: el nombre para mostrar que se usa para el remitente del mensaje.

   - **From (email)**: la dirección de correo electrónico del remitente.

   - **Dirección URL del servidor de inicio de sesión de phishing**: haga clic en el menú desplegable y seleccione una de las direcciones URL disponibles de la lista. Esta es la dirección URL a la que se verá tentado a los usuarios en hacer clic. Las opciones son:

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
     > - Todas las direcciones URL son intencionadamente http, no HTTPS.
     >
     > - Un servicio de reputación de dirección URL puede identificar una o varias de estas direcciones URL como no seguras. Compruebe la disponibilidad de la dirección URL en los exploradores Web admitidos antes de usar la dirección URL en una campaña de suplantación de identidad (phishing).

   - **Dirección URL de la página de aterrizaje personalizada**: escriba una página de aterrizaje opcional en la que se tomen los usuarios si hacen clic en el vínculo phishing y escriben sus credenciales. Este vínculo reemplaza la página de aterrizaje predeterminada. Por ejemplo, si tiene un entrenamiento de conciencia interno, puede especificar esta dirección URL aquí.

   - **Categoría**: Actualmente, no se usa esta configuración (se ignora cualquier cosa que haya escrito).

   - **Subject**: el campo **Subject** del mensaje de correo electrónico.

   Cuando termine, haga clic en **Siguiente**.

6. En el paso de **redacción de correo electrónico** , cree el cuerpo del mensaje del mensaje de correo electrónico. Puede usar la pestaña **correo electrónico** (un editor HTML enriquecido) o la ficha **origen** (código HTML sin formato).

   El formato HTML puede ser tan sencillo o complejo como sea necesario. Puede insertar imágenes y texto para mejorar la increíbleidad del mensaje en el cliente de correo electrónico del destinatario.

   - `${username}` inserta el nombre del destinatario.

   - `${loginserverurl}` inserta el valor de la **dirección URL del servidor de inicio de sesión de suplantación de identidad** del paso anterior.

   Cuando termine, haga clic en **Siguiente**.

7. En el paso **confirmar** , haga clic en **Finalizar**.

#### <a name="step-2-create-and-launch-the-spear-phishing-campaign"></a>Paso 2: crear e iniciar la campaña de suplantación de identidad de Spear

1. En el centro de seguridad & cumplimiento, vaya **Threat management** a \> **simulador de ataques**de administración de amenazas.

2. En la página **simular ataques** , realice una de las siguientes selecciones en función del tipo de campaña que desee crear:

   - En la sección **Spear phishing (credenciales cosecha)** , haga clic en **iniciar ataque** o en ataque de inicio de **detalles de ataque** \> **Launch Attack**.

   - En la sección **Spear phishing (datos adjuntos)** , haga clic en **iniciar ataque** o en ataque de inicio de **detalles de ataque** \> **Launch Attack**.

3. El Asistente para **configurar un ataque de suplantación de identidad** se inicia en un nuevo flotante. En el paso **iniciar** , siga uno de estos pasos:

   - En el cuadro **nombre** , escriba un nombre para mostrar único para la campaña. No haga clic en **Usar plantilla**, ya que creará el mensaje de correo electrónico más adelante en el asistente.

   - Haga clic en **Usar plantilla** y seleccione una plantilla de correo electrónico integrada o personalizada. Una vez seleccionada la plantilla, el cuadro **nombre** se rellena automáticamente en función de la plantilla, pero puede cambiar el nombre.

   ![Página de inicio de phishing](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)

   Cuando termine, haga clic en **Siguiente**.

4. En el paso **destinatarios de destino** , siga uno de estos pasos:

   - Haga clic en **Libreta de direcciones** para seleccionar los destinatarios (usuarios o grupos) de la campaña. Cada destinatario de destino debe tener un buzón de correo de Exchange Online. Si hace clic en **filtrar** y **aplicar** sin especificar ningún criterio de búsqueda, todos los destinatarios se devuelven y se agregan a la campaña.

   - Haga clic en **importar** y, a continuación, en importar **archivo** para importar un archivo de valores separados por comas (CSV) o archivos separados por líneas de direcciones de correo electrónico. Cada línea debe contener la dirección de correo electrónico del destinatario.

   Cuando termine, haga clic en **Siguiente**.

5. En el paso **configurar detalles de correo electrónico** , configure las siguientes opciones:

   Si seleccionó una plantilla en el paso **iniciar** , la mayoría de estos valores ya están configurados, pero puede cambiarlos.

   - **From (nombre)**: el nombre para mostrar que se usa para el remitente del mensaje.

   - **From (email)**: la dirección de correo electrónico del remitente. Puede escribir una dirección de correo electrónico real o falsa desde el dominio de correo electrónico de su organización o puede escribir una dirección de correo electrónico externa real o falsa. Una dirección de correo electrónico de remitente válida de la organización se resolverá realmente en el cliente de correo electrónico del destinatario.

   - **Dirección URL del servidor de inicio de sesión de phishing**: haga clic en el menú desplegable y seleccione una de las direcciones URL disponibles de la lista. Esta es la dirección URL a la que se verá tentado a los usuarios en hacer clic. Las opciones son:

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
     > - Todas las direcciones URL son intencionadamente http, no HTTPS.
     >
     > - Un servicio de reputación de dirección URL puede identificar una o varias de estas direcciones URL como no seguras. Compruebe la disponibilidad de la dirección URL en los exploradores Web admitidos antes de usar la dirección URL en una campaña de suplantación de identidad (phishing).
     >
     > - Es necesario que seleccione una dirección URL. En el caso de las campañas de **"Spear phishing" (datos adjuntos)** , puede quitar el vínculo del cuerpo del mensaje en el paso siguiente (de lo contrario, el mensaje contendrá tanto un vínculo **como** datos adjuntos).

   - **Tipo de datos adjuntos**: esta configuración solo está disponible en las campañas de **"Spear phishing" (datos adjuntos)** . Haga clic en la lista desplegable y seleccione **. DOCX** o **. PDF** de la lista.

   - **Nombre de datos adjuntos**: esta configuración solo está disponible en las campañas de **"Spear phishing" (datos adjuntos)** . Escriba un nombre de archivo para los datos adjuntos. docx o. pdf.

   - **Dirección URL de la página de aterrizaje personalizada**: escriba una página de aterrizaje opcional en la que se tomen los usuarios si hacen clic en el vínculo phishing y escriben sus credenciales. Este vínculo reemplaza la página de aterrizaje predeterminada. Por ejemplo, si tiene un entrenamiento de conciencia interno, puede especificar esta dirección URL aquí.

   - **Subject**: el campo **Subject** del mensaje de correo electrónico.

   Cuando termine, haga clic en **Siguiente**.

6. En el paso de **redacción de correo electrónico** , cree el cuerpo del mensaje del mensaje de correo electrónico. Si seleccionó una plantilla en el paso **iniciar** , el cuerpo del mensaje ya está configurado, pero puede personalizarlo. Puede usar la pestaña **correo electrónico** (un editor HTML enriquecido) o la ficha **origen** (código HTML sin formato).

   El formato HTML puede ser tan sencillo o complejo como sea necesario. Puede insertar imágenes y texto para mejorar la increíbleidad del mensaje en el cliente de correo electrónico del destinatario.

   - `${username}` inserta el nombre del destinatario.

   - `${loginserverurl}` inserta el valor **URL del servidor de inicio de sesión de suplantación de identidad** .

   Para las campañas de **"Spear phishing" (datos adjuntos)** , debe quitar el vínculo del cuerpo del mensaje (de lo contrario, el mensaje contendrá tanto un vínculo **como** datos adjuntos y los clics de vínculo no se realizará el seguimiento en una campaña de datos adjuntos).

   ![Crear cuerpo de correo electrónico](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)

   Cuando termine, haga clic en **Siguiente**.

7. En el paso **confirmar** , haga clic en **Finalizar** para iniciar la campaña. El mensaje de suplantación de identidad se entrega a los destinatarios de destino.

## <a name="password-attack-campaigns"></a>Campañas de ataque con contraseña

Un *ataque de contraseña* intenta adivinar las contraseñas de las cuentas de usuario de una organización, normalmente después de que el atacante haya identificado una o varias cuentas de usuario válidas.

En el simulador de ataque, hay disponibles dos tipos diferentes de campañas para ataques con contraseña para que pueda probar la complejidad de las contraseñas de los usuarios:

- **Contraseña de fuerza bruta (ataque de diccionario)**: una *fuerza bruta* o un ataque de *Diccionario* usa un archivo de Diccionario de gran tamaño de contraseñas en una cuenta de usuario con la esperanza de que uno de ellos trabaje (muchas contraseñas con una cuenta). Los bloqueos de contraseñas incorrectos ayudan a impedir ataques de contraseñas de fuerza bruta.

  Para el ataque de diccionario, puede especificar una o varias contraseñas para probarlas (especificadas manualmente o en un archivo cargado) y puede especificar uno o varios usuarios.

- **Ataque por pulverización de contraseñas**: un ataque *rociado de contraseñas* usa la misma contraseña cuidadosamente considerada con una lista de cuentas de usuario (una contraseña en muchas cuentas). Los ataques por pulverización de contraseña son más difíciles de detectar que los ataques de fuerza bruta de contraseña (la probabilidad de que aumente el éxito cuando un atacante prueba una contraseña entre docenas o cientos de cuentas sin el riesgo de que se bloquee el bloqueo de contraseña incorrecto del usuario).

  Para el ataque con aerosol de contraseña, solo puede especificar una contraseña para probar y puede especificar uno o varios usuarios.

> [!NOTE]
> Los ataques de contraseñas en el simulador de ataque pasan las solicitudes de nombre de usuario y contraseña básicas de autenticación a un extremo, por lo que también funcionan con otros métodos de autenticación (AD FS, sincronización de hash de contraseña, paso a través, PingFederate, etc.). Para los usuarios con la MFA habilitada, aunque el ataque de contraseña intente su contraseña real, el intento se registrará siempre como un error (es decir, los usuarios de MFA nunca aparecerán en el recuento **correcto de intentos** de la campaña). Este es el resultado esperado. MFA es un método principal para ayudar a proteger contra ataques de contraseñas.

### <a name="create-and-launch-a-password-attack-campaign"></a>Crear e iniciar una campaña de ataque con contraseña

1. En el centro de seguridad & cumplimiento, vaya **Threat management** a \> **simulador de ataques**de administración de amenazas.

2. En la página **simular ataques** , realice una de las siguientes selecciones en función del tipo de campaña que desee crear:

   - En la sección **contraseña de fuerza bruta (ataque de diccionario)** , haga clic en **iniciar ataque** o en ataque de inicio de **detalles de ataque** \> **Launch Attack**.

   - en la sección **ataque por pulverización de contraseña** , haga clic en **iniciar ataque** o en ataque de inicio de **detalles de ataque** \> **Launch Attack**.

3. El Asistente para **configurar un ataque de contraseña** comienza en un nuevo control flotante. En el paso **iniciar** , escriba un nombre para mostrar único para la campaña y, a continuación, haga clic en **siguiente**.

4. En el paso **usuarios de destino** , siga uno de estos pasos:

   - Haga clic en **Libreta de direcciones** para seleccionar los destinatarios (usuarios o grupos) de la campaña. Cada destinatario de destino debe tener un buzón de correo de Exchange Online. Si hace clic en **filtrar** y **aplicar** sin especificar ningún criterio de búsqueda, todos los destinatarios se devuelven y se agregan a la campaña.

   - Haga clic en **importar** y, a continuación, en importar **archivo** para importar un archivo de valores separados por comas (CSV) o archivos separados por líneas de direcciones de correo electrónico. Cada línea debe contener la dirección de correo electrónico del destinatario.

   Cuando termine, haga clic en **Siguiente**.

5. En el paso **elegir configuración de ataque** , elija qué hacer en función del tipo de campaña:

   - **Contraseña de fuerza bruta (ataque de diccionario)**: realice uno de los pasos siguientes:

     - **Escriba las contraseñas manualmente**: en el cuadro **presione Entrar para agregar una contraseña** , escriba una contraseña y, a continuación, presione Entrar. Repita este paso tantas veces como sea necesario.

     - **Cargar contraseñas desde un archivo de diccionario**: haga clic en **cargar** para importar un archivo de texto existente que contenga una contraseña en cada línea y una última línea en blanco. El archivo de texto debe tener un tamaño de 10 MB o menos, y no puede contener más de 30000 contraseñas.

   - **Ataque por pulverizador de contraseña**: en **las contraseñas que se van a usar en el cuadro ataque** , escriba una contraseña.

   Cuando termine, haga clic en **Siguiente**.

6. En el paso **confirmar** , haga clic en **Finalizar** para iniciar la campaña. Las contraseñas especificadas se prueban en los usuarios especificados.

## <a name="view-campaign-results"></a>Ver los resultados de la campaña

Después de iniciar una campaña, puede comprobar el progreso y los resultados en la Página principal de **ataques de simulación** .

Las campañas activas mostrarán una barra de estado, un valor porcentual completado y el recuento de (usuarios completados) de (total de usuarios) ". Al hacer clic en el botón **Actualizar** se actualizará el progreso de las campañas activas. También puede hacer clic en **Finalizar** para detener una campaña activa.

Una vez finalizada la campaña, el estado cambia a **ataque completado**. Puede ver los resultados de la campaña realizando una de las acciones siguientes:

- En la página principales **ataques de simulación** , haga clic en **Ver informe** bajo el nombre de la campaña.

- En la página principales **ataques de simulación** , haga clic en detalles de **ataque** en la sección para el tipo de ataque. En la página **detalles de ataque** que se abre, seleccione la campaña en la sección historial de **ataques** .

Cualquiera de las acciones anteriores le llevará a una página denominada **detalles del ataque**. La información disponible en esta página para cada tipo de campaña se describe en las secciones siguientes.

### <a name="spear-phishing-credentials-harvest-campaign-results"></a>Resultados de la campaña de Spear phishing (recopilación de credenciales)

La siguiente información está disponible en la página **detalles de ataque** para cada campaña:

- La duración (fecha y hora de inicio y fecha de finalización) de la campaña.

- **Total de usuarios a los que se destina**

- **Intentos correctos**: el número de usuarios que hizo clic en el vínculo **y** escribió sus credenciales (*cualquier* valor de nombre de usuario y contraseña).

- **Tasa general de éxito**: porcentaje calculado por el **Successful attempts**  /  **número total de usuarios a los**que se ha dirigido correctamente.

- **Clic más rápido**: Cuánto tiempo tardó el primer usuario en hacer clic en el vínculo después de iniciar la campaña.

- **Promedio haga clic**en: cantidad de tiempo que tardó en hacer que todos los usuarios haga clic en el vínculo dividido por el número de usuarios que hizo clic en el vínculo.

- **Tasa de éxito**: un porcentaje calculado por (número de usuarios que hizo clic en el vínculo)/ **total de usuarios dirigidos**.

- **Credenciales más rápidas**: Cuánto tiempo tardó el primer usuario en escribir sus credenciales después de iniciar la campaña.

- **Promedio de credenciales**: la suma de cuánto tiempo tardó en escribir sus credenciales dividida por el número de usuarios que escribieron sus credenciales.

- **Tasa de éxito**de la credencial: porcentaje calculado por (número de usuarios que han especificado sus credenciales)/ **total de usuarios a los**que se destina.

- Gráfico de barras que muestra el **vínculo en** el que se hizo clic y los números de **credenciales especificados** por día.

- Un gráfico circular que muestra el **vínculo en**el que se hizo clic, las **credenciales suministradas**y **ninguno** de los porcentajes de la campaña.

- La sección **usuarios comprometidos** muestra los detalles de los usuarios que hacer clic en el vínculo:

  - La dirección de correo electrónico del usuario

  - Fecha y hora en que hizo clic en el vínculo.

  - La dirección IP del cliente.

  - Detalles sobre la versión del usuario de Windows y el explorador Web.

  Puede hacer clic en **exportar** para exportar los resultados a un archivo CSV.

### <a name="spear-phishing-attachment-campaign-results"></a>Resultados de la campaña de Spear phishing (datos adjuntos)

La siguiente información está disponible en la página **detalles de ataque** para cada campaña:

- La duración (fecha y hora de inicio y fecha de finalización) de la campaña.

- **Total de usuarios a los que se destina**

- **Intentos correctos**: el número de usuarios que abrieron o descargaron y abrieron los datos adjuntos (la vista previa no cuenta).

- **Tasa general de éxito**: porcentaje calculado por el **Successful attempts**  /  **número total de usuarios a los**que se ha dirigido correctamente.

- **Tiempo de apertura de datos adjuntos más rápido**: Cuánto tiempo tardó el primer usuario en abrir los datos adjuntos después de iniciar la campaña.

- **Tiempo medio de apertura de datos adjuntos**: la suma de la duración de la apertura de los datos adjuntos por el número de usuarios que abrieron los datos adjuntos.

- **Tasa de éxito de apertura de datos adjuntos**: porcentaje calculado por (número de usuarios que abrieron los datos adjuntos)/ **total de usuarios dirigidos**.

### <a name="brute-force-password-dictionary-attack-campaign-results"></a>Resultados de la campaña de contraseña de fuerza bruta (ataque de diccionario)

La siguiente información está disponible en la página **detalles de ataque** para cada campaña:

- La duración (fecha y hora de inicio y fecha de finalización) de la campaña.

- **Total de usuarios a los que se destina**

- **Intentos correctos**: el número de usuarios que se encontraron que utilizaban una de las contraseñas especificadas.

- **Tasa general de éxito**: porcentaje calculado por el **Successful attempts**  /  **número total de usuarios a los**que se ha dirigido correctamente.

- La sección **usuarios comprometidos** muestra las direcciones de correo electrónico de los usuarios afectados. Puede hacer clic en **exportar** para exportar los resultados a un archivo CSV.

### <a name="password-spray-attack-campaign-results"></a>Resultados de la campaña de ataque con aerosol de contraseña

La siguiente información está disponible en la página **detalles de ataque** para cada campaña:

- La duración (fecha y hora de inicio y fecha de finalización) de la campaña.

- **Total de usuarios a los que se destina**

- **Intentos correctos**: el número de usuarios que se encontraron que usaban la contraseña especificada.

- **Tasa general de éxito**: porcentaje calculado por el **Successful attempts**  /  **número total de usuarios a los**que se ha dirigido correctamente.
