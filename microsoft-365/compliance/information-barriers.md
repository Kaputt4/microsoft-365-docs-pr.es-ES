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
ms.openlocfilehash: 214a2614b6ca7381bbded39ff5f5143236f6c001
ms.sourcegitcommit: 570c3be37b6ab1d59a4988f7de9c9fb5ca38028f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2022
ms.locfileid: "65363126"
---
# <a name="learn-about-information-barriers"></a>Más información acerca de las barreras de información

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

Microsoft Purview Barreras de información (IB) es una solución de cumplimiento que permite restringir la comunicación bidireccional y la colaboración entre grupos y usuarios en Microsoft Teams, SharePoint Online y OneDrive para la Empresa. A menudo utilizado en sectores altamente regulados, el IB puede ayudar a evitar conflictos de interés y a proteger la información interna entre los usuarios y las áreas organizativas.

Cuando se aplican directivas de IB, los usuarios que no deben comunicarse o compartir archivos con otros usuarios específicos no podrán encontrar, seleccionar, chatear o llamar a esos usuarios. Las directivas de IB establecen automáticamente comprobaciones para detectar y evitar la comunicación y colaboración no autorizadas entre grupos y usuarios definidos. Las directivas de IB son independientes de [los límites de cumplimiento](/microsoft-365/compliance/set-up-compliance-boundaries) de las investigaciones de eDiscovery que controlan las ubicaciones de contenido de usuario que los administradores de eDiscovery pueden buscar.

Las directivas de IB pueden permitir o impedir la comunicación y la colaboración entre grupos y usuarios en los siguientes escenarios de ejemplo:

- Los usuarios del grupo *Day Trader* no deben comunicarse ni compartir archivos con el *equipo de marketing*
- El personal financiero que trabaja con información confidencial de la empresa no debe comunicarse ni compartir archivos con determinados grupos de su organización.
- Un equipo interno con material secreto comercial no debe llamar ni chatear en línea con personas de determinados grupos dentro de su organización.
- Un equipo de investigación solo debe llamar o chatear en línea con un equipo de desarrollo de productos.
- Un sitio SharePoint para el grupo *Day Trader* no debe ser compartido ni accedido por nadie fuera del grupo *Day Trader*

> [!IMPORTANT]
> Las barreras de información **solo admiten** restricciones bidireccionales de comunicación y colaboración. Por ejemplo, **no se admite** un escenario en el que Marketing pueda comunicarse y colaborar con Day Traders, pero Day Traders no puede comunicarse ni colaborar con Marketing.

## <a name="information-barriers-and-microsoft-teams"></a>Barreras de información y Microsoft Teams

En Microsoft Teams, las directivas de IB determinan e impiden los siguientes tipos de comunicación y colaboración no autorizadas:

- Buscar un usuario
- Agregar un miembro a un equipo
- Iniciar una sesión de chat con alguien
- Iniciar un chat de grupo
- Invitar a alguien a unirse a una reunión
- Compartir una pantalla
- Realizar una llamada
- Uso compartido de un archivo con otro usuario
- Acceso a un archivo mediante el uso compartido de un vínculo

Si los usuarios que realizan estas actividades en Microsoft Teams se incluyen en una directiva de IB para evitar la actividad, no podrán continuar. Además, se puede impedir que todos los usuarios incluidos en una directiva de IB se comuniquen con otros usuarios en Microsoft Teams. Cuando las personas afectadas por las directivas de IB forman parte del mismo equipo o chat de grupo, es posible que se eliminen de esas sesiones de chat y no se permita una comunicación adicional con el grupo.

Para obtener más información, consulte [barreras de información en Microsoft Teams](/MicrosoftTeams/information-barriers-in-teams).

## <a name="information-barriers-and-sharepoint-and-onedrive"></a>Barreras de información y SharePoint y OneDrive

En SharePoint Online y OneDrive, las directivas de IB detectan e impiden los siguientes tipos de colaboración no autorizada:

- Adición de un miembro a un sitio
- Acceso al sitio o al contenido por parte de un usuario
- Uso compartido de sitio o contenido con otro usuario
- Buscar en un sitio

Para obtener más información, consulte [Barreras de información en SharePoint](/sharepoint/information-barriers) y [Barreras de información en OneDrive](/onedrive/information-barriers).

## <a name="information-barriers-and-exchange-online"></a>Barreras de información y Exchange Online

Las directivas de IB no están disponibles para restringir la comunicación y la colaboración entre grupos y usuarios en los mensajes de correo electrónico. Las directivas de IB se basan en [Exchange Online directivas de libreta de direcciones (AAP).](/exchange/address-books/address-book-policies/address-book-policies) Los ABPs permiten a las organizaciones asignar virtualmente usuarios a grupos específicos con el fin de proporcionar vistas personalizadas de la libreta de direcciones global (GAL) de la organización. Cuando se crean directivas de IB, los ABPs para las directivas se crean automáticamente. A medida que se agregan directivas de IB en su organización, la estructura y el comportamiento de la GAL cambiarán para cumplir con las directivas de IB.

Antes de definir y aplicar directivas de IB, debe quitar todas las directivas de libreta de direcciones Exchange existentes de su organización. Las directivas de IB se basan en directivas de libreta de direcciones y las directivas ABP existentes no son compatibles con los AAP creados por IB. Para quitar las directivas de libreta de direcciones existentes, consulte [Quitar una directiva de libreta de direcciones en Exchange Online](/exchange/address-books/address-book-policies/remove-an-address-book-policy). Una vez habilitadas las directivas de IB y si tiene habilitada la libreta de direcciones jerárquica, todos los usuarios no incluidos en un segmento ib verán la [libreta de direcciones jerárquica](/exchange/address-books/hierarchical-address-books/hierarchical-address-books) en Exchange en línea.

Actualmente, solo se admiten las implementaciones Exchange Online para las directivas de IB. Si su organización necesita definir y controlar las comunicaciones por correo electrónico, considere la posibilidad de usar [Exchange reglas de flujo de correo](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).

## <a name="ready-to-get-started"></a>¿Está listo para empezar?

- [Introducción a las barreras de información](information-barriers-policies.md)
- [Administración de directivas de barrera de información](information-barriers-edit-segments-policies.md)
- [Consulte los atributos que se pueden usar para las directivas de barrera de información.](information-barriers-attributes.md)
