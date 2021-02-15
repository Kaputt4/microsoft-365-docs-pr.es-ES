---
title: Más información sobre las barreras de información en Microsoft 365
description: Use barreras de información para garantizar el cumplimiento de las comunicaciones con Microsoft Teams en su organización.
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
localization_priority: None
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1ef09fbf7a517950ae182472e4b4d5ef896d65e5
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126547"
---
# <a name="learn-about-information-barriers-in-microsoft-365"></a>Más información sobre las barreras de información en Microsoft 365

Los servicios en la nube de Microsoft incluyen potentes capacidades de comunicación y colaboración. Pero suponga que desea restringir la comunicación y la colaboración entre dos grupos para evitar que se produzca un conflicto de interés en su organización. O quizás quiera restringir la comunicación y la colaboración entre determinadas personas de la organización para proteger la información interna. Microsoft 365 permite la comunicación y la colaboración entre grupos y organizaciones, por lo que hay una forma de restringir la comunicación y la colaboración entre grupos de usuarios específicos cuando sea necesario? Con las barreras de información, puede hacerlo.

Microsoft Teams, SharePoint Online y OneDrive para la Empresa admiten barreras de información. Suponiendo que su [suscripción incluye](#required-licenses-and-permissions) barreras de información, un administrador de cumplimiento o un administrador de barreras de información pueden definir directivas para permitir o impedir comunicaciones entre grupos de usuarios en Microsoft Teams. Las directivas de barreras de información se pueden usar para situaciones como estas:

- El grupo de usuarios del día no debe comunicarse ni compartir archivos con el equipo de marketing
- El personal de finanzas que trabaja en información confidencial de la empresa no debe comunicar ni compartir archivos con determinados grupos dentro de su organización
- Un equipo interno con material secreto comercial no debe llamar ni chatear en línea con personas de determinados grupos dentro de su organización
- Un equipo de investigación solo debe llamar o chatear en línea con un equipo de desarrollo de productos
- No se debe compartir ni tener acceso a un sitio para un grupo de vendedores de día

> [!IMPORTANT]
> Las barreras de información ***solo admiten** restricciones de dos vías. Las restricciones de un solo sentido, como el marketing, pueden comunicarse y colaborar con los comerciantes de día, pero los comerciantes de día no pueden comunicarse y colaborar con el marketing _* no _se admite_**.

Para todos estos escenarios de ejemplo (y más), se pueden definir directivas de barreras de información para impedir o permitir las comunicaciones y la colaboración en Microsoft Teams, SharePoint Online y OneDrive. Estas directivas pueden impedir que los usuarios llamen o chatee con aquellos que no deberían, o permitir que los usuarios se comuniquen solo con grupos específicos de Microsoft Teams. Con las directivas de barreras de información en vigor, siempre que los usuarios cubiertos por dichas directivas intenten comunicarse y colaborar con otras personas en Microsoft Teams, sharePoint Online o OneDrive se realizan comprobaciones para impedir (o permitir) la comunicación y la colaboración (según se define en las directivas de barreras de información).

Para obtener más información sobre la experiencia del usuario con barreras de información, vea:

- [Barreras de información en Microsoft Teams](/MicrosoftTeams/information-barriers-in-teams)
- [Barreras de información en SharePoint Online](/sharepoint/information-barriers)
- [Barreras de información en OneDrive](/onedrive/information-barriers)

> [!IMPORTANT]
> Actualmente, las barreras de información no se aplican a las comunicaciones por correo electrónico. Además, las barreras de información son independientes de los [límites de cumplimiento.](set-up-compliance-boundaries.md)<p> Antes de definir y aplicar directivas de barreras de información, asegúrese de que su organización no tenga directivas de libreta de direcciones de [Exchange](/exchange/address-books/address-book-policies/address-book-policies) en vigor. (Las barreras de información se basan en las directivas de la libreta de direcciones).

## <a name="what-happens-with-information-barriers"></a>Qué sucede con las barreras de información

Cuando haya directivas de barreras de información, las personas que no deberán comunicarse o compartir archivos con otros usuarios específicos no podrán encontrar, seleccionar, chatear ni llamar a esos usuarios. Con las barreras de información, se realizan comprobaciones para evitar la comunicación y colaboración no autorizadas. 

Las barreras de información se aplican a Microsoft Teams (chats y canales), SharePoint Online y OneDrive. En Microsoft Teams, las directivas de barreras de información determinan y evitan los siguientes tipos de comunicaciones no autorizadas:

- Buscar un usuario
- Agregar un miembro a un equipo
- Iniciar una sesión de chat con alguien
- Inicio de un chat en grupo
- Invitar a alguien a unirse a una reunión
- Compartir una pantalla
- Realizar una llamada
- Compartir un archivo con otro usuario
- Acceso al archivo a través del vínculo para compartir

Si los participantes están incluidos en una directiva de barreras de información para evitar la actividad, no podrán continuar. Además, es posible que se bloquee a todos los incluidos en una directiva de barreras de información para que no se comuniquen con otros usuarios de Microsoft Teams. Cuando las personas afectadas por las directivas de barreras de información forman parte del mismo equipo o chat en grupo, es posible que se quiten de esas sesiones de chat y que no se permita una mayor comunicación con el grupo.

Para obtener más información sobre la experiencia del usuario con barreras de información, vea [barreras de información en Microsoft Teams.](/MicrosoftTeams/information-barriers-in-teams)

En SharePoint Online y OneDrive, las directivas de barreras de información determinan y evitan los siguientes tipos de colaboraciones no autorizadas:

- Agregar un miembro a un sitio
- Obtener acceso a un sitio o contenido por un usuario
- Compartir contenido o sitio con otro usuario
- Buscar en un sitio

Para obtener más información sobre la experiencia del usuario con barreras de información, vea [barreras de información en SharePoint Online](/sharepoint/information-barriers)

## <a name="required-licenses-and-permissions"></a>Permisos y licencias necesarios

Las barreras de información se están implementando ahora y se incluyen en las suscripciones, como:

- Microsoft 365 E5/A5
- Office 365 E5/A5
- Cumplimiento avanzado de Office 365
- Cumplimiento E5/A5 de Microsoft 365
- Administración de riesgos de Microsoft 365 Insider

Para obtener más información, vea la guía [de licencias de Microsoft 365](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)para la seguridad y & cumplimiento.

Para [definir o editar directivas de barreras](information-barriers-policies.md)de información, debe tener asignado uno de los siguientes roles:

- Administrador global de Microsoft 365
- Administrador global de Office 365
- Administrador de cumplimiento
- Administración de cumplimiento de LAC

(Para obtener más información sobre roles y permisos, vea Permisos en el Centro de seguridad y & cumplimiento de [Office 365).](../security/office-365-security/permissions-in-the-security-and-compliance-center.md)

Debe estar familiarizado con los cmdlets de PowerShell para definir, validar o editar directivas de barreras de información. Aunque proporcionamos varios ejemplos de cmdlets de PowerShell en el artículo de [ayuda,](information-barriers-policies.md)necesitará conocer otros detalles, como parámetros, para su organización.

## <a name="next-steps"></a>Pasos siguientes

- [Más información sobre las barreras de información en Microsoft Teams](/MicrosoftTeams/information-barriers-in-teams)
- [Obtenga más información sobre las barreras de información en SharePoint Online](/sharepoint/information-barriers)
- [Más información sobre las barreras de información en OneDrive](/onedrive/information-barriers)
- [Ver los atributos que se pueden usar para las directivas de barreras de información](information-barriers-attributes.md)
- [Definir directivas para barreras de información](information-barriers-policies.md)
- [Editar (o quitar) directivas de barreras de información](information-barriers-edit-segments-policies.md)