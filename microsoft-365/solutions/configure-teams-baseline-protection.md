---
title: Configure equipos con la protección de base de referencia
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- m365solution-3tiersprotection
- m365solution-securecollab
ms.custom:
- Ent_Solutions
description: Obtenga información acerca de cómo implementar equipos con un nivel de protección de base de referencia.
ms.openlocfilehash: cd5a88069b9947bd4dcb01f6ca76620bb8ed9a52
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2021
ms.locfileid: "51200298"
---
# <a name="configure-teams-with-baseline-protection"></a>Configure equipos con la protección de base de referencia

En este artículo, veremos cómo implementar equipos con un nivel de protección de base de referencia. Este nivel permite a los usuarios disponer de una amplia variedad de opciones de colaboración al mismo tiempo que mejora la gestión de permisos y proporciona protección básica contra el uso compartido excesivo. Las protecciones recomendadas para este nivel incluyen directivas de identidad y acceso a dispositivos y protección contra malware. Asimismo, puede aplicar directivas de acceso condicional y protección de pérdida de datos según sea necesario.

## <a name="initial-protections"></a>Protecciones iniciales

Como primer paso, le recomendamos que configure directivas básicas de identidad y acceso de dispositivo. Para más información, vea [Recomendaciones de directivas para proteger los chats, grupos y archivos de Teams](../security/office-365-security/teams-access-policies.md).

También recomendamos activar las características básicas de Microsoft Defender para Office 365 para protegerse contra malware en documentos, archivos adjuntos y vínculos. Se recomienda activar todas las opciones de la tabla siguiente.

