---
title: Configuración de un equipo con aislamiento de seguridad
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-3tiersprotection
- m365solution-securecollab
ms.custom:
- Ent_Solutions
description: Obtenga información acerca de cómo crear un equipo con una etiqueta de confidencialidad exclusiva para la seguridad.
ms.openlocfilehash: 439dee40d1501801fc09d570614a591259c6f09c
ms.sourcegitcommit: 31be333178b934c519f419656f4c3a53e1beffdc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2021
ms.locfileid: "49881710"
---
# <a name="configure-a-team-with-security-isolation"></a>Configuración de un equipo con aislamiento de seguridad

Este artículo contiene recomendaciones y pasos para configurar un equipo privado en Microsoft Teams y usar una etiqueta de confidencialidad única para cifrar los archivos de forma que solo los miembros del equipo puedan descifrarlos.

Más allá del acceso privado, este artículo describe cómo configurar el sitio de SharePoint asociado, al que puede obtener acceso desde la sección **Archivos** de un canal de equipo, para la seguridad adicional que necesita para almacenar datos altamente regulados.

Los elementos de configuración para un equipo con aislamiento de seguridad son:

- Un grupo privado
- Seguridad adicional en el sitio de SharePoint asociado para el equipo que:
  - Impide que los miembros del sitio compartan el sitio con otras personas.
  - Impide que los usuarios que no sean miembros del sitio soliciten acceso al sitio.
- Una etiqueta de sensibilidad específica para este equipo que:
    - Impide el acceso a contenido de SharePoint desde dispositivos no administrados
    - Permite o deniega al equipo acceso de invitado en función de sus necesidades.
    - Cifra los documentos a los que se aplica la etiqueta

> [!IMPORTANT]
> Antes de proceder con los pasos de este artículo, asegúrese de que tiene habilitadas las [etiquetas de confidencialidad para proteger el contenido en Microsoft Teams, grupos de Office 365 y sitios de SharePoint](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).

Vea este vídeo para obtener información general del proceso.
<br>
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4mGHf]

<a name="poster"></a> Para ver un resumen de una página de este escenario, consulte el [Póster de aislamiento de seguridad de Microsoft Teams](../downloads/team-security-isolation-poster.pdf).

[![Póster de aislamiento de seguridad de Microsoft Teams](../media/secure-teams-security-isolation/team-security-isolation-poster.png)](../downloads/team-security-isolation-poster.pdf)

