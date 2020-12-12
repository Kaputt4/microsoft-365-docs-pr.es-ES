---
title: Colaborar con invitados en un documento
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
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
description: En este artículo, aprenderá a colaborar con invitados en un documento de SharePoint y OneDrive.
ms.openlocfilehash: 1b2fe003902b69e4c0c58852af67862ce6f2eb34
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663516"
---
# <a name="collaborate-with-guests-on-a-document"></a>Colaborar con invitados en un documento

Si necesita colaborar con personas fuera de su organización en documentos de SharePoint o OneDrive, puede enviarles un vínculo de uso compartido al documento. En este artículo, analizaremos los pasos de configuración de Microsoft 365 necesarios para configurar los vínculos de uso compartido de SharePoint y OneDrive según las necesidades de su organización.

## <a name="video-demonstration"></a>Vídeo de demostración

En este vídeo se muestran los pasos de configuración que se describen en este documento.</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE450Vt?autoplay=false]

## <a name="azure-external-collaboration-settings"></a>Configuración de colaboración externa de Azure

El uso compartido en Microsoft 365 se rige en su nivel más alto por la [configuración de colaboración externa B2B en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations). Si el uso compartido de invitado está deshabilitado o restringido en Azure AD, esta configuración invalida cualquier configuración de uso compartido que configure en Microsoft 365.

Compruebe la configuración de colaboración externa B2B para asegurarse de que no se bloquee el uso compartido con invitados.

![Captura de pantalla de la página de configuración de relaciones de organización de Azure Active Directory](../media/azure-ad-organizational-relationships-settings.png)

Para establecer la configuración de colaboración externa

