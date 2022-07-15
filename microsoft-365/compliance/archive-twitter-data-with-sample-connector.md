---
title: Configurar un conector para archivar datos de Twitter
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
ms.date: 04/08/2022
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: seo-marvel-apr2020
description: Obtenga información sobre cómo los administradores pueden configurar y usar un conector nativo para importar datos de Twitter a Microsoft 365.
ms.openlocfilehash: 83558b4a2f188853b4deac31cf636476480a2557
ms.sourcegitcommit: 5e5c2c1f7c321b5eb1c5b932c03bdd510005de13
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/15/2022
ms.locfileid: "66822255"
---
# <a name="set-up-a-microsoft-connector-to-archive-twitter-data-preview"></a>Configuración de un conector de Microsoft para archivar datos de Twitter (versión preliminar)

Use un conector en el portal de cumplimiento Microsoft Purview para importar y archivar datos de Twitter a Microsoft 365. Después de configurar y configurar el conector, se conecta a la cuenta de Twitter de su organización (de forma programada), convierte el contenido de un elemento en un formato de mensaje de correo electrónico y, a continuación, importa esos elementos a un buzón de correo de Microsoft 365.

Una vez importados los datos de Twitter, puede aplicar las características de Microsoft Purview, como la suspensión por juicio, la búsqueda de contenido, el archivado de In-Place, la auditoría y las directivas de retención de Microsoft 365 a los datos de Twitter. Por ejemplo, cuando un buzón se coloca en suspensión por juicio o se asigna a una directiva de retención, se conservan los datos de Twitter. Puede buscar datos de terceros mediante Búsqueda de contenido o asociar el buzón donde se almacenan los datos de Twitter con un custodio en un caso de Microsoft Purview eDiscovery (Premium). El uso de un conector para importar y archivar datos de Twitter en Microsoft 365 puede ayudar a su organización a cumplir las directivas gubernamentales y normativas.

Una vez importados los datos de Twitter, puede aplicar características de Microsoft Purview como suspensión por juicio, búsqueda de contenido, archivado de In-Place, auditoría, cumplimiento de comunicaciones y directivas de retención de Microsoft 365 a los datos almacenados en el buzón. Por ejemplo, puede buscar datos de Twitter mediante búsqueda de contenido o asociar el buzón donde se almacenan los datos con un custodio en un caso de exhibición de documentos electrónicos (Premium). El uso de un conector para importar y archivar datos de Twitter en Microsoft 365 puede ayudar a su organización a cumplir las directivas gubernamentales y normativas.

Si desea participar en la versión preliminar, póngase en contacto con el equipo en dcfeedback@microsoft.com.

## <a name="before-you-set-up-a-connector"></a>Antes de configurar un conector

Complete los siguientes requisitos previos antes de configurar y configurar un conector en el portal de cumplimiento para importar y archivar datos de la cuenta de Twitter de su organización.

- Necesita una cuenta de Twitter para su organización; debe iniciar sesión en esta cuenta al configurar el conector.

