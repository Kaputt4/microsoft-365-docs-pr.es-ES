---
title: Configurar un conector para archivar datos de Twitter
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Configure un conector para importar datos de Twitter a Microsoft 365 para poder usar las características de cumplimiento, como la retención legal, la búsqueda de contenido y las directivas de retención.
ms.openlocfilehash: efc02dcf7b9c40fafedf230e4786f6f6494c27d6
ms.sourcegitcommit: ab0a944159d9349fbc7adc2f51c7f881254d7782
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "44210586"
---
# <a name="set-up-a-connector-to-archive-twitter-data-preview"></a>Configurar un conector para archivar datos de Twitter (versión preliminar)

Use un conector en el centro de cumplimiento de Microsoft 365 para importar y archivar datos de Twitter a Microsoft 365. Una vez que haya configurado y configurado el conector, éste se conectará a la cuenta de Twitter de su organización (de forma programada), convierte el contenido de un elemento a un formato de mensaje de correo electrónico y, a continuación, importa esos elementos a un buzón en Microsoft 365.

Una vez importados los datos de Twitter, puede aplicar las características de cumplimiento de Microsoft 365, como la retención por juicio, la búsqueda de contenido, el archivado local, la auditoría y las directivas de retención de Microsoft 365 a los datos de Twitter. Por ejemplo, cuando un buzón se coloca en retención por juicio o se asigna a una directiva de retención, se conservan los datos de Twitter. Puede buscar datos de terceros mediante la búsqueda de contenido o asociar el buzón en el que se almacenan los datos de Twitter con un custodio en un caso de exhibición avanzada de documentos electrónicos. El uso de un conector para importar y archivar datos de Twitter en Microsoft 365 puede ayudar a su organización a cumplir las directivas gubernamentales y regulatorias.

Una vez importados los datos de Twitter, puede aplicar las características de cumplimiento de Microsoft 365, como la retención por juicio, la búsqueda de contenido, el archivado local, la auditoría, el cumplimiento de comunicaciones y las directivas de retención de Microsoft 365 a los datos almacenados en el buzón. Por ejemplo, puede buscar datos de Twitter mediante la búsqueda de contenido o asociar el buzón en el que se almacenan los datos con un custodio en un caso de exhibición avanzada de documentos electrónicos. El uso de un conector para importar y archivar datos de Twitter en Microsoft 365 puede ayudar a su organización a cumplir las directivas gubernamentales y regulatorias.

## <a name="prerequisites-for-setting-up-a-connector-for-twitter"></a>Requisitos previos para configurar un conector para Twitter

Complete los siguientes requisitos previos para poder configurar y configurar un conector en el centro de cumplimiento de Microsoft 365 para importar y archivar datos de la cuenta de Twitter de su organización.

- Necesita una cuenta de Twitter para su organización; debe iniciar sesión en esta cuenta cuando configure el conector.

