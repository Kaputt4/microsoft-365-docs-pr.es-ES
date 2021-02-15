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
description: En este artículo, aprenderá a colaborar con invitados en un documento en SharePoint y OneDrive.
ms.openlocfilehash: 1b2fe003902b69e4c0c58852af67862ce6f2eb34
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663516"
---
# <a name="collaborate-with-guests-on-a-document"></a>Colaborar con invitados en un documento

Si necesita colaborar con personas de fuera de su organización en documentos de SharePoint o OneDrive, puede enviarles un vínculo para compartir al documento. En este artículo, veremos los pasos de configuración de Microsoft 365 necesarios para configurar vínculos de uso compartido para SharePoint y OneDrive para las necesidades de su organización.

## <a name="video-demonstration"></a>Vídeo de demostración

En este vídeo se muestran los pasos de configuración descritos en este documento.</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE450Vt?autoplay=false]

## <a name="azure-external-collaboration-settings"></a>Configuración de colaboración externa de Azure

El uso compartido en Microsoft 365 se rige en su nivel más alto por la configuración de [colaboración externa B2B en Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations) Si el uso compartido de invitados está deshabilitado o restringido en Azure AD, esta configuración invalida cualquier configuración de uso compartido que configure en Microsoft 365.

Compruebe la configuración de colaboración externa B2B para asegurarse de que no se bloquee el uso compartido con invitados.

![Captura de pantalla de la página de configuración de relaciones de organización de Azure Active Directory](../media/azure-ad-organizational-relationships-settings.png)

Para establecer la configuración de colaboración externa

