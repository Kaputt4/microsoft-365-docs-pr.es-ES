---
title: Configurar un conector para archivar datos de Twitter
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: seo-marvel-apr2020
description: Obtenga información sobre cómo los administradores pueden configurar y usar un conector nativo para importar datos de Twitter a Microsoft 365.
ms.openlocfilehash: 5b35259985664ac47b9d1f6265c8ca4282a4cd31
ms.sourcegitcommit: 7d4aa58ae9fc893825b6e648fa3f072c3ac59628
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2021
ms.locfileid: "49790068"
---
# <a name="set-up-a-connector-to-archive-twitter-data-preview"></a>Configurar un conector para archivar datos de Twitter (versión preliminar)

Use un conector en el Centro de cumplimiento de Microsoft 365 para importar y archivar datos de Twitter a Microsoft 365. Después de configurar y configurar el conector, se conecta a la cuenta de Twitter de su organización (de forma programada), convierte el contenido de un elemento en un formato de mensaje de correo electrónico y, a continuación, importa esos elementos a un buzón de Microsoft 365.

Después de importar los datos de Twitter, puede aplicar las características de cumplimiento de Microsoft 365, como retención por juicio, búsqueda de contenido, archivado de In-Place, auditoría y directivas de retención de Microsoft 365 a los datos de Twitter. Por ejemplo, cuando un buzón se coloca en retención por juicio o se asigna a una directiva de retención, se conservan los datos de Twitter. Puede buscar datos de terceros mediante la búsqueda de contenido o asociar el buzón donde se almacenan los datos de Twitter con un administrador en un caso de eDiscovery avanzado. El uso de un conector para importar y archivar datos de Twitter en Microsoft 365 puede ayudar a su organización a cumplir con las directivas gubernamentales y reglamentarias.

Después de importar los datos de Twitter, puede aplicar las características de cumplimiento de Microsoft 365, como retención por juicio, búsqueda de contenido, archivado de In-Place, auditoría, cumplimiento de comunicaciones y directivas de retención de Microsoft 365 a los datos almacenados en el buzón. Por ejemplo, puede buscar datos de Twitter mediante la búsqueda de contenido o asociar el buzón donde se almacenan los datos con un administrador en un caso de eDiscovery avanzado. El uso de un conector para importar y archivar datos de Twitter en Microsoft 365 puede ayudar a su organización a cumplir con las directivas gubernamentales y reglamentarias.

## <a name="before-you-set-up-a-connector"></a>Antes de configurar un conector

Complete los siguientes requisitos previos antes de poder configurar un conector en el Centro de cumplimiento de Microsoft 365 para importar y archivar datos desde la cuenta de Twitter de su organización.

- Necesita una cuenta de Twitter para su organización; debe iniciar sesión en esta cuenta al configurar el conector.

