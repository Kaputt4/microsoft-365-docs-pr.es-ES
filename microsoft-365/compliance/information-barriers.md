---
title: Información sobre las barreras de información en Microsoft 365
description: Use barreras de información para garantizar el cumplimiento de las comunicaciones con Microsoft Teams dentro de su organización.
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
ms.openlocfilehash: 4ef3fce82a10792c8289a4a3c4e3cb5639a4d178
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051882"
---
# <a name="learn-about-information-barriers-in-microsoft-365"></a>Información sobre las barreras de información en Microsoft 365

Los servicios en la nube de Microsoft incluyen funcionalidades eficaces de comunicación y colaboración. Pero supongamos que desea restringir la comunicación y la colaboración entre dos grupos para evitar que se produzca un conflicto de interés en su organización. O quizás quiera restringir la comunicación y la colaboración entre determinadas personas dentro de su organización para proteger la información interna. Microsoft 365 permite la comunicación y la colaboración entre grupos y organizaciones, por lo que hay una forma de restringir la comunicación y la colaboración entre grupos específicos de usuarios cuando sea necesario. Con las barreras de información, puede hacerlo.

Microsoft Teams, SharePoint Online y OneDrive para la Empresa admiten barreras de información. Suponiendo que la [suscripción incluye](#required-licenses-and-permissions) barreras de información, un administrador de cumplimiento o un administrador de barreras de información pueden definir directivas para permitir o impedir las comunicaciones entre grupos de usuarios en Microsoft Teams. Las directivas de barrera de información se pueden usar para situaciones como estas:

- El usuario del grupo de comerciantes del día no debe comunicarse ni compartir archivos con el equipo de marketing
- El personal de finanzas que trabaja en información confidencial de la empresa no debe comunicarse ni compartir archivos con determinados grupos dentro de su organización
- Un equipo interno con material secreto comercial no debe llamar ni chatear en línea con personas de determinados grupos dentro de su organización
- Un equipo de investigación solo debe llamar o chatear en línea con un equipo de desarrollo de productos
- Un sitio para el grupo de comerciantes de día no debe ser compartido o accedido por nadie fuera del grupo de comerciantes del día

> [!IMPORTANT]
> Las barreras de información ***solo admiten** restricciones de dos vías. Las restricciones de un solo modo, como el marketing, pueden comunicarse y colaborar con los comerciantes de día, pero los comerciantes de día no pueden comunicarse y colaborar con el marketing _* no _se admite_**.

Para todos estos escenarios de ejemplo (y más), las directivas de barrera de información se pueden definir para impedir o permitir comunicaciones y colaboración en Microsoft Teams, SharePoint Online y OneDrive. Estas directivas pueden impedir que las personas llamen o chatee con los que no deberían, o permitir que las personas se comuniquen solo con grupos específicos de Microsoft Teams. Con las directivas de barrera de información en vigor, siempre que los usuarios que están cubiertos por dichas directivas intenten comunicarse y colaborar con otros usuarios en Microsoft Teams, las comprobaciones de SharePoint Online o OneDrive se realizan para impedir (o permitir) la comunicación y colaboración (tal como se define en las directivas de barrera de información).

Para obtener más información sobre la experiencia del usuario con las barreras de información, vea:

- [Barreras de información en Microsoft Teams](/MicrosoftTeams/information-barriers-in-teams)
- [Barreras de información en SharePoint Online](/sharepoint/information-barriers)
- [Barreras de información en OneDrive](/onedrive/information-barriers)

> [!IMPORTANT]
> Actualmente, las barreras de información no se aplican a las comunicaciones por correo electrónico. Además, las barreras de información son independientes de los [límites de cumplimiento](set-up-compliance-boundaries.md).<p> Antes de definir y aplicar directivas de barrera de información, asegúrese de que su organización no tenga directivas de libreta de [direcciones de Exchange](/exchange/address-books/address-book-policies/address-book-policies) en vigor. (Las barreras de información se basan en directivas de libreta de direcciones).

## <a name="what-happens-with-information-barriers"></a>Qué sucede con las barreras de información

Cuando haya directivas de barrera de información, las personas que no deben comunicarse o compartir archivos con otros usuarios específicos no podrán encontrar, seleccionar, chatear o llamar a esos usuarios. Con las barreras de información, se realizan comprobaciones para evitar la comunicación y colaboración no autorizadas. 

Las barreras de información se aplican a Microsoft Teams (chats y canales), SharePoint Online y OneDrive. En Microsoft Teams, las directivas de barrera de información determinan y evitan los siguientes tipos de comunicaciones no autorizadas:

- Buscar un usuario
- Agregar un miembro a un equipo
- Iniciar una sesión de chat con alguien
- Iniciar un chat de grupo
- Invitar a alguien a unirse a una reunión
- Compartir una pantalla
- Realizar una llamada
- Compartir un archivo con otro usuario
- Acceso al archivo a través del vínculo de uso compartido

Si las personas implicadas se incluyen en una directiva de barrera de información para impedir la actividad, no podrán continuar. Además, potencialmente, todos los usuarios incluidos en una directiva de barrera de información pueden bloquearse para que no se comuniquen con otros usuarios de Microsoft Teams. Cuando las personas afectadas por directivas de barrera de información forman parte del mismo chat de grupo o equipo, es posible que se quiten de esas sesiones de chat y que no se permita una comunicación adicional con el grupo.

Para obtener más información sobre la experiencia del usuario con las barreras de información, consulte [Information Barriers in Microsoft Teams](/MicrosoftTeams/information-barriers-in-teams).

En SharePoint Online y OneDrive, las directivas de barrera de información determinan y evitan los siguientes tipos de colaboraciones no autorizadas:

- Agregar un miembro a un sitio
- Acceso a un sitio o contenido por parte de un usuario
- Compartir sitio o contenido con otro usuario
- Buscar en un sitio

Para obtener más información sobre la experiencia del usuario con barreras de información, vea [Information barriers in SharePoint Online](/sharepoint/information-barriers)

## <a name="required-licenses-and-permissions"></a>Permisos y licencias necesarios

Las barreras de información se están implementando ahora y se incluyen en las suscripciones, como:

- Microsoft 365 E5/A5
- Office 365 E5/A5
- Cumplimiento avanzado de Office 365
- Cumplimiento de Microsoft 365 E5/A5
- Administración de riesgos de Microsoft 365 Insider

Para obtener más información, vea Guía de licencias de [Microsoft 365](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)para seguridad & cumplimiento .

Para [definir o editar directivas de barrera de información,](information-barriers-policies.md)se le debe asignar uno de los siguientes roles:

- Administrador global de Microsoft 365
- Administrador global de Office 365
- Administrador de cumplimiento
- Administración de cumplimiento de IB

(Para obtener más información sobre roles y permisos, vea Permisos en el Centro de seguridad y [& cumplimiento de Office 365.)](../security/defender-365-security/permissions-in-the-security-and-compliance-center.md)

Debe estar familiarizado con los cmdlets de PowerShell para definir, validar o editar directivas de barrera de información. Aunque proporcionamos varios ejemplos de cmdlets de PowerShell en el artículo sobre cómo [hacerlo,](information-barriers-policies.md)deberá conocer otros detalles, como parámetros, para su organización.

## <a name="next-steps"></a>Siguientes pasos

- [Más información sobre las barreras de información en Microsoft Teams](/MicrosoftTeams/information-barriers-in-teams)
- [Más información sobre las barreras de información en SharePoint Online](/sharepoint/information-barriers)
- [Más información sobre las barreras de información en OneDrive](/onedrive/information-barriers)
- [Vea los atributos que se pueden usar para las directivas de barrera de información](information-barriers-attributes.md)
- [Definir directivas para barreras de información](information-barriers-policies.md)
- [Editar (o quitar) directivas de barrera de información](information-barriers-edit-segments-policies.md)