|Opción|Información|
|:------|:-----------|
|Archivos adjuntos seguros para SPO, OneDrive y Teams|[Archivos adjuntos seguros](../security/office-365-security/safe-attachments.md)<br>[Microsoft Defender para Office 365 para SharePoint, OneDrive y Microsoft Teams](../security/office-365-security/mdo-for-spo-odb-and-teams.md).|
|Documentos seguros|[Documentos seguros en Microsoft Defender para Office 365](../security/office-365-security/safe-docs.md)|
|Vínculos seguros en Teams|[Vínculos seguros de Office 365 en Teams](../security/office-365-security/safe-links.md#safe-links-settings-for-microsoft-teamssafe-links-settings-for-microsoft-teams)<br>[Vínculos seguros](../security/office-365-security/safe-links.md)|

## <a name="teams-guest-sharing"></a>Uso compartido de invitados en Teams

En cada uno de los niveles tenemos la opción de compartir con personas de fuera de la organización. En el caso de los niveles de confidencialidad y alta confidencialidad, tendremos la opción de desactivar el uso compartido de invitados en el nivel de equipo usando etiquetas de confidencialidad. Pero la configuración de uso compartido de invitados en el nivel de la organización tiene que estar activada para que el uso compartido de invitados funcione en Teams.

![Captura de pantalla de la opción de acceso de invitados de Teams](../media/teams-guest-access-toggle-on.png)

Para establecer la configuración de acceso de invitados de Teams

1. Inicie sesión en el Centro de administración de Microsoft 365 en [https://admin.microsoft.com](https://admin.microsoft.com).
2. En el panel de navegación izquierdo, haga clic en **Mostrar todos**.
3. En **Centros de administración**, haga clic en **Teams**.
4. En el centro de administración de Teams, en el panel de navegación de la izquierda, expanda **Configuración de toda la organización** y haga clic en **Acceso de invitado**.
5. Asegúrese de que **Permitir el acceso de invitados en Teams** se haya establecido en **Activado**.
6. Realice los cambios que quiera en la configuración de invitado adicional y luego haga clic en **Guardar**.

> [!NOTE]
> La configuración de invitado de Teams puede tardar hasta veinticuatro horas en activarse después de activarla.

El uso compartido de invitados está activado de forma predeterminada para los grupos de Office 365 y SharePoint, pero si ha cambiado anteriormente alguna de las configuraciones de uso compartido de invitado en su organización, le recomendamos que revise [Colaborar con invitados en un equipo](./collaborate-as-team.md) para asegurarse de que el uso compartido de invitados estará disponible en Teams.

## <a name="site-and-file-sharing"></a>Uso compartido de sitios y archivos

Para reducir el riesgo de compartir accidentalmente archivos o carpetas con personas de fuera de su organización, le recomendamos que cambie el vínculo de uso compartido predeterminado para SharePoint a *Solo personas de la organización*. (Si los usuarios necesitan compartir externamente y ha habilitado el uso compartido de invitados, aún podrán cambiar el tipo de vínculo al compartir).

Para cambiar el vínculo para compartir predeterminado
1. Abra el [Centro de administración de SharePoint](https://admin.microsoft.com/sharepoint).
2. En **Directivas**, haga clic en **Uso compartido**.
3. En **Vínculos de archivos y carpetas**, seleccione **Solo personas de la organización**.
4. Haga clic en **Guardar**.

Para disfrutar de la mejor experiencia de uso compartido de invitados, también le recomendamos que habilite la [Integración de SharePoint y OneDrive con B2B de Azure AD](/sharepoint/sharepoint-azureb2b-integration-preview).

## <a name="create-a-team"></a>Crear un equipo

La configuración adicional para el nivel de protección de base de referencia se lleva a cabo en el sitio de SharePoint asociado a un equipo. [Cree un equipo público o privado](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b) antes de continuar con la siguiente sección.

## <a name="site-sharing-settings"></a>Configuración de uso compartido del sitio 

De forma predeterminada, los miembros de un sitio de SharePoint pueden invitar a otros usuarios al sitio. Cuando un sitio forma parte de un equipo, los miembros del equipo se incluyen como miembros del sitio. Sin embargo, los usuarios agregados directamente al sitio no tienen acceso al resto del equipo. Por este motivo, le recomendamos que administre los permisos exclusivamente mediante el equipo.

Para ayudarle con la administración de permisos, le recomendamos que configure el sitio asociado para que solo los propietarios del sitio puedan compartirlo. Esto simplifica la administración de permisos y evita el acceso por parte de usuarios sin el conocimiento del propietario del equipo. Haga esto para cada equipo que necesita protección de base de referencia.

Para actualizar la configuración de uso compartido del sitio
1. En la barra de herramientas del equipo, haga clic en **Archivos**.
2. Haga clic en **Abrir en SharePoint**.
3. En la barra de herramientas de SharePoint, haga clic en el icono de configuración y luego en **Permisos del sitio**.
4. En el panel **Permisos del sitio**, en **Uso compartido del sitio**, haga clic en **Cambiar cómo pueden compartir los miembros**.
5. En **Permisos de uso compartido**, elija **Los propietarios y miembros del sitio, y las personas con permisos de edición pueden compartir archivos y carpetas, pero solo los propietarios de sitios pueden compartir el sitio** y haga clic en **Guardar**.

## <a name="additional-protections"></a>Protecciones adicionales

Microsoft 365 ofrece otros métodos para proteger el contenido. Considere si las siguientes opciones ayudarían a mejorar la seguridad de su organización.

- Hacer que los invitados acepten las [condiciones de uso](/azure/active-directory/conditional-access/terms-of-use).
- Configurar una [directiva de tiempo de espera de sesión](/azure/active-directory/conditional-access/howto-conditional-access-session-lifetime) para invitados
- Crear [tipos de información confidencial](../compliance/sensitive-information-type-learn-about.md) y usar [protección de pérdida de datos](../compliance/data-loss-prevention-policies.md) para establecer directivas en relación con el acceso a información confidencial.

## <a name="see-also"></a>Consulte también

[Administración de directivas de reunión en Teams](/microsoftteams/meeting-policies-in-teams)

[Introducción a la administración de riesgos internos](../compliance/insider-risk-management-configure.md)