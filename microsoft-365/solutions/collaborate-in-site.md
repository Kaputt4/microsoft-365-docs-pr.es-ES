---
title: Colaborar con invitados en un sitio
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-3tiersprotection
- m365solution-securecollab
- m365initiative-externalcollab
ms.custom:
- seo-marvel-apr2020
localization_priority: Normal
f1.keywords: NOCSH
description: Obtenga información sobre los pasos de configuración de Microsoft 365 necesarios para configurar un sitio de SharePoint para la colaboración con los invitados.
ms.openlocfilehash: df9068ef4b4eb35f946b78d8f7fefa01c254c79c
ms.sourcegitcommit: 8a726ed7ec19a8728c079780fa4d343a5f759fbb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2020
ms.locfileid: "49029998"
---
# <a name="collaborate-with-guests-in-a-site"></a>Colaborar con invitados en un sitio

Si necesita colaborar con invitados en documentos, datos y listas, puede usar un sitio de SharePoint. Los sitios modernos de SharePoint están conectados a grupos de 365 de Microsoft y pueden administrar la pertenencia al sitio y proporcionar herramientas de colaboración adicionales, como un buzón compartido y un calendario.

En este artículo, analizaremos los pasos de configuración de Microsoft 365 necesarios para configurar un sitio de SharePoint para la colaboración con los invitados.

## <a name="video-demonstration"></a>Vídeo de demostración

En este vídeo se muestran los pasos de configuración que se describen en este documento.</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44Llg?autoplay=false]

## <a name="azure-external-collaboration-settings"></a>Configuración de colaboración externa de Azure

El uso compartido en Microsoft 365 se rige en su nivel más alto por la [configuración de relaciones organizativas en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations). Si el uso compartido de invitado está deshabilitado o restringido en Azure AD, esta configuración invalida cualquier configuración de uso compartido que configure en Microsoft 365.

Compruebe la configuración de colaboración externa para asegurarse de que no se bloquee el uso compartido con invitados.

![Captura de pantalla de la página de configuración de colaboración externa de Azure Active Directory](../media/azure-ad-organizational-relationships-settings.png)

Para establecer la configuración de colaboración externa

