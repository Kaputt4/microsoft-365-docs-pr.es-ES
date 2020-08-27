---
title: Configurar un conector para archivar datos de Facebook
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
description: Aprenda a configurar & usar un conector en el centro de cumplimiento de Microsoft 365 para importar & datos de archivo de las páginas de empresa de Facebook a Microsoft 365.
ms.openlocfilehash: 747f98ff084eaa8536c10b2f4edefcc20d11d7f9
ms.sourcegitcommit: 195172dd836e8a793e8e0c2db3323b7391bc51ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2020
ms.locfileid: "47255857"
---
# <a name="set-up-a-connector-to-archive-facebook-data-preview"></a>Configurar un conector para archivar datos de Facebook (versión preliminar)

Use un conector en el centro de cumplimiento de Microsoft 365 para importar y archivar datos de las páginas de empresa de Facebook a Microsoft 365. Una vez que haya configurado y configurado el conector, se conecta a la página de empresa de Facebook (de forma programada), convierte el contenido de los elementos de Facebook a un formato de mensaje de correo electrónico y, a continuación, importa esos elementos a un buzón en Microsoft 365.

Una vez importados los datos de Facebook, puede aplicar las características de cumplimiento de Microsoft 365, como la retención por juicio, la búsqueda de contenido, el archivado local, la auditoría, el cumplimiento de comunicaciones y las directivas de retención de Microsoft 365 a los datos de Facebook. Por ejemplo, cuando un buzón se coloca en retención por juicio o se asigna a una directiva de retención, los datos de Facebook se conservan. Puede buscar datos de terceros mediante la búsqueda de contenido o asociar el buzón en el que se almacenan los datos de Facebook con un custodio en un caso de exhibición avanzada de documentos electrónicos. El uso de un conector para importar y archivar datos de Facebook en Microsoft 365 puede ayudar a su organización a cumplir las directivas gubernamentales y regulatorias.

## <a name="prerequisites-for-setting-up-a-connector-for-facebook-business-pages"></a>Requisitos previos para configurar un conector para páginas empresariales de Facebook

Complete los siguientes requisitos previos para poder configurar y configurar un conector en el centro de cumplimiento de Microsoft 365 para importar y archivar datos de las páginas de negocio de Facebook de la organización. 

- Necesita una cuenta de Facebook para las páginas empresariales de su organización (debe iniciar sesión en esta cuenta cuando configure el conector). Actualmente, solo puede archivar datos de páginas empresariales de Facebook; no se pueden archivar datos de perfiles de Facebook individuales.

