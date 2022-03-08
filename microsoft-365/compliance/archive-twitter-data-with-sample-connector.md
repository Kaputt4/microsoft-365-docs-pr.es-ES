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
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: seo-marvel-apr2020
description: Obtenga información sobre cómo los administradores pueden configurar y usar un conector nativo para importar datos de Twitter a Microsoft 365.
ms.openlocfilehash: 959cdd49d229334f3129eb21505c4489d23ded4f
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63320639"
---
# <a name="set-up-a-microsoft-connector-to-archive-twitter-data-preview"></a>Configurar un conector de Microsoft para archivar datos de Twitter (versión preliminar)

Use un conector en el Centro de cumplimiento de Microsoft 365 para importar y archivar datos de Twitter a Microsoft 365. Después de configurar y configurar el conector, se conecta a la cuenta de Twitter de la organización (de forma programada), convierte el contenido de un elemento en un formato de mensaje de correo electrónico y, a continuación, importa esos elementos a un buzón de correo en Microsoft 365.

Después de importar los datos de Twitter, puede aplicar Microsoft 365 las características de cumplimiento como retención por juicio, búsqueda de contenido, archivado de In-Place, auditoría y directivas de retención Microsoft 365 a los datos de Twitter. Por ejemplo, cuando un buzón se coloca en retención por juicio o se asigna a una directiva de retención, se conservan los datos de Twitter. Puede buscar datos de terceros mediante la búsqueda de contenido o asociar el buzón donde se almacenan los datos de Twitter con un custodio en un Advanced eDiscovery caso. El uso de un conector para importar y archivar datos de Twitter en Microsoft 365 puede ayudar a su organización a cumplir con las directivas gubernamentales y reglamentarias.

Después de importar los datos de Twitter, puede aplicar Microsoft 365 características de cumplimiento como retención por juicio, búsqueda de contenido, archivado de In-Place, auditoría, cumplimiento de comunicaciones y directivas de retención Microsoft 365 a los datos almacenados en el buzón. Por ejemplo, puede buscar datos de Twitter mediante búsqueda de contenido o asociar el buzón donde se almacenan los datos con un custodio en un Advanced eDiscovery caso. El uso de un conector para importar y archivar datos de Twitter en Microsoft 365 puede ayudar a su organización a cumplir con las directivas gubernamentales y reglamentarias.

## <a name="before-you-set-up-a-connector"></a>Antes de configurar un conector

Complete los siguientes requisitos previos antes de configurar y configurar un conector en el Centro de cumplimiento de Microsoft 365 importar y archivar datos desde la cuenta de Twitter de su organización.

- Necesita una cuenta de Twitter para su organización; debe iniciar sesión en esta cuenta al configurar el conector.

