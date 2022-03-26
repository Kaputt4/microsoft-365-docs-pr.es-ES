---
title: Colaborar con personas ajenas a la organización
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-securecollab
- m365solution-scenario
- m365initiative-externalcollab
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.localizationpriority: medium
f1.keywords: NOCSH
recommendations: false
description: Obtén información sobre cómo configurar Microsoft 365 aplicaciones como Teams, OneDrive y SharePoint colaboración con personas de fuera de la organización.
ms.openlocfilehash: 65511cbafdc1f5a666c11e1bef7fefd6e6852ee3
ms.sourcegitcommit: 46456ca009c9d50622e57e24269be74986184654
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/22/2022
ms.locfileid: "63712782"
---
# <a name="collaborating-with-people-outside-your-organization"></a>Colaborar con personas ajenas a la organización

Las capacidades de uso compartido externo de Microsoft 365 proporcionan una oportunidad para que los usuarios de la organización colaboren con socios, proveedores, clientes y otros usuarios que no tienen una cuenta en el directorio. Puede compartir equipos, canales o sitios completos con personas ajenas a su organización o simplemente archivos individuales.

La colaboración con personas fuera de la organización consta de estos componentes principales:

- **Habilitar el** uso compartido: configure los controles de uso compartido en Azure Active Directory, Teams, grupos de Microsoft 365 y SharePoint para permitir el nivel de uso compartido que desea para su organización.
- **Configurar relaciones organizativas: si usa canales compartidos**, debe configurar las opciones de acceso entre inquilinos en Azure Active Directory para permitir el acceso directo a la conexión B2B para cada organización con la que desee colaborar. (Estas organizaciones también deben configurar las relaciones organizativas con el inquilino).
- Habilitar la seguridad **adicional: aunque** las características básicas de uso compartido se pueden configurar para requerir que las personas de fuera de la organización se autentiquen, Microsoft 365 proporciona muchas características de seguridad y cumplimiento adicionales que le ayudarán a proteger los datos y mantener las directivas de gobierno mientras se comparten externamente.

Lea [Configurar la colaboración segura con Microsoft 365 y Microsoft Teams](/microsoft-365/solutions/setup-secure-collaboration-with-teams) información sobre cómo el uso compartido externo se vincula con la guía general Microsoft 365 colaboración.

## <a name="enable-sharing"></a>Habilitar el uso compartido

De forma predeterminada, el uso compartido con personas de fuera de la organización mediante acceso de invitado o acceso anónimo está habilitado, pero los canales compartidos deben habilitarse configurando relaciones organizativas en Azure AD. La mayoría de los escenarios de uso compartido de invitados funcionan sin configuración adicional. Para confirmar la configuración de un escenario que está usando o habilitar uno nuevo, elija entre las siguientes opciones:

- [Colaborar en](collaborate-on-documents.md) documentos: aprenda a configurar Microsoft 365 para permitir el uso compartido y la colaboración con personas de fuera de la organización (tanto invitados como usuarios no autenticados) en archivos y carpetas.
- [Colaborar en un sitio](collaborate-in-site.md): obtenga información sobre cómo configurar Microsoft 365 para habilitar el uso compartido SharePoint sitios con invitados.
- [Colaborar en equipo](collaborate-as-team.md): obtenga información sobre cómo configurar Microsoft 365 para habilitar la colaboración de invitados en Teams.
- [Colaborar con participantes externos en un canal para](/microsoft-365/solutions/collaborate-teams-direct-connect) colaborar con personas fuera de la organización en un canal compartido.

Para obtener una visión completa de la configuración de uso compartido de invitados disponible en Microsoft 365, consulte Microsoft 365 referencia de configuración [de uso compartido de invitados](microsoft-365-guest-settings.md).

## <a name="enable-additional-security"></a>Habilitar seguridad adicional

Una vez que hayas habilitado el escenario que quieras usar para compartir con personas de fuera de la organización, considera medidas de seguridad adicionales para ayudar a proteger el contenido contra el uso compartido accidental o intencionado inadecuado.

- [Procedimientos recomendados para compartir archivos y](best-practices-anonymous-sharing.md) carpetas con usuarios no autenticados: obtenga información sobre los procedimientos recomendados para compartir con usuarios no autenticados.
- [Limitar la exposición accidental](share-limit-accidental-exposure.md) : aprenda a reducir las posibilidades de compartir accidentalmente contenido confidencial con personas de fuera de la organización.
- [Crear](create-secure-guest-sharing-environment.md) un entorno de uso compartido de invitados seguro: obtenga información sobre las herramientas que se proporcionan en Microsoft 365 para garantizar que el uso compartido con personas ajenas a su organización se realiza de forma segura y segura y cumple los requisitos de gobierno.

## <a name="collaborate-with-partner-companies"></a>Colaborar con empresas asociadas

Cuando trabaje en un proyecto grande que implique invitados de otra organización, considere la posibilidad de compartir canales. Dado que los canales compartidos no usan cuentas de invitado, los usuarios de la otra organización pueden acceder al canal compartido directamente sin tener que iniciar sesión en la organización por separado.

Si tiene una relación de proveedor continua en la que los invitados suelen cambiar, puede usar la administración de derechos en Azure Active Directory para simplificar la administración de invitados y permitir que la compañía asociada comparta esa responsabilidad. Consulte [Crear una extranet B2B con invitados administrados para](b2b-extranet.md) obtener más información.

## <a name="limit-sharing"></a>Limitar el uso compartido

Si algunas de las características de uso compartido de Microsoft 365 conflicto con las directivas de gobierno, vea [Limitar el](microsoft-365-limit-sharing.md) uso compartido en Microsoft 365 para obtener información sobre las opciones para limitar el uso compartido.

## <a name="related-topics"></a>Temas relacionados

[Introducción a la colaboración de archivos en Microsoft 365](/sharepoint/intro-to-file-collaboration)

[Planear la colaboración de archivos SharePoint con Microsoft 365](/sharepoint/deploy-file-collaboration)