- La organización debe tener una suscripción de Azure válida. Si no tiene una suscripción a Azure existente, puede registrarse en una de estas opciones:

    - [Regístrese para obtener una suscripción gratuita de Azure de un año](https://azure.microsoft.com/free) 

    - [Registrarse para obtener una suscripción de pago de pago a través de la suscripción de Azure](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/)

    > [!NOTE]
    > La [suscripción gratuita de Azure Active Directory](use-your-free-azure-ad-subscription-in-office-365.md) que se incluye con la suscripción a Microsoft 365 no es compatible con los conectores del centro de seguridad & cumplimiento.

- La organización debe permitir que el servicio de importación de Office 365 obtenga acceso a los datos de buzones de la organización. Para dar su consentimiento a esta solicitud, vaya a [esta página](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent), inicie sesión con las credenciales de un administrador global y, después, acepte la solicitud.

- El usuario que configura el conector personalizado en el centro de cumplimiento de Microsoft 365 (en el paso 5) debe tener asignado el rol importación y exportación de buzones de correo en Exchange Online. Este rol no está asignado a ningún grupo de roles de Exchange Online de forma predeterminada. Puede Agregar el rol importación y exportación de buzones al grupo de funciones de administración de la organización en Exchange Online. O bien, puede crear un grupo de roles, asignar el rol de importación y exportación de buzones de correo y, a continuación, agregar los usuarios adecuados como miembros. Para obtener más información, vea las secciones  [crear grupos](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) de roles o [modificar grupos de roles](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) en el artículo sobre la administración de grupos de roles en Exchange Online.

## <a name="step-1-create-an-app-in-azure-active-directory"></a>Paso 1: crear una aplicación en Azure Active Directory

El primer paso es registrar una nueva aplicación en Azure Active Directory (AAD). Esta aplicación se corresponde con el recurso de la aplicación web que implementa en el paso 4 y el paso 5 para el conector de Facebook. 

Para obtener instrucciones paso a paso, consulte [crear una aplicación en Azure Active Directory](deploy-facebook-connector.md#step-1-create-an-app-in-azure-active-directory).

Al finalizar este paso (mediante las instrucciones paso a paso anteriores), guardará la siguiente información en un archivo de texto. Estos valores se usan en pasos posteriores del proceso de implementación.

- IDENTIFICADOR de la aplicación AAD

- Secreto de la aplicación AAD

- Identificador de inquilino

## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a>Paso 2: implementar el servicio Web del conector desde GitHub a su cuenta de Azure

El siguiente paso es implementar el código fuente de la aplicación de conector de páginas empresariales de Facebook que usará la API de Facebook para conectarse a su cuenta de Facebook y extraer los datos para que pueda importarlos a Microsoft 365. El conector de Facebook que implemente para su organización cargará los elementos de las páginas de empresa de Facebook en la ubicación de almacenamiento de Azure que se crea en este paso. Después de crear un conector de páginas empresariales de Facebook en el centro de cumplimiento de Microsoft 365 (en el paso 5), el servicio de importación copiará los datos de las páginas de negocio de Facebook desde la ubicación de Azure Storage a un buzón de la organización 365 de Microsoft. Como se explicó anteriormente en la sección [requisitos previos](#prerequisites-for-setting-up-a-connector-for-facebook-business-pages) , debe tener una suscripción de Azure válida para crear una cuenta de almacenamiento de Azure.

Para obtener instrucciones paso a paso, consulte [implementar el servicio Web del conector de github en su cuenta de Azure](deploy-facebook-connector.md#step-2-deploy-the-connector-web-service-from-github-to-your-azure-account).

En las instrucciones paso a paso para completar este paso, deberá proporcionar la siguiente información:

- APISecretKey: este secreto se crea durante la finalización de este paso. Se usa en el paso 5.

- TenantId: el identificador de inquilino de su organización de Microsoft 365 que copió después de crear la aplicación de conector de Facebook en Azure Active Directory en el paso 1.

Después de completar este paso, asegúrese de copiar la dirección URL de Azure App Service (por ejemplo, https://fbconnector.azurewebsites.net) . Debe usar esta dirección URL para completar los pasos 3, 4 y 5).

## <a name="step-3-register-the-web-app-on-facebook"></a>Paso 3: registrar la aplicación web en Facebook

El siguiente paso es crear y configurar una nueva aplicación en Facebook. El conector de páginas empresariales de Facebook que ha creado en el paso 5 usa la aplicación Web de Facebook para interactuar con la API de Facebook para obtener datos de las páginas de negocio de Facebook de su organización.

Para obtener instrucciones paso a paso, consulte [registrar la aplicación de Facebook](deploy-facebook-connector.md#step-3-register-the-facebook-app).

Al finalizar este paso (siguiendo las instrucciones paso a paso), guarde la siguiente información en un archivo de texto. Estos valores se usan para configurar la aplicación de conector de Facebook en el paso 4.

- IDENTIFICADOR de la aplicación de Facebook

- Secreto de la aplicación de Facebook

- Token de comprobación de webhooks de Facebook

## <a name="step-4-configure-the-facebook-connector-app"></a>Paso 4: configurar la aplicación de conector de Facebook

El siguiente paso es agregar opciones de configuración a la aplicación conector de Facebook que cargó cuando creó el recurso de Azure Web App en el paso 1. Para ello, vaya a la Página principal de la aplicación del conector y configure.

Para obtener instrucciones paso a paso, consulte [Configure The Facebook Connector App](archive-facebook-data-with-sample-connector.md#step-4-configure-the-facebook-connector-app).

Al finalizar este paso (siguiendo las instrucciones paso a paso), se proporciona la siguiente información (que se ha copiado a un archivo de texto después de completar los pasos anteriores):

- IDENTIFICADOR de la aplicación de Facebook (obtenido en el paso 3)

- Secreto de la aplicación de Facebook (obtenido en el paso 3)

- Token de comprobación de webhooks de Facebook (obtenido en el paso 3)

- IDENTIFICADOR de aplicación de Azure Active Directory (el identificador de la aplicación de AAD que se obtuvo en el paso 1)

- Secreto de la aplicación de Azure Active Directory (el secreto de la aplicación AAD obtenido en el paso 1)

## <a name="step-5-set-up-a-facebook-business-pages-connector-in-the-microsoft-365-compliance-center"></a>Paso 5: configurar un conector de páginas empresariales de Facebook en el centro de cumplimiento de Microsoft 365

El último paso consiste en configurar el conector en el centro de cumplimiento de Microsoft 365 que importará datos de las páginas de empresa de Facebook a un buzón específico en Microsoft 365. Después de completar este paso, el servicio de importación de Office 365 empezará a importar datos de las páginas de empresa de Facebook a Microsoft 365.

Para obtener instrucciones paso a paso, consulte [STEP 5: set up a Facebook Connector in the Microsoft 365 Compliance Center](deploy-facebook-connector.md#step-5-set-up-a-facebook-connector-in-the-microsoft-365-compliance-center). 

Al finalizar este paso (siguiendo las instrucciones paso a paso), proporciona la siguiente información (que ha copiado en un archivo de texto después de completar los pasos).

- IDENTIFICADOR de la aplicación AAD (obtenido en el paso 1)

- Dirección URL de Azure App Service (obtenida en el paso 1; por ejemplo, https://fbconnector.azurewebsites.net)

- APISecretKey (creado en el paso 2)
