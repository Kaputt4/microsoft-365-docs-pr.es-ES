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
- admindeeplinkSPO
ms.localizationpriority: medium
f1.keywords: NOCSH
recommendations: false
description: Obtenga información sobre los pasos de configuración de Microsoft 365 necesarios para configurar un sitio de SharePoint para la colaboración con invitados.
ms.openlocfilehash: 6814eb2dd1d0876c332a7be932fc8c59a43f198c
ms.sourcegitcommit: 48a75b40e607542e5fe219b6e75ffc757804a9c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/16/2022
ms.locfileid: "67344655"
---
# <a name="collaborate-with-guests-in-a-site"></a>Colaborar con invitados en un sitio

Si necesita colaborar con invitados en documentos, datos y listas, puede usar un sitio de SharePoint. Los sitios modernos de SharePoint están conectados a Grupos de Microsoft 365 y pueden administrar la pertenencia al sitio y proporcionar herramientas de colaboración adicionales, como un buzón compartido y un calendario.

En este artículo, le guiaremos por los pasos de configuración de Microsoft 365 necesarios para configurar un sitio de SharePoint para la colaboración con invitados.

## <a name="video-demonstration"></a>Demostración de vídeo

En este vídeo se muestran los pasos de configuración descritos en este documento.</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44Llg?autoplay=false]

## <a name="azure-external-collaboration-settings"></a>Configuración de colaboración externa de Azure

El uso compartido en Microsoft 365 se rige en su nivel más alto por la [configuración de colaboración externa B2B en Azure Active Directory](/azure/active-directory/external-identities/delegate-invitations). Si el uso compartido con invitados está deshabilitado o restringido en Azure AD, esta configuración invalida cualquier configuración de uso compartido que configure en Microsoft 365.

Compruebe la configuración de colaboración externa B2B para asegurarse de que no se ha bloqueado el uso compartido con invitados.

![Captura de pantalla de la página Configuración de colaboración externa de Azure Active Directory.](../media/azure-ad-organizational-relationships-settings.png)

Para establecer la configuración de colaboración externa