- La organización debe tener una suscripción de Azure válida. Si no tiene una suscripción de Azure existente, puede registrarse para obtener una de estas opciones:

    - [Registrarse para obtener una suscripción gratuita de Azure de un año](https://azure.microsoft.com/free) 

    - [Registrarse para obtener una suscripción de Azure de pago por uso](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/)

    > [!NOTE]
    > La [suscripción gratuita de Azure Active Directory](use-your-free-azure-ad-subscription-in-office-365.md) que se incluye con la suscripción de Microsoft 365 no admite los conectores en el portal de cumplimiento.

- El conector de Twitter puede importar un total de 200 000 elementos en un solo día. Si hay más de 200 000 elementos de Twitter en un día, ninguno de esos elementos se importará a Microsoft 365.

- Al usuario que configura el conector de Twitter en el portal de cumplimiento (en el paso 5) se le debe asignar el rol Administración Conector de datos. Este rol es necesario para agregar conectores en la página **Conectores de datos** del portal de cumplimiento. Este rol se agrega de forma predeterminada a varios grupos de roles. Para obtener una lista de estos grupos de roles, consulte la sección "Roles en los centros de seguridad y cumplimiento" de [Permisos en el Centro de cumplimiento de & seguridad](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center). Como alternativa, un administrador de su organización puede crear un grupo de roles personalizado, asignar el rol Administración conector de datos y, a continuación, agregar los usuarios adecuados como miembros. Para obtener instrucciones, consulte la sección "Crear un grupo de roles personalizado" en [Permisos en el portal de cumplimiento Microsoft Purview](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group).

## <a name="step-1-create-an-app-in-azure-active-directory"></a>Paso 1: Creación de una aplicación en Azure Active Directory

El primer paso es registrar una nueva aplicación en Azure Active Directory (AAD). Esta aplicación corresponde al recurso de aplicación web que implementa en el paso 2 para el conector de Twitter.

Para obtener instrucciones paso a paso, consulte [Creación de una aplicación en Azure Active Directory](deploy-twitter-connector.md#step-1-create-an-app-in-azure-active-directory).

Durante la finalización de este paso (siguiendo las instrucciones paso a paso), guardará la siguiente información en un archivo de texto. Estos valores se usarán en pasos posteriores en el proceso de implementación.

- Identificador de aplicación de AAD

- Secreto de aplicación de AAD

- Identificador de inquilino

## <a name="step-2-deploy-connector-web-service-from-github-repository-to-your-azure-account"></a>Paso 2: Implementación del servicio web del conector desde el repositorio de GitHub en la cuenta de Azure

El siguiente paso es implementar el código fuente de la aplicación del conector de Twitter que usará la API de Twitter para conectarse a su cuenta de Twitter y extraer datos para que pueda importarlos a Microsoft 365. El conector de Twitter que implemente para su organización cargará los elementos de la cuenta de Twitter de la organización en la ubicación de Azure Storage que se crea en este paso. Después de crear un conector de Twitter en el portal de cumplimiento (en el paso 5), el servicio de importación de Microsoft 365 copiará los datos de Twitter de la ubicación de Azure Storage en un buzón de Microsoft 365. Como se explicó anteriormente en la sección [Antes de configurar un conector](#before-you-set-up-a-connector) , debe tener una suscripción de Azure válida para crear una cuenta de Azure Storage.

Para implementar el código fuente de la aplicación del conector de Twitter:

1. Vaya a [este sitio de GitHub](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet).

2. Haga clic en **Implementar en Azure**.

Para obtener instrucciones paso a paso, consulte [Implementación del servicio web del conector desde GitHub en su cuenta de Azure](deploy-twitter-connector.md#step-2-deploy-the-connector-web-service-from-github-to-your-azure-account).

Mientras sigue las instrucciones paso a paso para completar este paso, proporciona la siguiente información.

- APISecretKey: este secreto se crea durante la finalización de este paso. Se usa en el paso 5.

- tenantId: el identificador de inquilino de la organización de Microsoft 365 que copió después de crear la aplicación de Twitter en Azure Active Directory en el paso 1.

Después de completar este paso, asegúrese de copiar la dirección URL de App Service (por ejemplo, `https://twitterconnector.azurewebsites.net`). Debe usar esta dirección URL para completar los pasos 3, 4 y 5).

## <a name="step-3-create-developer-app-on-twitter"></a>Paso 3: Creación de una aplicación para desarrolladores en Twitter

El siguiente paso es crear y configurar una aplicación para desarrolladores en Twitter. El conector personalizado que cree en el paso 7 usa la aplicación twitter para interactuar con la API de Twitter y obtener datos de la cuenta de Twitter de su organización.

Para obtener instrucciones paso a paso, consulte [Creación de la aplicación de Twitter](deploy-twitter-connector.md#step-3-create-the-twitter-app).

Durante la finalización de este paso (siguiendo las instrucciones paso a paso), se guarda la siguiente información en un archivo de texto. Estos valores se usarán para configurar la aplicación del conector de Twitter en el paso 4.

- Clave de API de Twitter

- Clave secreta de la API de Twitter

- Token de acceso de Twitter

- Secreto de token de acceso de Twitter

## <a name="step-4-configure-the-twitter-connector-app"></a>Paso 4: Configuración de la aplicación del conector de Twitter

El siguiente paso es agregar la configuración de configuración a la aplicación del conector de Twitter que implementó en el paso 2. Para ello, vaya a la página principal de la aplicación del conector y configurándola.

Para obtener instrucciones paso a paso, consulte [Configuración de la aplicación web del conector](deploy-twitter-connector.md#step-4-configure-the-connector-web-app).

Durante la finalización de este paso (siguiendo las instrucciones paso a paso), proporcionará la siguiente información (que ha copiado en un archivo de texto después de completar los pasos anteriores):

- Clave de API de Twitter (obtenida en el paso 3)

- Clave secreta de la API de Twitter (obtenida en el paso 3)

- Token de acceso de Twitter (obtenido en el paso 3)

- Secreto de token de acceso de Twitter (obtenido en el paso 3)

- Identificador de aplicación de Azure Active Directory (el identificador de aplicación de AAD obtenido en el paso 1)

- Secreto de aplicación de Azure Active Directory (el secreto de aplicación de AAD obtenido en el paso 1)

## <a name="step-5-set-up-a-twitter-connector-in-the-compliance-portal"></a>Paso 5: Configurar un conector de Twitter en el portal de cumplimiento

El último paso es configurar el conector de Twitter en el portal de cumplimiento que importará datos de la cuenta de Twitter de su organización a un buzón especificado en Microsoft 365. Después de completar este paso, el servicio de importación de Microsoft 365 comenzará a importar datos de la cuenta de Twitter de su organización a Microsoft 365.

Para obtener instrucciones paso a paso, consulte [Configuración de un conector de Twitter en el portal de cumplimiento Microsoft Purview](deploy-twitter-connector.md#step-5-set-up-a-twitter-connector-in-the-compliance-portal).

Durante la finalización de este paso (siguiendo las instrucciones paso a paso), proporcionará la siguiente información (que ha copiado en un archivo de texto después de completar los pasos).

- Dirección URL de Azure App Service (obtenida en el paso 2; por ejemplo, `https://twitterconnector.azurewebsites.net`)

- APISecretKey (que creó en el paso 2)