- Su organización debe tener una suscripción válida de Azure. Si no tiene una suscripción de Azure existente, puede registrarse para obtener una de estas opciones:

    - [Registrarse para obtener una suscripción gratuita de Azure de un año](https://azure.microsoft.com/free) 

    - [Registrarse para obtener una suscripción de Azure de pago por uso](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/)

    > [!NOTE]
    > La suscripción gratuita de [Azure Active Directory](use-your-free-azure-ad-subscription-in-office-365.md) que se incluye con su suscripción de Microsoft 365 no admite los conectores en el Centro de seguridad & cumplimiento.

- El conector de Twitter puede importar un total de 200 000 elementos en un solo día. Si hay más de 200 000 elementos de Twitter en un día, ninguno de esos elementos se importará a Microsoft 365.

- El usuario que configura el conector de Twitter en el Centro de cumplimiento de Microsoft 365 (en el paso 5) debe tener asignado el rol de importación y exportación de buzones en Exchange Online. Este rol no está asignado a ningún grupo de roles de Exchange Online de forma predeterminada. Puede agregar el rol De importación y exportación de buzones al grupo de roles Administración de la organización en Exchange Online. O bien, puede crear un grupo de roles, asignar el rol de importación y exportación de buzones de correo y, a continuación, agregar los usuarios adecuados como miembros. Para obtener más información, vea [](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) las secciones Crear grupos de [roles](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) o Modificar grupos de roles en el artículo "Administrar grupos de roles en Exchange Online".

## <a name="step-1-create-an-app-in-azure-active-directory"></a>Paso 1: Crear una aplicación en Azure Active Directory

El primer paso es registrar una nueva aplicación en Azure Active Directory (AAD). Esta aplicación corresponde al recurso de aplicación web que implementó en el paso 2 para el conector de Twitter.

Para obtener instrucciones paso a paso, consulte [Crear una aplicación en Azure Active Directory.](deploy-twitter-connector.md#step-1-create-an-app-in-azure-active-directory)

Durante la finalización de este paso (siguiendo las instrucciones paso a paso), guardará la siguiente información en un archivo de texto. Estos valores se usarán en pasos posteriores del proceso de implementación.

- Id. de aplicación de AAD

- Secreto de aplicación de AAD

- Id. de inquilino

## <a name="step-2-deploy-connector-web-service-from-github-repository-to-your-azure-account"></a>Paso 2: Implementar el servicio web del conector desde el repositorio de GitHub en su cuenta de Azure

El siguiente paso es implementar el código fuente de la aplicación del conector de Twitter que usará la API de Twitter para conectarse a su cuenta de Twitter y extraer datos para poder importarlos a Microsoft 365. El conector de Twitter que implemente para su organización cargará los elementos de la cuenta de Twitter de su organización en la ubicación de Azure Storage que se crea en este paso. Después de crear un conector de Twitter en el Centro de cumplimiento de Microsoft 365 (en el paso 5), el servicio de importación de Microsoft 365 copiará los datos de Twitter de la ubicación de Azure Storage en un buzón de Microsoft 365. Como se explicó [anteriormente](#before-you-set-up-a-connector) en la sección Antes de configurar un conector, debe tener una suscripción válida de Azure para crear una cuenta de Azure Storage.

Para implementar el código fuente para la aplicación del conector de Twitter:

1. Vaya a [este sitio de GitHub.](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet)

2. Haga **clic en Implementar en Azure.**

Para obtener instrucciones paso a paso, vea Implementar el servicio web del conector [de GitHub en su cuenta de Azure.](deploy-twitter-connector.md#step-2-deploy-the-connector-web-service-from-github-to-your-azure-account)

Mientras siga las instrucciones paso a paso para completar este paso, proporcione la siguiente información

- APISecretKey: este secreto se crea durante la finalización de este paso. Se usa en el paso 5.

- tenantId: el id. de inquilino de la organización de Microsoft 365 que copió después de crear la aplicación de Twitter en Azure Active Directory en el paso 1.

Después de completar este paso, asegúrese de copiar la dirección URL del servicio de aplicaciones (por ejemplo, `https://twitterconnector.azurewebsites.net` ). Debe usar esta dirección URL para completar los pasos 3, 4 y 5).

## <a name="step-3-create-developer-app-on-twitter"></a>Paso 3: Crear una aplicación para desarrolladores en Twitter

El siguiente paso es crear y configurar una aplicación para desarrolladores en Twitter. El conector personalizado que cree en el paso 7 usa la aplicación twitter para interactuar con la API de Twitter para obtener datos de la cuenta de Twitter de su organización.

Para obtener instrucciones paso a paso, consulta [Crear la aplicación de Twitter.](deploy-twitter-connector.md#step-3-create-the-twitter-app)

Durante la finalización de este paso (siguiendo las instrucciones paso a paso), se guarda la siguiente información en un archivo de texto. Estos valores se usarán para configurar la aplicación del conector de Twitter en el paso 4.

- Clave de API de Twitter

- Clave secreta de la API de Twitter

- Token de acceso de Twitter

- Secreto de token de acceso de Twitter

## <a name="step-4-configure-the-twitter-connector-app"></a>Paso 4: Configurar la aplicación del conector de Twitter

El siguiente paso es agregar opciones de configuración a la aplicación de conector de Twitter que implementó en el paso 2. Para ello, vaya a la página principal de la aplicación del conector y la configure.

Para obtener instrucciones paso a paso, vea [Configurar la aplicación web del conector.](deploy-twitter-connector.md#step-4-configure-the-connector-web-app)

Durante la finalización de este paso (siguiendo las instrucciones paso a paso), proporcionará la siguiente información (que ha copiado en un archivo de texto después de completar los pasos anteriores):

- Clave de API de Twitter (obtenida en el paso 3)

- Clave secreta de la API de Twitter (obtenida en el paso 3)

- Token de acceso de Twitter (obtenido en el paso 3)

- Secreto de token de acceso de Twitter (obtenido en el paso 3)

- Identificador de aplicación de Azure Active Directory (el identificador de aplicación de AAD obtenido en el paso 1)

- Secreto de aplicación de Azure Active Directory (el secreto de aplicación de AAD obtenido en el paso 1)

## <a name="step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center"></a>Paso 5: Configurar un conector de Twitter en el Centro de cumplimiento de Microsoft 365

El último paso es configurar el conector de Twitter en el Centro de cumplimiento de Microsoft 365 que importará datos desde la cuenta de Twitter de su organización a un buzón especificado en Microsoft 365. Después de completar este paso, el servicio de importación de Microsoft 365 empezará a importar datos desde la cuenta de Twitter de su organización a Microsoft 365.

Para obtener instrucciones paso a paso, consulte Configurar un conector de Twitter en el Centro de cumplimiento de [Microsoft 365.](deploy-twitter-connector.md#step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center) 

Durante la finalización de este paso (siguiendo las instrucciones paso a paso), proporcionarás la siguiente información (que has copiado en un archivo de texto después de completar los pasos).

- Dirección URL del servicio de aplicaciones de Azure (obtenida en el paso 2; por ejemplo, `https://twitterconnector.azurewebsites.net` )

- APISecretKey (que creó en el paso 2)