También puede descargar este póster en los formatos [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/team-security-isolation-poster.pdf) o [PowerPoint](https://download.microsoft.com/download/8/0/5/8057fc16-c044-40b6-a652-7ed555ba2895/team-security-isolation-poster.pptx) e imprimirlo en tamaño carta, legal o tabloide (11 x 17).

## <a name="initial-protections"></a>Protecciones iniciales

Para ayudar a proteger el acceso al equipo y a su sitio de SharePoint subyacente, revise las siguientes recomendaciones:
- [Directivas de acceso a dispositivos e identidades](../security/office-365-security/identity-access-policies.md)
- [Directivas de acceso de SharePoint Online](../security/office-365-security/sharepoint-file-access-policies.md)
- [Implementación de equipos con la protección de base de referencia](configure-teams-baseline-protection.md)

## <a name="guest-sharing"></a>Uso compartido de invitados

Según la naturaleza de su empresa, es posible que quiera habilitar o no el uso compartido de invitados para este equipo. Si tiene previsto colaborar con personas ajenas a su organización en el equipo, habilite el uso compartido de invitados. 

Para más información sobre el uso compartido de invitados de forma segura, vea los recursos siguientes:

- [Limitar la exposición accidental de archivos al compartirlos con usuarios externos a la organización](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure)
- [Crear un entorno seguro de uso compartido para invitados](https://docs.microsoft.com/microsoft-365/solutions/create-secure-guest-sharing-environment)

Para permitir o bloquear el uso compartido de invitados, utilizamos una combinación de una etiqueta de confidencialidad para el equipo y controles de uso compartido a nivel de sitio para el sitio de SharePoint asociado, ambos tratados más adelante.

## <a name="create-a-private-team"></a>Creación de un equipo privado

Ya que estamos creando una etiqueta de sensibilidad específica para este equipo, el siguiente paso es crear el equipo. Si tiene un equipo existente, puede usarlo.

Para crear un equipo para información confidencial
1. En Teams, haga clic en **Teams** en el lado izquierdo de la aplicación, luego haga clic en **Unirse o crear un equipo** en la parte inferior de la lista de equipos.
2. Haga clic en **Crear equipo** (primera tarjeta, esquina superior izquierda).
3. Elija **Crear un equipo desde cero**.
4. En la lista **Confidencialidad**, conserve el valor predeterminado.
5. En **Privacidad**, haga clic en **Privado**.
6. Escriba un nombre para el equipo que esté relacionado con su proyecto confidencial. Por ejemplo, **Proyecto Saturno**.
7. Haga clic en **Crear**.
8. Agregue usuarios al equipo y, después, haga clic en **Cerrar**.

## <a name="private-channel-settings"></a>Configuración de canal privado

Recomendamos que se restrinja la creación de canales privados a los propietarios del equipo.

Para restringir la creación de un canal privado
1. En el equipo, haga clic en **Más opciones** y después en **Administrar equipo**.
2. En la pestaña **Configuración**, expanda **Permisos de los miembros**.
3. Desactive la casilla de verificación **Permitir a los miembros crear canales privados**.

También puede usar [Directivas de equipos](https://docs.microsoft.com/MicrosoftTeams/teams-policies) para controlar quién puede crear canales privados.

## <a name="create-a-sensitivity-label"></a>Creación de una etiqueta de confidencialidad

Para configurar un equipo de aislamiento de seguridad, usaremos una etiqueta de confidencialidad creada específicamente para este equipo. Esta etiqueta se usa en el nivel de equipo para controlar el uso compartido de invitados y bloquear el acceso desde dispositivos no administrados. También se puede usar para clasificar y cifrar archivos individuales en el equipo, de modo que solo los propietarios y miembros del equipo puedan abrirlos.

Si tiene un partner interno o un grupo de accionistas que debería poder ver los documentos codificados, pero no editarlos, puede agregarlos a la etiqueta con permisos de solo vista. Después, puede agregar estos usuarios al sitio de SharePoint del equipo con permisos de lector y tendrán acceso de solo lectura al sitio en el que se almacenan los documentos, pero no al equipo.


Crear una etiqueta de confidencialidad
1. Abra el [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com).
2. En **Soluciones**, haga clic en **Protección de la información**.
3. Haga clic en **Crear una etiqueta**.
4. Asigne un nombre a la etiqueta. Para ello, le recomendamos que use el nombre del equipo con el que lo vaya a emplear.
5. Escriba un nombre y una descripción para el complemento y, a continuación, haga clic en **Siguiente**.
6. En la página **Definir el ámbito de la página de la etiqueta**, seleccione **Archivos & mensajes de correo electrónico** y **Grupos & sitios** y haga clic en **Siguiente**.
7. Luego, en la página **Elegir la configuración de protección para archivos y mensajes de correo electrónico**, asegúrese de seleccionar **Cifrar archivos y mensajes de correo electrónico** luego haga clic en **Siguiente**.
8. En la página **Cifrado**, elija **Configurar opciones de cifrado**.
9. Haga clic en **Agregar usuarios o grupos**, seleccione el equipo que ha creado y haga clic en **Agregar**.
10. Haga clic en **Elegir permisos**.
11. Elija **coautoría** de la lista desplegable y, después, haga clic en **Guardar**.
12. Si desea incluir usuarios o grupos con acceso de solo lectura a los archivos con la etiqueta:
    1. Haga clic en **Asignar permisos**
    1. Haga clic en **Agregar usuarios o grupos**, seleccione los usuarios o grupos que desea agregar, y después haga clic en **Agregar**.
    1. Haga clic en **Elegir permisos**.
    1. Elija **Espectador** de la lista desplegable y, después, haga clic en **Guardar**.
13.  Haga clic en **Guardar** y después en **Siguiente**.
14. En la página *Etiquetado automático para archivos y mensajes de correo electrónico**, haga clic en **Siguiente**.
15. En la página **Definir la configuración de protección de los sitios y grupos**, seleccione **Configuración de privacidad y acceso de usuarios externo** y **Configuración de acceso de dispositivo y uso compartido externo** y haga clic en **Siguiente**.
16. En la página **Definir privacidad y acceso a usuarios externos**, en **Privacidad**, seleccione la opción **Privado**.
17. Si desea permitir el acceso de invitado, en **Acceso de usuarios externos**, seleccione **Permitir que los propietarios del grupo de Microsoft 365 agreguen personas de fuera de su organización al grupo como invitados**.
18. Haga clic en **Siguiente**.
19. En la página **Definir el uso compartido externo y el acceso al dispositivo**, seleccione **Controlar el uso compartido externo en sitios de SharePoint etiquetados**.
20. En **El contenido se puede compartir con**, elija **Invitados nuevos y existentes** si va a permitir el acceso de invitado o **Solo los usuarios de su organización** en caso contrario.
21. En **Equipos no administrados**, elija **Bloquear el acceso**.
22. Haga clic en **Siguiente**.
23. En la página **Etiquetado automático para las columnas de la base de datos**, haga clic en **Siguiente**.
24. Haga clic en **Crear etiqueta** y después en **Listo**.

Una vez que haya creado la etiqueta, debe comunicarla a los usuarios que la van a usar. En este caso, haremos que la etiqueta esté disponible solo para las personas del equipo.

Publicación de una etiqueta de confidencialidad
1. En el Centro de cumplimiento de Microsoft 365, en la página **Protección de la información**, escoja la pestaña **Directivas de etiqueta**.
2. Haga clic en **Publicar etiquetas**.
3. En la página **Elegir etiquetas de confidencialidad para publicar**, haga clic en **Elija las etiquetas de confidencialidad para publicar**.
4. Seleccione la etiqueta que ha creado y haga clic en **Agregar**.
5. Haga clic en **Siguiente**.
6. En la página Publicar a usuarios y grupos, haga clic en **Elija usuarios y grupos**.
7. Haga clic en **Agregar** y, después, seleccione el equipo que creó.
8. Haga clic en **Agregar** y, a continuación en **Listo**.
9. Haga clic en **Siguiente**.
10. En la página Configuración de la directiva, active la casilla de verificación **Los usuarios deben ofrecer una justificación para quitar una etiqueta o una etiqueta de clasificación inferior** y, después, haga clic en **Siguiente**.
11. Escriba el nombre de la directiva y haga clic en **Siguiente**.
12. Haga clic en **Enviar** y después en **Listo**.

## <a name="apply-the-label-to-the-team"></a>Aplicación de la etiqueta al equipo

Una vez que se haya publicado la etiqueta, debe aplicarla al equipo para que se apliquen las configuraciones de uso compartido de invitados y dispositivos administrados. Esta acción se lleva a cabo en el Centro de administración de SharePoint. Tenga en cuenta que la etiqueta puede tardar algún tiempo en estar disponible una vez que se ha publicado.

Para aplicar la etiqueta de confidencialidad
1. Abra el [Centro de administración de SharePoint](https://admin.microsoft.com/sharepoint).
2. En **Sitios**, haga clic en **Sitios activos**.
3. Haga clic en el sitio que está asociado al equipo.
4. En **Uso compartido externo** de la pestaña **Confidencialidad**, haga clic en **Editar**.
5. Seleccione la etiqueta que ha creado y haga clic en **Guardar**.

## <a name="sharepoint-settings"></a>Configuración de SharePoint

Hay tres pasos que seguir en SharePoint:

- Actualice la configuración de uso compartido de invitado para el sitio en el Centro de administración de SharePoint para que coincida con lo que ha elegido al crear la etiqueta, y actualice el vínculo para compartir predeterminado a *Usuarios con acceso existente*.
- Actualice la configuración de uso compartido del sitio en el propio sitio para evitar que los miembros compartan los archivos, las carpetas o el sitio, y desactivar las solicitudes de acceso.
- Si agregó personas o grupos a la etiqueta con permisos de espectador, puede agregarlos al sitio de SharePoint con permisos de lectura.

### <a name="sharepoint-guest-settings"></a>Configuración de invitados de SharePoint

La configuración de uso compartido de invitado que eligió al crear la etiqueta (que solo afecta a la pertenencia al equipo) debe coincidir con la configuración de uso compartido de invitados para el sitio de SharePoint asociado de la siguiente manera:

|Configuración de etiqueta|Configuración del sitio de SharePoint|
|:------------|:----------------------|
|**Permitir que los propietarios de grupos de Ofﬁce 365 agreguen a usuarios ajenos a la organización a los grupos** seleccionado|**Invitados nuevos y existentes** (predeterminado para equipos nuevos)|
|**Permitir que los propietarios de grupos de Ofﬁce 365 agreguen a usuarios ajenos a la organización a los grupos** no seleccionado|**Solo personas de la organización**|

También actualizará el tipo de vínculo para compartir predeterminado con el fin de reducir el riesgo de compartir por error archivos y carpetas a un público más amplio del previsto.

Para actualizar la configuración del sitio
1. Abra el [Centro de administración de SharePoint](https://admin.microsoft.com/sharepoint).
2. En **Sitios**, haga clic en **Sitios activos**.
3. Haga clic en el sitio que está asociado al equipo.
4. En **Uso compartido externo** de la pestaña **Directivas**, haga clic en **Editar**.
5. Si permitió el uso compartido de invitado al crear la etiqueta confidencial, asegúrese de que **Invitados nuevos y existentes** está seleccionado. Si no ha permitió el uso compartido cuando creó la etiqueta, elija **Solo las personas de la organización**.
6. En Tipo de vínculo de uso compartido predeterminado, desactive la casilla de verificación **Igual que la configuración de nivel de organización** y seleccione **Usuarios con acceso existente**.
7. Haga clic en **Guardar**.

#### <a name="private-channels"></a>Canales privados

Si agrega canales privados al equipo, cada canal privado crea un sitio de SharePoint nuevo con la configuración de uso compartido predeterminada. Estos sitios no están visibles en el Centro de administración de SharePoint, por lo que debe usar el cmdlet [Set-SPOSite](https://docs.microsoft.com/powershell/module/sharepoint-online/set-sposite) de PowerShell con los siguientes parámetros para actualizar la configuración de uso compartido de invitados:

- `-SharingCapability Disabled` para desactivar el uso compartido de invitados (está activado de forma predeterminada)
- `-DefaultSharingLinkType Internal` para cambiar el vínculo para compartir predeterminado a *Usuarios específicos*

Si no tiene previsto usar canales privados con su equipo, puede desactivar la posibilidad de que los miembros del equipo los creen en **Permisos de los miembros** en [Configuración de equipo](https://support.microsoft.com/office/ce053b04-1b8e-4796-baa8-90dc427b3acc).

### <a name="site-sharing-settings"></a>Configuración de uso compartido del sitio 

Para ayudar a garantizar que el sitio de SharePoint no se comparta con personas que no son miembros del equipo, limitamos dicho uso compartido a los propietarios. También limitamos el uso compartido de archivos y carpetas a los propietarios del equipo. Esto permite asegurar que los propietarios son conscientes siempre que se comparte un archivo con alguien ajeno al equipo.

Para configurar el uso compartido del sitio solo para propietarios
1. En Teams, vaya a la pestaña **General** del equipo que quiere actualizar.
2. En la barra de herramientas del equipo, haga clic en **Archivos**.
3. Haga clic en los puntos suspensivos y, luego, en **Abrir en SharePoint**.
4. En la barra de herramientas, haga clic en el sitio de SharePoint subyacente, en el icono de configuración y, luego, en **Permisos del sitio**.
5. En el panel Permisos del sitio, en **Configuración de uso compartido**, haga clic en **Cambiar configuración de uso compartido**.
6. En **Permisos de uso compartido**, seleccione **Solo los propietarios del sitio pueden compartir archivos, carpetas, además del sitio** y, luego, haga clic en **Guardar**.

### <a name="custom-site-permissions"></a>Permisos del sitio personalizados

Si ha agregado personas con permiso de espectador en la etiqueta de confidencialidad, puede agregarlos al sitio de SharePoint con el acceso de lectura para que tengan acceso a los archivos fácilmente.

Para agregar a usuarios al sitio
1. En el sitio, haga clic en el icono de configuración y luego en **Permisos del sitio**.
2. Haga clic en **Invitar a personas** y, después, en **Compartir solo el sitio**.
3. Escriba los nombres de los usuarios y grupos a los que desea invitar.
4. Para cada persona o grupo que agregue, cambie sus permisos de **Edición** a **Lectura**.
5. Elija si quiere enviarles un correo electrónico con un vínculo al sitio.
6. Haga clic en **Agregar**.

## <a name="additional-protections"></a>Protecciones adicionales

Microsoft 365 ofrece otros métodos para proteger el contenido. Considere si las siguientes opciones ayudarían a mejorar la seguridad de su organización.

- Hacer que los invitados acepten los [términos de uso](https://docs.microsoft.com/azure/active-directory/conditional-access/terms-of-use).
- Configurar una [directiva de tiempo de espera de sesión](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-session-lifetime) para invitados
- Crear [tipos de información confidencial](https://docs.microsoft.com/microsoft-365/compliance/custom-sensitive-info-types) y usar [protección de pérdida de datos](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies) para establecer directivas en relación con el acceso a información confidencial.
- Use revisiones de [acceso de Azure Active Directory](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview) para revisar periódicamente el acceso al equipo y la afiliación.

## <a name="drive-user-adoption-for-team-members"></a>Fomentar que los miembros del equipo usen las funcionalidades

Una vez que el equipo esté listo, es hora de impulsar la adopción de este equipo y la seguridad adicional para los miembros del equipo.

### <a name="train-your-users"></a>Proporcione formación a los usuarios

Los miembros del equipo pueden acceder al equipo y a todos sus recursos, incluidos los chats, las reuniones y otras aplicaciones. Al trabajar con archivos de la sección **Archivos** de un canal, los miembros del equipo deben asignar la etiqueta de confidencialidad a los archivos creados.

Cuando la etiqueta se aplica al archivo, está protegido. Los miembros del equipo pueden abrirlo y colaborar en tiempo real. Si el archivo abandona el sitio y se reenvía a un usuario malintencionado, este tendrá que proporcionar credenciales de una cuenta de usuario que sea miembro del equipo para abrir el archivo y ver su contenido. 

Entrenar a los miembros del equipo:

- Sobre la importancia de usar el nuevo equipo para los chats, las reuniones, los archivos y los demás recursos del sitio de SharePoint y las consecuencias de la filtración de datos altamente regulados, tales como las repercusiones legales, las multas, el ramsonware o la pérdida de ventaja frente a la competencia.
- Cómo acceder al equipo.
- Cómo crear archivos nuevos en el sitio o cargar archivos nuevos almacenados de forma local.
- Cómo etiquetar archivos con la etiqueta de confidencialidad adecuada para el equipo.
- Cómo la etiqueta protege los archivos incluso cuando se filtran del sitio.

Esta formación debería incluir ejercicios prácticos para que los miembros del equipo puedan experimentar con las funcionalidades y sus resultados.

### <a name="conduct-periodic-reviews-of-usage-and-address-team-member-feedback"></a>Realice revisiones periódicas de uso y responda a los comentarios de los miembros del equipo

En las semanas después de la formación haga lo siguiente:

- Responda rápidamente a los comentarios de los miembros del equipo y ajuste las directivas y las configuraciones.
- Analice el uso del equipo y compárelo con las expectativas de uso.
- Compruebe que los archivos altamente regulados se hayan etiquetado de forma correcta con la etiqueta de confidencialidad. (Puede ver qué archivos tienen una etiqueta asignada viendo una carpeta en SharePoint y añadiendo la columna **Confidencialidad** a través de la opción **Mostrar/ocultar columnas** que está en **Añadir columna**).

Volver a dar formación a los usuarios que lo necesiten.

## <a name="see-also"></a>Consulte también

[Azure AD Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-configure)
