---
title: Más información acerca de las barreras de información
description: Obtenga información sobre las barreras de información en Microsoft Purview.
keywords: Microsoft 365, Microsoft Purview, cumplimiento, barreras de información
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
ms.localizationpriority: ''
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 72a53580222b315f86fd397e391b026937b8035b
ms.sourcegitcommit: 5c64002236561000c5bd63c71423e8099e803c2d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/09/2022
ms.locfileid: "65287186"
---
# <a name="learn-about-information-barriers"></a>Más información acerca de las barreras de información

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

Los servicios en la nube de Microsoft incluyen funcionalidades eficaces de comunicación y colaboración. Pero supongamos que quiere restringir la comunicación y la colaboración entre dos grupos para evitar que se produzca un conflicto de interés en la organización. O bien, quizás quiera restringir la comunicación y la colaboración entre ciertas personas dentro de su organización con el fin de proteger la información interna. Microsoft 365 permite la comunicación y la colaboración entre grupos y organizaciones, ¿existe una manera de restringir la comunicación y la colaboración entre grupos específicos de usuarios cuando sea necesario? Con Las barreras de información de Microsoft Purview (IB), ¡puede!

Microsoft Teams, SharePoint Online y OneDrive para la Empresa admiten barreras de información. Suponiendo que la [suscripción](#required-licenses-and-permissions) incluya barreras de información, un administrador de cumplimiento o un administrador de barreras de información puede definir directivas para permitir o impedir las comunicaciones entre grupos de usuarios en Microsoft Teams. Las directivas de barrera de información se pueden usar para situaciones como las siguientes:

- El usuario del grupo de operadores de día no debe comunicarse ni compartir archivos con el equipo de marketing.
- El personal financiero que trabaja con información confidencial de la empresa no debe comunicarse ni compartir archivos con determinados grupos de su organización.
- Un equipo interno con material secreto comercial no debe llamar ni chatear en línea con personas de determinados grupos dentro de su organización.
- Un equipo de investigación solo debe llamar o chatear en línea con un equipo de desarrollo de productos.
- Un sitio para el grupo de operadores de día no debe ser compartido ni accedido por nadie fuera del grupo de operadores de día

> [!IMPORTANT]
> Las barreras de información ***solo admiten** _ restricciones bidireccionales. Las restricciones de una manera, como el marketing, pueden comunicarse y colaborar con los operadores de día, pero los operadores de día no pueden comunicarse y colaborar con marketing _*_no se admiten_**.

Para todos estos escenarios de ejemplo (y más), se pueden definir directivas de barrera de información para impedir o permitir las comunicaciones y la colaboración en Microsoft Teams, SharePoint Online y OneDrive. Estas directivas pueden impedir que las personas llamen o chateen con las que no deberían, o permitir que las personas se comuniquen solo con grupos específicos de Microsoft Teams. Con las directivas de barrera de información en vigor, cada vez que los usuarios que están cubiertos por esas directivas intentan comunicarse y colaborar con otros usuarios en Microsoft Teams, SharePoint comprobaciones en línea o OneDrive se realizan para impedir (o permitir) la comunicación y la colaboración (tal como se define en las directivas de barrera de información).

Para más información sobre la experiencia del usuario con barreras de información, consulte:

- [Barreras de información en Microsoft Teams](/MicrosoftTeams/information-barriers-in-teams)
- [Barreras de información en SharePoint Online](/sharepoint/information-barriers)
- [Barreras de información en OneDrive](/onedrive/information-barriers)

> [!IMPORTANT]
> Actualmente, las barreras de información no se aplican a las comunicaciones por correo electrónico. Además, las barreras de información son independientes de [los límites de cumplimiento](set-up-compliance-boundaries.md).<p> Antes de definir y aplicar directivas de barrera de información, asegúrese de que su organización no tiene [Exchange directivas de libreta de direcciones](/exchange/address-books/address-book-policies/address-book-policies) en vigor. (Las barreras de información se basan en las directivas de libreta de direcciones).

## <a name="what-happens-with-information-barriers"></a>¿Qué ocurre con las barreras de información?

Cuando se aplican directivas de barrera de información, las personas que no deben comunicarse ni compartir archivos con otros usuarios específicos no podrán encontrar, seleccionar, chatear o llamar a esos usuarios. Con las barreras de información, se realizan comprobaciones para evitar la comunicación y la colaboración no autorizadas.

Las barreras de información se aplican a Microsoft Teams (chats y canales), SharePoint En línea y OneDrive. En Microsoft Teams, las directivas de barrera de información determinan y evitan los siguientes tipos de comunicaciones no autorizadas:

- Buscar un usuario
- Agregar un miembro a un equipo
- Iniciar una sesión de chat con alguien
- Iniciar un chat de grupo
- Invitar a alguien a unirse a una reunión
- Compartir una pantalla
- Realizar una llamada
- Uso compartido de un archivo con otro usuario
- Acceso al archivo mediante el vínculo de uso compartido

Si las personas implicadas se incluyen en una directiva de barrera de información para evitar la actividad, no podrán continuar. Además, potencialmente, todos los usuarios incluidos en una directiva de barrera de información pueden tener bloqueada la comunicación con otros usuarios en Microsoft Teams. Cuando las personas afectadas por las directivas de barrera de información forman parte del mismo equipo o chat grupal, es posible que se les quite de esas sesiones de chat y no se pueda continuar con la comunicación con el grupo.

Para más información sobre la experiencia del usuario con las barreras de información, consulte [Barreras de información en Microsoft Teams](/MicrosoftTeams/information-barriers-in-teams).

En SharePoint Online y OneDrive, las directivas de barrera de información determinan e impiden los siguientes tipos de colaboraciones no autorizadas:

- Adición de un miembro a un sitio
- Acceso al sitio o al contenido por parte de un usuario
- Uso compartido de sitio o contenido con otro usuario
- Buscar en un sitio

Para más información sobre la experiencia del usuario con barreras de información, consulte [Barreras de información en SharePoint Online](/sharepoint/information-barriers).

## <a name="required-licenses-and-permissions"></a>Permisos y licencias necesarios

Antes de empezar a trabajar con IB, debe confirmar la [suscripción Microsoft 365](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) y los complementos. Para acceder y usar IB, su organización debe tener una de las siguientes suscripciones o complementos:

- suscripción Microsoft 365 E5/A5 (versión de pago o de prueba)
- suscripción Office 365 E5/A5/A3/A1 (versión de pago o de prueba)
- Cumplimiento avanzado de Office 365 complemento (ya no está disponible para nuevas suscripciones)
- suscripción Microsoft 365 E3/A3/A1 + el complemento de cumplimiento de Microsoft 365 E5/A5
- suscripción Microsoft 365 E3/A3/A1 + el complemento Microsoft 365 E5/A5 Insider Risk Management

Para obtener más información, consulte [Microsoft 365 guía de licencias para el cumplimiento de & de seguridad](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection).

Para [definir o editar directivas de barrera de información](information-barriers-policies.md), se le debe asignar uno de los siguientes roles:

- Administrador global de Microsoft 365
- Administrador global de Office 365
- Administrador de cumplimiento
- Administración de cumplimiento IB

(Para obtener más información sobre los roles y permisos, consulte [Permisos en el Centro de cumplimiento de Office 365 Security &](../security/office-365-security/permissions-in-the-security-and-compliance-center.md)).

Debe estar familiarizado con los cmdlets de PowerShell para definir, validar o editar directivas de barrera de información. Aunque proporcionamos varios ejemplos de cmdlets de PowerShell en el [artículo de procedimientos](information-barriers-policies.md), deberá conocer otros detalles, como los parámetros, para su organización.

## <a name="next-steps"></a>Siguientes pasos

- [Más información sobre las barreras de información en Microsoft Teams](/MicrosoftTeams/information-barriers-in-teams)
- [Más información sobre las barreras de información en SharePoint Online](/sharepoint/information-barriers)
- [Más información sobre las barreras de información en OneDrive](/onedrive/information-barriers)
- [Consulte los atributos que se pueden usar para las directivas de barrera de información.](information-barriers-attributes.md)
- [Definir directivas de barreras de información](information-barriers-policies.md)
- [Editar o quitar directivas de barrera de información](information-barriers-edit-segments-policies.md)