1. Inicie sesión en Azure Active Directory en [https://aad.portal.azure.com](https://aad.portal.azure.com) .
2. En el panel de navegación izquierdo, haga clic **en Azure Active Directory.**
3. Haga **clic en Identidades externas.**
4. En la **pantalla Introducción,** en el panel de navegación izquierdo, haga clic en **Configuración de colaboración externa.**
5. Asegúrese de **que los administradores y los usuarios del** rol de invitador de invitado pueden invitar y que **los** miembros pueden invitar están establecidos en **Sí**.
6. Si ha realizado cambios, haga clic en **Guardar**.

Tenga en cuenta la configuración de la **sección Restricciones de colaboración.** Asegúrese de que los dominios de los invitados con los que desea colaborar no están bloqueados.

Si trabaja con invitados de varias organizaciones, es posible que desee restringir su capacidad para obtener acceso a los datos del directorio. Esto les impedirá ver quién más es un invitado en el directorio. Para ello, en Restricciones de  acceso de usuario invitado, seleccione Usuarios **invitados** tienen acceso limitado a las propiedades y la pertenencia a la configuración de objetos de directorio o el acceso de usuarios invitados está restringido a las propiedades y pertenencias a sus **propios** objetos de directorio.

## <a name="sharepoint-organization-level-sharing-settings"></a>Configuración de uso compartido en el nivel de organización de SharePoint

Para que las personas de fuera de su organización tengan acceso a un documento en SharePoint o OneDrive, la configuración de uso compartido en el nivel de organización de SharePoint y OneDrive debe permitir el uso compartido con personas externas a la organización.

La configuración de nivel de organización de SharePoint determina la configuración que estará disponible para sitios individuales de SharePoint. La configuración del sitio no puede ser más permisiva que la configuración de nivel de organización. La configuración de nivel de organización de OneDrive determina el nivel de uso compartido que estará disponible en las bibliotecas de OneDrive de los usuarios.

Para SharePoint y OneDrive, si desea permitir el uso compartido de archivos y carpetas sin autenticar, elija **Cualquiera**. Si desea asegurarse de que las personas fuera de su organización tienen que autenticarse, elija **Invitados nuevos y existentes.** *Cualquiera* de los vínculos es la forma más sencilla de compartir: las personas de fuera de su organización pueden abrir el vínculo sin autenticación y pueden pasarlo a otros usuarios.

Para SharePoint, elija la configuración más permisiva que necesita cualquier sitio de su organización.

![Captura de pantalla de la configuración de uso compartido en el nivel de organización de SharePoint](../media/sharepoint-organization-external-sharing-controls.png)


Para establecer la configuración de uso compartido en el nivel de organización de SharePoint

1. En el Centro de administración de Microsoft 365, en el panel de navegación izquierdo, en Centros de **administración,** haga clic **en SharePoint.**
2. En el Centro de administración de SharePoint, en el panel de navegación izquierdo, en **Directivas,** haga clic en **Compartir.**
3. Asegúrese de que el uso compartido externo para SharePoint o OneDrive esté establecido en **Cualquiera** o **en Invitados nuevos y existentes.** (Tenga en cuenta que la configuración de OneDrive no puede ser más permisiva que la configuración de SharePoint).
4. Si ha realizado cambios, haga clic en **Guardar**.

## <a name="sharepoint-organization-level-default-link-settings"></a>Configuración de vínculos predeterminada en el nivel de organización de SharePoint

La configuración predeterminada de vínculos de archivos y carpetas determina la opción de vínculo que se mostrará a los usuarios de forma predeterminada cuando compartan un archivo o carpeta. Los usuarios pueden cambiar el tipo de vínculo a una de las otras opciones antes de compartir, si lo desean.

Tenga en cuenta que esta configuración afecta a los sitios de SharePoint de su organización, así como a OneDrive.

Elija un vínculo de cualquiera de los siguientes tipos que, a continuación, se selecciona de forma predeterminada cuando los usuarios comparten archivos y carpetas:

- **Cualquiera con el vínculo:** elija esta opción si espera realizar una gran cantidad de uso compartido de archivos y carpetas no autenticados. Si desea permitir *vínculos* cualquiera pero le preocupa el uso compartido accidental no autenticado, considere una de las otras opciones como predeterminada. Este tipo de vínculo solo está disponible si ha habilitado el uso compartido **cualquiera.**
- **Solo las personas de su organización:** elija esta opción si espera que la mayoría del uso compartido de archivos y carpetas esté con personas dentro de la organización.
- **Usuarios específicos:** considere esta opción si espera compartir muchos archivos y carpetas con invitados. Este tipo de vínculo funciona con invitados y requiere que se autentiquen.
 
![Captura de pantalla de la configuración de uso compartido de los archivos y carpetas de nivel de organización de SharePoint ](../media/sharepoint-organization-files-folders-sharing-settings.png)


Para establecer la configuración predeterminada de vínculos de nivel de organización de SharePoint y OneDrive

1. Vaya a la página Uso compartido en el Centro de administración de SharePoint.
2. En **Vínculos de archivos y** carpetas, seleccione el vínculo para compartir predeterminado que desea usar.
3. Si ha realizado cambios, haga clic en **Guardar**.

Para establecer el permiso para el vínculo para compartir, en Elija el permiso que está seleccionado de forma predeterminada para **los vínculos para compartir.**

1. Seleccione **Ver** si no desea que los usuarios no autenticados realicen cambios en los archivos y carpetas.
2. Seleccione **Editar** si desea permitir que los usuarios no autenticados realicen cambios en los archivos y carpetas.

Tenga en cuenta que las dos opciones de reenvío anteriores se pueden aplicar no solo para invitados o usuarios externos, sino también para usuarios internos. La opción de permiso que elija viene determinada por la discreción propia.

Para establecer permisos para vínculos que permiten compartir con cualquier persona

1. En estos **vínculos se pueden conceder estos permisos:** sub-panel, 
    1. En la **lista** desplegable Archivos, 
        - Seleccione **Ver y editar** si desea permitir que los usuarios no autenticados realicen cambios en los archivos.
        - Seleccione **Ver** si no desea que los usuarios no autenticados realicen cambios en los archivos.
    2. En la **lista** desplegable Carpetas,
        - Seleccione **Ver, editar y cargar** si desea permitir que los usuarios no autenticados realicen cambios en las carpetas.
        - Seleccione **Ver** si no desea que los usuarios no autenticados realicen cambios en las carpetas.

## <a name="sharepoint-site-level-sharing-settings"></a>Configuración de uso compartido en el nivel de sitio de SharePoint

Si está compartiendo archivos y carpetas que se encuentran en un sitio de SharePoint, también debe comprobar la configuración de uso compartido de nivel de sitio para ese sitio.

![Captura de pantalla de la configuración de uso compartido externo del sitio de SharePoint](../media/sharepoint-site-external-sharing-settings.png)

Para establecer la configuración de uso compartido de nivel de sitio

1. En el Centro de administración de SharePoint, en el panel de navegación izquierdo, expanda **Sitios** y haga clic **en Sitios activos.**
2. Seleccione el sitio en el que desea compartir archivos y carpetas con invitados.
3. Desplácese a la derecha por la fila (en la que está presente el sitio seleccionado) y haga clic en cualquier parte de la **columna Uso compartido** externo.
4. En la página que aparece, haga clic en **la pestaña** Directivas.
5. En el **panel Uso compartido** externo, haga clic en **Editar**.
6. Asegúrese de que el uso compartido está establecido en **Cualquiera** o **Invitados nuevos y existentes.**
7. Si ha realizado cambios, haga clic en **Guardar**.

## <a name="invite-users"></a>Invitar a usuarios

La configuración de uso compartido de invitados ya está configurada; para que los usuarios puedan compartir archivos y carpetas con personas de fuera de la organización. Vea [Compartir archivos y carpetas de OneDrive](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) y archivos o carpetas de [SharePoint para](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) obtener más información.

## <a name="see-also"></a>Vea también

[Prácticas recomendadas para compartir archivos y carpetas con usuarios no autenticados](best-practices-anonymous-sharing.md)

[Reducir la exposición accidental de archivos al compartirlos con invitados](share-limit-accidental-exposure.md)

[Integración de SharePoint y OneDrive con Azure AD B2B](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)