1. Inicie sesión en Azure Active Directory en [https://aad.portal.azure.com](https://aad.portal.azure.com).
2. En el panel de navegación izquierdo, haga clic en **Azure Active Directory**
3. Haga clic en **Identidades externas**.
4. En la pantalla **introducción**, en el panel de navegación izquierdo, haga clic en **Configuración de colaboración externa**.
5. Asegúrese de que **Los usuarios miembros y usuarios asignados a roles de administrador específicos pueden invitar a usuarios invitados, incluidos los invitados con permisos de miembro** o **Cualquier usuario de la organización puede invitar a usuarios invitados, incluidos invitados y no administradores** está seleccionado.
6. Si ha realizado cambios, haga clic en **Guardar**.

Fíjese en la configuración en la sección **Restricciones de colaboración**. Asegúrese de que los dominios de los invitados con los que quiere colaborar no están bloqueados.

Si trabaja con invitados de varias organizaciones, tal vez quiera restringir su capacidad para acceder a los datos del directorio. Esto les impedirá ver quién más es un invitado en el directorio. Para ello, en **Restricciones de acceso de usuario invitado**, seleccione **Los usuarios invitados tienen acceso limitado a las propiedades y a la pertenencia de la configuración de objetos de directorio** o **El acceso de usuarios invitados está restringido a las propiedades y pertenencias de sus propios objetos de directorio**.

## <a name="microsoft-365-groups-guest-settings"></a>Configuración de invitados de Grupos de Microsoft 365

Los sitios modernos de SharePoint usan Grupos de Microsoft 365 para controlar el acceso al sitio. La configuración de invitado Grupos de Microsoft 365 debe estar activada para que funcione el acceso de invitado en sitios de SharePoint.

![Captura de pantalla de la configuración de invitados de Grupos de Microsoft 365 en el Centro de administración de Microsoft 365.](../media/office-365-groups-guest-settings.png)

Para establecer la configuración de invitados de Grupos de Microsoft 365

1. En el Centro de administración de Microsoft 365, en el panel de navegación izquierdo, expanda **Configuración**.
2. Haga clic en **Configuración de la organización**.
3. En la lista, haga clic en **Grupos de Microsoft 365**.
4. Asegúrese de que las casillas **Permitir que los propietarios del grupo agreguen personas de fuera de la organización a Grupos de Microsoft 365 como invitados** y **Permitir que los miembros del grupo invitados accedan al contenido del grupo** están activadas.
5. Si ha realizado cambios, haga clic en **Guardar cambios**.

## <a name="sharepoint-organization-level-sharing-settings"></a>Configuración de uso compartido de nivel de organización de SharePoint

Para que los invitados tengan acceso a sitios de SharePoint, la configuración de uso compartido de nivel de organización de SharePoint debe permitir el uso compartido con invitados.

La configuración de nivel de organización determina la configuración que estará disponible para sitios individuales. La configuración del sitio no puede ser más permisiva que la configuración de nivel de organización.

Si desea permitir el uso compartido de archivos y carpetas no autenticados, elija **Cualquiera**. Si desea asegurarse de que todas las personas fuera de su organización tienen que autenticarse, elija **Invitados nuevos y existentes**. Elija la configuración más permisiva que cualquier sitio de su organización necesite.

![Captura de pantalla de la configuración de uso compartido en el nivel de organización de SharePoint.](../media/sharepoint-organization-external-sharing-controls.png)


Para establecer la configuración de uso compartido de nivel de organización de SharePoint

1. En el Centro de administración de Microsoft 365, en el panel de navegación izquierdo, en **Administración centros**, seleccione **SharePoint**.
2. En el Centro de administración de SharePoint, en el panel de navegación izquierdo, en **Directivas**, seleccione <a href="https://go.microsoft.com/fwlink/?linkid=2185222" target="_blank">**Compartir**</a>.
3. Asegúrese de que el uso compartido externo de SharePoint está establecido en **Cualquier usuario** o **Invitados nuevos y existentes**.
4. Si ha realizado cambios, seleccione **Guardar**.

## <a name="create-a-site"></a>Crear un sitio

El siguiente paso es crear el sitio que tiene previsto usar para colaborar con invitados.

Para crear un sitio
1. En el Centro de administración de SharePoint en **Sitios**, seleccione <a href="https://go.microsoft.com/fwlink/?linkid=2185220" target="_blank">**Sitios activos**</a>.
2. Seleccione **Crear**.
3. Seleccione **Sitio de equipo**.
4. Escriba un nombre de sitio y escriba un nombre para el propietario del grupo (propietario del sitio).
5. En **Configuración avanzada**, elija si desea que este sitio sea público o privado.
6. Seleccione **Siguiente**.
7. Seleccione **Finalizar**.

Invitaremos a los usuarios más tarde. A continuación, es importante comprobar la configuración de uso compartido de nivel de sitio para este sitio.

## <a name="sharepoint-site-level-sharing-settings"></a>Configuración de uso compartido de nivel de sitio de SharePoint

Compruebe la configuración de uso compartido de nivel de sitio para asegurarse de que permiten el tipo de acceso que desea para este sitio. Por ejemplo, si establece la configuración de nivel de organización en **Cualquiera**, pero quiere que todos los invitados se autentiquen para este sitio, asegúrese de que la configuración de uso compartido de nivel de sitio esté establecida en **Invitados nuevos y existentes**.

Tenga en cuenta que el sitio no se puede compartir con personas no autenticadas (**configuración cualquiera** ), pero pueden ser archivos y carpetas individuales.

También puede usar [etiquetas de confidencialidad para controlar la configuración de uso compartido externo para sitios de SharePoint](../compliance/sensitivity-labels-teams-groups-sites.md).

![Captura de pantalla de la configuración de uso compartido externo del sitio de SharePoint.](../media/sharepoint-site-external-sharing-settings.png)

Para establecer la configuración de uso compartido de nivel de sitio
1. En el Centro de administración de SharePoint, en el panel de navegación izquierdo, expanda **Sitios** y haga clic en <a href="https://go.microsoft.com/fwlink/?linkid=2185220" target="_blank">**Sitios activos**</a>.
2. Seleccione el sitio que desea compartir.
3. Seleccione ...y seleccione **Compartir**.
4. Asegúrese de que el uso compartido está establecido en **Cualquiera** o en **Invitados nuevos y existentes**.
5. Si ha realizado cambios, seleccione **Guardar**.

## <a name="invite-users"></a>Invitar a usuarios

La configuración de uso compartido de invitados ya está configurada, por lo que puede empezar a agregar usuarios e invitados internos a su sitio. El acceso al sitio se controla a través del grupo de Microsoft 365 asociado, por lo que agregaremos usuarios allí.

Para invitar a usuarios internos a un grupo

1. Vaya al sitio donde desea agregar usuarios.
2. Seleccione **el vínculo Miembros** en la esquina superior derecha, que indica el recuento de miembros.
3. Seleccione **Agregar miembros**.
4. Escriba los nombres o direcciones de correo electrónico de los usuarios que desea invitar al sitio y, a continuación, seleccione **Guardar**.

Los invitados no se pueden agregar al grupo de Microsoft 365 desde el sitio. Para obtener información sobre cómo agregar invitados a un grupo, consulte [Incorporación de invitados a Grupos de Microsoft 365](https://support.microsoft.com/office/bfc7a840-868f-4fd6-a390-f347bf51aff6).

## <a name="see-also"></a>Vea también

[Prácticas recomendadas para compartir archivos y carpetas con usuarios no autenticados](best-practices-anonymous-sharing.md)

[Reducir la exposición accidental de archivos al compartirlos con invitados](share-limit-accidental-exposure.md)

[Crear un entorno seguro de uso compartido para invitados](create-secure-guest-sharing-environment.md)

[Crear una extranet B2B con invitados administrados](b2b-extranet.md)

[Integración de SharePoint y OneDrive con Azure AD B2B](/sharepoint/sharepoint-azureb2b-integration-preview)