1. Inicie sesión en Azure Active Directory en [https://aad.portal.azure.com](https://aad.portal.azure.com) .
2. En el panel de navegación izquierdo, haga clic en **Azure Active Directory**.
3. Haga clic en **identidades externas**.
4. En la **pantalla introducción** , en el panel de navegación de la izquierda, haga clic en **configuración de colaboración externa**.
5. Asegúrese de que los **administradores y los usuarios de la función invitador invitado puedan** invitar y que **los miembros puedan invitar** están establecidos en **sí**.
6. Si ha realizado cambios, haga clic en **Guardar**.

Anote la configuración de la sección **restricciones de colaboración** . Asegúrese de que los dominios de los invitados con los que desea colaborar no están bloqueados.

Si trabaja con invitados de varias organizaciones, es posible que desee restringir su capacidad para obtener acceso a los datos del directorio. Esto impedirá que vean quién más es un invitado en el directorio. Para ello, en **restricciones de acceso de usuarios invitados** , seleccione **los usuarios invitados tienen restringido el acceso a las propiedades y la pertenencia de los objetos de directorio la configuración** o **el acceso de usuario invitado está restringido a las propiedades y pertenencia de sus propios objetos de directorio**.

## <a name="microsoft-365-groups-guest-settings"></a>Configuración de invitado de Microsoft 365 Groups

Los sitios modernos de SharePoint usan grupos de Microsoft 365 para controlar el acceso al sitio. La configuración de invitado de Microsoft 365 Groups debe estar activada para que el acceso de invitado en los sitios de SharePoint funcione.

![Captura de pantalla de la configuración de invitados de los grupos de Microsoft 365 en el Centro de administración de Microsoft 365](../media/office-365-groups-guest-settings.png)

Para establecer la configuración de invitado de Microsoft 365 Groups

1. En el centro de administración de Microsoft 365, en el panel de navegación izquierdo, expanda **configuración**.
2. Haga clic en configuración de la **organización**.
3. En la lista, haga clic en **grupos de 365 de Microsoft**.
4. Asegúrese de que los **propietarios del grupo Let agreguen personas externas a la organización a Microsoft 365 Groups As Guests** y **permita a los miembros del grupo de invitados tener acceso a** las casillas de verificación contenido del grupo.
5. Si ha realizado cambios, haga clic en **Guardar cambios**.

## <a name="sharepoint-organization-level-sharing-settings"></a>Configuración de uso compartido en el nivel de la organización de SharePoint

Para que los invitados tengan acceso a los sitios de SharePoint, la configuración de uso compartido en el nivel de la organización de SharePoint debe permitir el uso compartido con invitados.

La configuración en el nivel de la organización determina la configuración que estará disponible para cada uno de los sitios. La configuración del sitio no puede ser más permisiva que la configuración de nivel de organización.

Si desea permitir el uso compartido de archivos y carpetas sin autenticar, elija **cualquiera**. Si desea asegurarse de que todos los usuarios ajenos a la organización tienen que autenticarse, elija los **invitados nuevos y existentes**. Elija la configuración más permisiva que necesitará cualquier sitio de la organización.

![Captura de pantalla de la configuración de uso compartido en el nivel de organización de SharePoint](../media/sharepoint-organization-external-sharing-controls.png)


Para establecer la configuración de uso compartido en el nivel de la organización de SharePoint

1. En el centro de administración de Microsoft 365, en el panel de navegación izquierdo, en **centros de administración** , haga clic en **SharePoint**.
2. En el centro de administración de SharePoint, en el panel de navegación izquierdo, en **directivas** , haga clic en **uso compartido**.
3. Asegúrese de que el uso compartido externo para SharePoint está establecido en **todos** o en **invitados nuevos o existentes**.
4. Si ha realizado cambios, haga clic en **Guardar**.

## <a name="create-a-site"></a>Crear un sitio

El siguiente paso es crear el sitio que va a usar para colaborar con los invitados.

Para crear un sitio
1. En el Centro de administración de SharePoint, en **Sitios** , haga clic en **Sitios activos**.
2. Haga clic en **Crear**.
3. Haga clic en **sitio de grupo**.
4. Escriba un nombre de sitio y escriba un nombre para el propietario del grupo (propietario del sitio).
5. En **Configuración avanzada** , elija si desea que este sitio sea público o privado.
6. Haga clic en **Siguiente**.
7. Haga clic en **Finalizar**.

Invitaremos a los usuarios más adelante. A continuación, es importante comprobar la configuración de uso compartido de nivel de sitio para este sitio.

## <a name="sharepoint-site-level-sharing-settings"></a>Configuración de uso compartido en el nivel de sitio de SharePoint

Compruebe la configuración de uso compartido de nivel de sitio para asegurarse de que permite el tipo de acceso que desea para este sitio. Por ejemplo, si establece la configuración de nivel de organización en **cualquiera** , pero desea que todos los invitados se autentiquen en este sitio, asegúrese de que la configuración de uso compartido de nivel de sitio esté establecida en **invitados nuevos y existentes**.

Tenga en cuenta que no se puede compartir el sitio con personas no autenticadas (configuración de **cualquier persona** ), pero puede que los archivos y las carpetas individuales.

![Captura de pantalla de la configuración de uso compartido externo del sitio de SharePoint](../media/sharepoint-site-external-sharing-settings.png)

Para establecer la configuración de uso compartido de nivel de sitio
1. En el Centro de administración de SharePoint, en el panel de navegación izquierdo, expanda **Sitios** y haga clic en **Sitios activos**.
2. Seleccione el sitio que desea compartir.
3. Haga clic en... y haga clic en **compartir**.
4. Asegúrese de que el uso compartido está establecido en **todos** o en **invitados nuevos o existentes**.
5. Si ha realizado cambios, haga clic en **Guardar**.

## <a name="invite-users"></a>Invitar a usuarios

La configuración de uso compartido de invitados ya está configurada, por lo que puede empezar a agregar invitados y usuarios internos a su sitio. El acceso al sitio se controla a través del grupo de Microsoft 365 asociado, por lo que vamos a agregar a los usuarios.

Para invitar a usuarios internos a un grupo
1. Navegue hasta el sitio en el que desea agregar usuarios.
2. Haga clic en el vínculo **miembros** en la esquina superior derecha, que denota el recuento de miembros.
3. Haga clic en **Agregar miembros**.
4. Escriba los nombres o las direcciones de correo electrónico de los usuarios que desea invitar al sitio y, a continuación, haga clic en **Guardar**.

No se pueden agregar usuarios invitados desde el sitio. Debe agregarlos mediante Outlook en la Web. Por lo tanto, como requisito previo para agregar e invitar invitados a un grupo, haga clic en la dirección URL del sitio en la columna **dirección URL**  para ir a la página específica del sitio. En esta página, haga clic en el icono del **iniciador de aplicaciones** y seleccione **Outlook**. Esta es la pantalla desde la que puede invitar a los invitados a un grupo, para qué procedimiento se describe a continuación.

Para invitar a invitados a un grupo
1. En **grupos** , haga clic en el grupo al que desea invitar a los invitados.
2. Abra la tarjeta de contacto de grupo y haga clic en vínculo de **miembros** en la esquina superior derecha (el vínculo que indica el recuento de miembros).
3. Haga clic en **Agregar miembros**.
4. Escriba las direcciones de correo electrónico de los invitados que desea invitar y, a continuación, haga clic en **Agregar**.
5. Haga clic en **Cerrar**.
Tenga en cuenta que debe hacer clic en **cerrar** solo si no es el propietario del grupo y, como resultado, no tiene permiso para agregar el invitado al grupo. En estos casos, la solicitud para agregar el invitado al grupo se transfiere al propietario del grupo para su aprobación.

## <a name="see-also"></a>Vea también

[Prácticas recomendadas para compartir archivos y carpetas con usuarios no autenticados](best-practices-anonymous-sharing.md)

[Reducir la exposición accidental de archivos al compartirlos con invitados](share-limit-accidental-exposure.md)

[Crear un entorno seguro de uso compartido para invitados](create-secure-guest-sharing-environment.md)

Para obtener más información, consulte [Crear una extranet de B2B con invitados administrados](b2b-extranet.md).

[Integración de SharePoint y OneDrive con la B2B de Azure AD](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)