- Su organización debe tener una suscripción válida de Azure. Si no tiene una suscripción de Azure existente, puede registrarse en una de estas opciones:

    - [Registrarse para obtener una suscripción gratuita de Azure de un año](https://azure.microsoft.com/free) 

    - [Registrarse para una suscripción de Azure de pago por uso](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/)

    > [!NOTE]
    > La [suscripción Azure Active Directory](use-your-free-azure-ad-subscription-in-office-365.md) gratuita que se incluye con la suscripción Microsoft 365 no admite los conectores de la Centro de cumplimiento de Microsoft 365.

- El conector de Twitter puede importar un total de 200 000 elementos en un solo día. Si hay más de 200 000 elementos de Twitter en un día, ninguno de esos elementos se importará a Microsoft 365.

- El usuario que configura el conector de Twitter en el Centro de cumplimiento de Microsoft 365 (en el paso 5) debe tener asignado el rol de administrador del conector de datos. Este rol es necesario para agregar conectores en la **página Conectores de datos** de la Centro de cumplimiento de Microsoft 365. Este rol se agrega de forma predeterminada a varios grupos de roles. Para obtener una lista de estos grupos de roles, vea la sección "Roles en los centros de seguridad y cumplimiento" en Permisos en el [Centro de seguridad & cumplimiento](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center). Como alternativa, un administrador de la organización puede crear un grupo de roles personalizado, asignar el rol de administrador del conector de datos y, a continuación, agregar los usuarios adecuados como miembros. Para obtener instrucciones, vea la sección "Crear un grupo de roles personalizado" en [Permisos en el Centro de cumplimiento de Microsoft 365](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group).

## <a name="step-1-create-an-app-in-azure-active-directory"></a>Paso 1: Crear una aplicación en Azure Active Directory

El primer paso es registrar una nueva aplicación en Azure Active Directory (AAD). Esta aplicación corresponde al recurso de aplicación web que implementas en el paso 2 para el conector de Twitter.

Para obtener instrucciones paso a paso, consulta [Crear una aplicación en Azure Active Directory](deploy-twitter-connector.md#step-1-create-an-app-in-azure-active-directory).

Durante la finalización de este paso (siguiendo las instrucciones paso a paso), guardará la siguiente información en un archivo de texto. Estos valores se usarán en pasos posteriores del proceso de implementación.

- AAD de aplicación

- AAD secreto de aplicación

- Identificador de inquilino

## <a name="step-2-deploy-connector-web-service-from-github-repository-to-your-azure-account"></a>Paso 2: Implementar el servicio web del conector GitHub repositorio en su cuenta de Azure

El siguiente paso es implementar el código fuente de la aplicación del conector de Twitter que usará la API de Twitter para conectarse a tu cuenta de Twitter y extraer datos para que puedas importarlo a Microsoft 365. El conector de Twitter que implemente para su organización cargará los elementos de la cuenta de Twitter de su organización en la ubicación Azure Storage que se crea en este paso. Después de crear un conector de Twitter en el Centro de cumplimiento de Microsoft 365 (en el paso 5), el servicio de importación de Microsoft 365 copiará los datos de Twitter de la ubicación de Azure Storage en un buzón de Microsoft 365. Como se explicó [anteriormente en](#before-you-set-up-a-connector) la sección Antes de configurar un conector, debe tener una suscripción válida de Azure para crear una cuenta Azure Storage conector.

Para implementar el código fuente de la aplicación del conector de Twitter:

1. Vaya a [este GitHub sitio](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet).

2. Haga **clic en Implementar en Azure**.

Para obtener instrucciones paso a paso, consulte [Deploy the connector web service from GitHub to your Azure account](deploy-twitter-connector.md#step-2-deploy-the-connector-web-service-from-github-to-your-azure-account).

Si bien sigue las instrucciones paso a paso para completar este paso, proporcione la siguiente información

- APISecretKey: este secreto se crea durante la finalización de este paso. Se usa en el paso 5.

- tenantId: el identificador de inquilino de la Microsoft 365 que copió después de crear la aplicación de Twitter en Azure Active Directory en el paso 1.

Después de completar este paso, asegúrese de copiar la dirección URL del servicio de aplicaciones (por ejemplo, `https://twitterconnector.azurewebsites.net`). Debe usar esta dirección URL para completar los pasos 3, 4 y 5).

## <a name="step-3-create-developer-app-on-twitter"></a>Paso 3: Crear aplicación para desarrolladores en Twitter

El siguiente paso es crear y configurar una aplicación para desarrolladores en Twitter. El conector personalizado que creas en el paso 7 usa la aplicación twitter para interactuar con la API de Twitter para obtener datos de la cuenta de Twitter de tu organización.

Para obtener instrucciones paso a paso, consulta [Crear la aplicación de Twitter](deploy-twitter-connector.md#step-3-create-the-twitter-app).

Durante la finalización de este paso (siguiendo las instrucciones paso a paso), se guarda la siguiente información en un archivo de texto. Estos valores se usarán para configurar la aplicación de conector de Twitter en el paso 4.

- Clave de API de Twitter

- Clave secreta de la API de Twitter

- Token de acceso de Twitter

- Secreto de token de acceso de Twitter

## <a name="step-4-configure-the-twitter-connector-app"></a>Paso 4: Configurar la aplicación del conector de Twitter

El siguiente paso es agregar opciones de configuración a la aplicación de conector de Twitter que implementó en el paso 2. Para ello, vaya a la página principal de la aplicación del conector y la configure.

Para obtener instrucciones paso a paso, consulta [Configurar la aplicación web del conector](deploy-twitter-connector.md#step-4-configure-the-connector-web-app).

Durante la finalización de este paso (siguiendo las instrucciones paso a paso), proporcionará la siguiente información (que ha copiado en un archivo de texto después de completar los pasos anteriores):

- Clave de API de Twitter (obtenida en el paso 3)

- Clave secreta de la API de Twitter (obtenida en el paso 3)

- Token de acceso de Twitter (obtenido en el paso 3)

- Secreto de token de acceso de Twitter (obtenido en el paso 3)

- Azure Active Directory de aplicación (el AAD de aplicación obtenido en el paso 1)

- Azure Active Directory secreto de aplicación (el secreto AAD de aplicación obtenido en el paso 1)

## <a name="step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center"></a>Paso 5: Configurar un conector de Twitter en el Centro de cumplimiento de Microsoft 365

El paso final es configurar el conector de Twitter en el Centro de cumplimiento de Microsoft 365 que importará datos de la cuenta de Twitter de su organización a un buzón especificado en Microsoft 365. Después de completar este paso, el servicio Microsoft 365 importará los datos de la cuenta de Twitter de su organización a Microsoft 365.

Para obtener instrucciones paso a paso, consulta [Configurar un conector de Twitter en el Centro de cumplimiento de Microsoft 365](deploy-twitter-connector.md#step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center). 

Durante la finalización de este paso (siguiendo las instrucciones paso a paso), proporcionará la siguiente información (que ha copiado en un archivo de texto después de completar los pasos).

- Dirección URL del servicio de aplicaciones de Azure (obtenida en el paso 2, por ejemplo, `https://twitterconnector.azurewebsites.net`)

- APISecretKey (que creó en el paso 2)