- La organización debe tener una suscripción de Azure válida. Si no tiene una suscripción a Azure existente, puede registrarse en una de estas opciones:

    - [Regístrese para obtener una suscripción gratuita de Azure de un año](https://azure.microsoft.com/free) 

    - [Registrarse para obtener una suscripción de pago de pago a través de la suscripción de Azure](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/)

    > [!NOTE]
    > La [suscripción gratuita de Azure Active Directory](use-your-free-azure-ad-subscription-in-office-365.md) que se incluye con la suscripción a Microsoft 365 no es compatible con los conectores del centro de seguridad & cumplimiento.

- La organización debe permitir que el servicio de importación de Office 365 obtenga acceso a los datos de buzones de la organización. Para dar su consentimiento a esta solicitud, vaya a [esta página](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent), inicie sesión con las credenciales de un administrador global y, después, acepte la solicitud.

- El usuario que configura el conector de Twitter en el centro de cumplimiento de Microsoft 365 (en el paso 5) debe tener asignado el rol importación y exportación de buzones de correo en Exchange Online. Este rol no está asignado a ningún grupo de roles de Exchange Online de forma predeterminada. Puede Agregar el rol importación y exportación de buzones al grupo de funciones de administración de la organización en Exchange Online. O bien, puede crear un grupo de roles, asignar el rol de importación y exportación de buzones de correo y, a continuación, agregar los usuarios adecuados como miembros. Para obtener más información, vea las secciones [crear grupos](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) de roles o [modificar grupos de roles](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) en el artículo sobre la administración de grupos de roles en Exchange Online.

## <a name="step-1-create-an-app-in-azure-active-directory"></a>Paso 1: crear una aplicación en Azure Active Directory

El primer paso es registrar una nueva aplicación en Azure Active Directory (AAD). Esta aplicación corresponde al recurso de la aplicación web que implementa en el paso 2 para Twitter Connector.

Para obtener instrucciones paso a paso, consulte [crear una aplicación en Azure Active Directory](deploy-twitter-connector.md#step-1-create-an-app-in-azure-active-directory).

Al finalizar este paso (siguiendo las instrucciones paso a paso), guardará la siguiente información en un archivo de texto. Estos valores se usarán en pasos posteriores del proceso de implementación.

- IDENTIFICADOR de la aplicación AAD

- Secreto de la aplicación AAD

- Identificador de inquilino

## <a name="step-2-deploy-connector-web-service-from-github-repository-to-your-azure-account"></a>Paso 2: implementar el servicio Web del conector desde el repositorio de GitHub a su cuenta de Azure

El siguiente paso es implementar el código fuente de la aplicación de Twitter Connector que usará la API de Twitter para conectarse a su cuenta de Twitter y extraer los datos para que pueda importarlos a Microsoft 365. El conector de Twitter que implemente para su organización cargará los elementos desde la cuenta de Twitter de su organización a la ubicación de almacenamiento de Azure que se crea en este paso. Después de crear un conector de Twitter en el centro de cumplimiento de Microsoft 365 (en el paso 5), el servicio de importación de Office 365 copiará los datos de Twitter desde la ubicación de Azure Storage a un buzón en Microsoft 365. Como se explicó anteriormente en la sección [requisitos previos](#prerequisites-for-setting-up-a-connector-for-twitter) , debe tener una suscripción de Azure válida para crear una cuenta de almacenamiento de Azure.

Para implementar el código fuente de la aplicación de Twitter Connector:

1. Vaya a [este sitio de github](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet).

2. Haga clic en **implementar en Azure**.

Para obtener instrucciones paso a paso, consulte [implementar el servicio Web del conector de github en su cuenta de Azure](deploy-twitter-connector.md#step-2-deploy-the-connector-web-service-from-github-to-your-azure-account).

Mientras sigue las instrucciones paso a paso para completar este paso, proporciona la siguiente información

- APISecretKey: este secreto se crea durante la finalización de este paso. Se usa en el paso 5.

- tenantId: el identificador de inquilino de su organización de Microsoft 365 que copió después de crear la aplicación de Twitter en Azure Active Directory en el paso 1.

Después de completar este paso, asegúrese de copiar la dirección URL del servicio de aplicaciones (por ejemplo, `https://twitterconnector.azurewebsites.net` ). Debe usar esta dirección URL para completar los pasos 3, 4 y 5).

## <a name="step-3-create-developer-app-on-twitter"></a>Paso 3: crear una aplicación para desarrolladores en Twitter

El siguiente paso es crear y configurar una aplicación para desarrolladores en Twitter. El conector personalizado que ha creado en el paso 7 usa la aplicación de Twitter para interactuar con la API de Twitter y obtener datos de la cuenta de Twitter de su organización.

Para obtener instrucciones paso a paso, consulte [crear la aplicación de Twitter](deploy-twitter-connector.md#step-3-create-the-twitter-app).

Al finalizar este paso (siguiendo las instrucciones paso a paso), guarde la siguiente información en un archivo de texto. Estos valores se usarán para configurar la aplicación de Twitter Connector en el paso 4.

- Clave de API de Twitter

- Clave secreta de API de Twitter

- Token de acceso de Twitter

- Secreto de token de acceso de Twitter

## <a name="step-4-configure-the-twitter-connector-app"></a>Paso 4: configurar la aplicación de Twitter Connector

El paso siguiente es agregar opciones de configuración a la aplicación conector de Twitter que implementó en el paso 2. Para ello, vaya a la Página principal de la aplicación del conector y configure.

Para obtener instrucciones paso a paso, consulte [Configure the Connector Web App](deploy-twitter-connector.md#step-4-configure-the-connector-web-app).

Al finalizar este paso (siguiendo las instrucciones paso a paso), proporcionará la siguiente información (que ha copiado a un archivo de texto después de completar los pasos anteriores):

- Clave de API de Twitter (obtenida en el paso 3)

- Clave secreta de la API de Twitter (obtenida en el paso 3)

- Token de acceso de Twitter (obtenido en el paso 3)

- Token de acceso de Twitter secreto (obtenido en el paso 3)

- IDENTIFICADOR de aplicación de Azure Active Directory (el identificador de la aplicación de AAD que se obtuvo en el paso 1)

- Secreto de la aplicación de Azure Active Directory (el secreto de la aplicación AAD obtenido en el paso 1)

## <a name="step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center"></a>Paso 5: configurar un conector de Twitter en el centro de cumplimiento de Microsoft 365

El último paso consiste en configurar el conector de Twitter en el centro de cumplimiento de Microsoft 365 que va a importar datos de la cuenta de Twitter de su organización a un buzón específico en Microsoft 365. Después de completar este paso, el servicio de importación de Office 365 empezará a importar datos de la cuenta de Twitter de su organización a Microsoft 365.

Para obtener instrucciones paso a paso, consulte [configurar un conector de Twitter en el centro de cumplimiento de Microsoft 365](deploy-twitter-connector.md#step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center). 

Al finalizar este paso (siguiendo las instrucciones paso a paso), proporcionará la siguiente información (que ha copiado en un archivo de texto después de completar los pasos).

- Dirección URL de Azure App Service (obtenida en el paso 2; por ejemplo, `https://twitterconnector.azurewebsites.net` )

- APISecretKey (creado en el paso 2)