1. Inicie sesión en Azure Active Directory en [https://aad.portal.azure.com](https://aad.portal.azure.com) .
2. En el panel de navegación izquierdo, haga clic en **Azure Active Directory**.
3. Haga clic en **identidades externas**.
4. En la **pantalla introducción** , en el panel de navegación de la izquierda, haga clic en **configuración de colaboración externa**.
5. Asegúrese de que los **administradores y los usuarios de la función invitador invitado puedan** invitar y que **los miembros puedan invitar** están establecidos en **sí**.
6. Si ha realizado cambios, haga clic en **Guardar**.

Anote la configuración de la sección **restricciones de colaboración** . Asegúrese de que los dominios de los invitados con los que desea colaborar no están bloqueados.

Si trabaja con invitados de varias organizaciones, es posible que desee restringir su capacidad para obtener acceso a los datos del directorio. Esto impedirá que vean quién más es un invitado en el directorio. Para ello, en **restricciones de acceso de usuarios invitados**, seleccione **los usuarios invitados tienen restringido el acceso a las propiedades y la pertenencia de los objetos de directorio la configuración** o **el acceso de usuario invitado está restringido a las propiedades y pertenencia de sus propios objetos de directorio**.

## <a name="sharepoint-organization-level-sharing-settings"></a>Configuración de uso compartido en el nivel de la organización de SharePoint

Para que las personas de fuera de la organización tengan acceso a un documento en SharePoint o OneDrive, la configuración de uso compartido en el nivel de la organización de SharePoint y OneDrive debe permitir el uso compartido con personas de fuera de la organización.

La configuración de nivel de organización para SharePoint determina la configuración que estará disponible para los sitios de SharePoint individuales. La configuración del sitio no puede ser más permisiva que la configuración de nivel de organización. La configuración en el nivel de la organización para OneDrive determina el nivel de uso compartido que estará disponible en las bibliotecas de OneDrive de los usuarios.

Para SharePoint y OneDrive, si quiere permitir el uso compartido de archivos y carpetas sin autenticar, elija **cualquier persona**. Si quiere asegurarse de que las personas de fuera de su organización tengan que autenticarse, elija los **invitados nuevos y existentes**. *Todos* los vínculos es la forma más sencilla de compartir: los usuarios ajenos a la organización pueden abrir el vínculo sin autenticación y tienen la posibilidad de pasarlo a otros.

Para SharePoint, elija la configuración más permisiva que necesitará cualquier sitio de la organización.

![Captura de pantalla de la configuración de uso compartido en el nivel de organización de SharePoint](../media/sharepoint-organization-external-sharing-controls.png)


Para establecer la configuración de uso compartido en el nivel de la organización de SharePoint

1. En el centro de administración de Microsoft 365, en el panel de navegación izquierdo, en **centros de administración**, haga clic en **SharePoint**.
2. En el centro de administración de SharePoint, en el panel de navegación izquierdo, en **directivas**, haga clic en **uso compartido**.
3. Asegúrese de que el uso compartido externo para SharePoint o OneDrive está establecido en **cualquiera** o **invitados nuevos o existentes**. (Tenga en cuenta que la configuración de OneDrive no puede ser más permisiva que la configuración de SharePoint).
4. Si ha realizado cambios, haga clic en **Guardar**.

## <a name="sharepoint-organization-level-default-link-settings"></a>Configuración de vínculos predeterminados de nivel de organización de SharePoint

La configuración predeterminada de los vínculos de archivos y carpetas determina la opción de vínculo que se mostrará a los usuarios de forma predeterminada cuando compartan un archivo o una carpeta. Los usuarios pueden cambiar el tipo de vínculo a una de las otras opciones antes de compartirlo, si lo deseas.

Tenga en cuenta que esta configuración afecta a los sitios de SharePoint de su organización, así como a OneDrive.

Elija un vínculo en cualquiera de los siguientes tipos que, a continuación, se selecciona de forma predeterminada cuando los usuarios comparten archivos y carpetas:

- **Cualquiera que tenga el vínculo** : elija esta opción si tiene previsto compartir una gran cantidad de archivos y carpetas sin autenticar. Si desea permitir que *todos* los vínculos, pero le preocupa el uso compartido no autenticado accidentalmente, considere una de las otras opciones como predeterminada. Este tipo de vínculo solo está disponible si ha habilitado a **todos los usuarios** que comparten el mismo.
- **Solo las personas de su organización** : elija esta opción si prevé que la mayoría del uso compartido de archivos y carpetas sea para personas dentro de la organización.
- **Personas específicas** : considere esta opción si espera compartir muchos archivos y carpetas con los invitados. Este tipo de vínculo funciona con los invitados y requiere que se autentiquen.
 
![Captura de pantalla de la configuración de uso compartido de los archivos y carpetas de nivel de organización de SharePoint ](../media/sharepoint-organization-files-folders-sharing-settings.png)


Para establecer la configuración de vínculos predeterminados de nivel de organización de SharePoint y OneDrive

1. Vaya a la página de uso compartido en el centro de administración de SharePoint.
2. En **vínculos de archivos y carpetas**, seleccione el vínculo de uso compartido predeterminado que desee usar.
3. Si ha realizado cambios, haga clic en **Guardar**.

Para establecer el permiso para el vínculo para compartir, en **elegir el permiso que está seleccionado de forma predeterminada para los vínculos para compartir.**

1. Seleccione **Ver** si no desea que los usuarios no autenticados realicen cambios en los archivos y carpetas.
2. Seleccione **Editar** si desea permitir que los usuarios no autenticados realicen cambios en los archivos y las carpetas.

Tenga en cuenta que las dos opciones de PREUSO anteriores pueden aplicarse no solo a los usuarios invitados o externos, sino también a los usuarios internos. La opción de permiso que elija está determinada por su propia discreción.

Para establecer permisos para vínculos que permiten el uso compartido con cualquiera

1. En **estos vínculos puede conceder estos permisos:** subpanel, 
    1. En la lista desplegable **archivos** , 
        - Seleccione **ver y editar** si desea permitir que los usuarios no autenticados realicen cambios en los archivos.
        - Seleccione **Ver** si no desea que los usuarios no autenticados realicen cambios en los archivos.
    2. En la lista desplegable **carpetas** ,
        - Seleccione **ver, editar y cargar** si desea permitir que los usuarios no autenticados realicen cambios en las carpetas.
        - Seleccione **Ver** si no desea que los usuarios no autenticados realicen cambios en las carpetas.

## <a name="sharepoint-site-level-sharing-settings"></a>Configuración de uso compartido en el nivel de sitio de SharePoint

Si está compartiendo archivos y carpetas que están en un sitio de SharePoint, también debe comprobar la configuración de uso compartido de nivel de sitio para ese sitio.

![Captura de pantalla de la configuración de uso compartido externo del sitio de SharePoint](../media/sharepoint-site-external-sharing-settings.png)

Para establecer la configuración de uso compartido de nivel de sitio

1. En el centro de administración de SharePoint, en el panel de navegación izquierdo, expanda **sitios** y haga clic en **sitios activos**.
2. Seleccione el sitio en el que desea compartir archivos y carpetas con los invitados.
3. Desplácese hacia la derecha por la fila (en la que está presente el sitio seleccionado) y haga clic en cualquier lugar de la columna **uso compartido externo** .
4. En la página que aparece, haga clic en la ficha **directivas** .
5. En el panel **uso compartido externo** , haga clic en **Editar**.
6. Asegúrese de que el uso compartido está establecido en **todos** o en **invitados nuevos o existentes**.
7. Si ha realizado cambios, haga clic en **Guardar**.

## <a name="invite-users"></a>Invitar a usuarios

La configuración del uso compartido de invitados ya está configurada; por lo tanto, ahora los usuarios pueden compartir archivos y carpetas con personas de fuera de la organización. Consulte [compartir archivos y carpetas de OneDrive](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) y [compartir archivos o carpetas de SharePoint](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) para obtener más información.

## <a name="see-also"></a>Vea también

[Prácticas recomendadas para compartir archivos y carpetas con usuarios no autenticados](best-practices-anonymous-sharing.md)

[Reducir la exposición accidental de archivos al compartirlos con invitados](share-limit-accidental-exposure.md)

[Integración de SharePoint y OneDrive con la B2B de Azure AD](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)
