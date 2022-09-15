---
title: Colaborar con personas ajenas a la organización
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
ms.collection:
- highpri
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
description: Obtenga información sobre cómo configurar aplicaciones de Microsoft 365 como Teams, OneDrive y SharePoint para la colaboración con personas ajenas a su organización.
ms.openlocfilehash: 3151f6c00795a9cab6de253869e2c9a82a2fb611
ms.sourcegitcommit: 0af064e8b6778060f1bd365378d69b16fc9949b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2022
ms.locfileid: "67730976"
---
# <a name="collaborating-with-people-outside-your-organization"></a>Colaborar con personas ajenas a la organización

Las funcionalidades de uso compartido externo de Microsoft 365 proporcionan una oportunidad para que los usuarios de su organización colaboren con asociados, proveedores, clientes y otros que no tengan una cuenta en el directorio. Puede compartir equipos, canales o sitios completos con personas ajenas a su organización o solo archivos individuales.

La colaboración con personas ajenas a la organización consta de estos componentes principales:

- **Habilitar el uso compartido**: configure los controles de uso compartido entre Azure Active Directory, Teams, Grupos de Microsoft 365 y SharePoint para permitir el nivel de uso compartido que desea para su organización.
- **Configuración de relaciones organizativas** : si usa canales compartidos, debe configurar los valores de acceso entre inquilinos en Azure Active Directory para permitir el acceso de conexión directa B2B para cada organización con la que quiera colaborar. (Estas organizaciones también deben configurar relaciones organizativas con el inquilino).
- **Habilitar seguridad adicional** : aunque las características básicas de uso compartido se pueden configurar para requerir que las personas de fuera de su organización se autentiquen, Microsoft 365 proporciona muchas características de seguridad y cumplimiento adicionales para ayudarle a proteger los datos y mantener las directivas de gobernanza mientras se comparte externamente.

Lea [Configuración de la colaboración segura con Microsoft 365 y Microsoft Teams](/microsoft-365/solutions/setup-secure-collaboration-with-teams) para obtener información sobre cómo vincula el uso compartido externo con la guía general de colaboración de Microsoft 365.

## <a name="enable-sharing"></a>Habilitación del uso compartido

De forma predeterminada, el uso compartido con personas ajenas a la organización mediante el acceso de invitado o el acceso anónimo está habilitado, pero los canales compartidos deben habilitarse mediante la configuración de relaciones organizativas en Azure AD. La mayoría de los escenarios de uso compartido de invitados funcionan sin más configuración. Para confirmar la configuración de un escenario que está usando o habilitar uno nuevo, elija entre las siguientes opciones:

- [Colaborar en documentos](collaborate-on-documents.md) : obtenga información sobre cómo configurar Microsoft 365 para permitir el uso compartido y la colaboración con personas ajenas a su organización (invitados y usuarios no autenticados) en archivos y carpetas.
- [Colaborar en un sitio](collaborate-in-site.md) : obtenga información sobre cómo configurar Microsoft 365 para habilitar el uso compartido de sitios de SharePoint con invitados.
- [Colaborar como equipo](collaborate-as-team.md) : aprenda a configurar Microsoft 365 para habilitar la colaboración de invitados en Teams.
- [Colabore con participantes externos en un canal](/microsoft-365/solutions/collaborate-teams-direct-connect) para colaborar con personas ajenas a la organización en un canal compartido.

Para obtener un vistazo completo a la configuración de uso compartido de invitados disponible en Microsoft 365, consulte [Referencia de configuración de uso compartido de invitados de Microsoft 365](microsoft-365-guest-settings.md).

## <a name="enable-additional-security"></a>Habilitación de seguridad adicional

Una vez que haya habilitado el escenario que desea usar para compartir con personas ajenas a su organización, considere medidas de seguridad adicionales para ayudar a proteger el contenido frente al uso compartido inadecuado accidental o intencionado.

- [Procedimientos recomendados para compartir archivos y carpetas con usuarios no autenticados](best-practices-anonymous-sharing.md) : obtenga información sobre los procedimientos recomendados para compartir con usuarios no autenticados.
- [Limitar la exposición accidental](share-limit-accidental-exposure.md) : aprenda a reducir las posibilidades de compartir accidentalmente contenido confidencial con personas ajenas a la organización.
- [Crear un entorno de uso compartido de invitados seguro](create-secure-guest-sharing-environment.md) : obtenga información sobre las herramientas proporcionadas en Microsoft 365 para ayudar a garantizar que el uso compartido con personas ajenas a la organización se realiza de forma segura y segura y cumple los requisitos de gobernanza.

## <a name="collaborate-with-partner-companies"></a>Colaboración con empresas asociadas

Cuando trabaje en un proyecto grande que implique invitados de otra organización, considere la posibilidad de usar canales compartidos. Dado que los canales compartidos no usan cuentas de invitado, los usuarios de la otra organización pueden acceder al canal compartido directamente sin tener que iniciar sesión en la organización por separado.

Si tiene una relación de proveedor en curso en la que los invitados suelen cambiar, puede usar la administración de derechos en Azure Active Directory para simplificar la administración de invitados y permitir que la empresa asociada comparta esa responsabilidad. Consulte [Creación de una extranet B2B con invitados administrados](b2b-extranet.md) para obtener más información.

## <a name="limit-sharing"></a>Limitar el uso compartido

Si algunas de las características de uso compartido de Microsoft 365 entran en conflicto con las directivas de gobernanza, consulte [Limitar el uso compartido en Microsoft 365](microsoft-365-limit-sharing.md) para obtener información sobre las opciones para limitar el uso compartido.

## <a name="related-topics"></a>Temas relacionados

[Introducción a la colaboración de archivos en Microsoft 365](/sharepoint/intro-to-file-collaboration)

[Planear la colaboración de archivos en SharePoint con Microsoft 365](/sharepoint/deploy-file-collaboration)
