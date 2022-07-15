---
title: Configurar un conector para archivar datos de Facebook
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
ms.date: 07/15/2022
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: seo-marvel-apr2020
description: Obtenga información sobre cómo configurar & usar un conector en el portal de cumplimiento Microsoft Purview para importar & datos de archivo de las páginas de Facebook Business a Microsoft 365.
ms.openlocfilehash: 79238bbbdcea71cf83342894d3b61e8047f5897a
ms.sourcegitcommit: 5e5c2c1f7c321b5eb1c5b932c03bdd510005de13
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/15/2022
ms.locfileid: "66822887"
---
# <a name="set-up-a-connector-to-archive-facebook-data-preview"></a>Configuración de un conector para archivar datos de Facebook (versión preliminar)

Use un conector en el portal de cumplimiento Microsoft Purview para importar y archivar datos de páginas de Facebook Business a Microsoft 365. Después de configurar y configurar el conector, se conecta a la página Facebook Business (de forma programada), convierte el contenido de los elementos de Facebook en un formato de mensaje de correo electrónico y, a continuación, importa esos elementos a un buzón de correo en Microsoft 365.

Una vez importados los datos de Facebook, puede aplicar las características de Microsoft Purview como suspensión por juicio, búsqueda de contenido, archivado de In-Place, auditoría, cumplimiento de comunicaciones y directivas de retención de Microsoft 365 a los datos de Facebook. Por ejemplo, cuando un buzón se coloca en suspensión por juicio o se asigna a una directiva de retención, se conservan los datos de Facebook. Puede buscar datos de terceros mediante Búsqueda de contenido o asociar el buzón donde se almacenan los datos de Facebook con un custodio en un caso de Microsoft Purview eDiscovery (Premium). El uso de un conector para importar y archivar datos de Facebook en Microsoft 365 puede ayudar a su organización a cumplir las directivas gubernamentales y normativas.

Si desea participar en la versión preliminar, póngase en contacto con el equipo en dcfeedback@microsoft.com.

## <a name="prerequisites-for-setting-up-a-connector-for-facebook-business-pages"></a>Requisitos previos para configurar un conector para páginas de Facebook Business

Complete los siguientes requisitos previos antes de configurar y configurar un conector en el portal de cumplimiento para importar y archivar datos desde las páginas de Facebook Business de su organización. 

- Necesita una cuenta de Facebook para las páginas empresariales de su organización (debe iniciar sesión en esta cuenta al configurar el conector). Actualmente, solo puede archivar datos de páginas de Facebook Business; no puede archivar datos de perfiles individuales de Facebook.

- La organización debe tener una suscripción de Azure válida. Si no tiene una suscripción de Azure existente, puede registrarse para obtener una de estas opciones:

    - [Registrarse para obtener una suscripción gratuita de Azure de un año](https://azure.microsoft.com/free)

    - [Registrarse para obtener una suscripción de Azure de pago por uso](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/)

    > [!NOTE]
    > La [suscripción gratuita de Azure Active Directory](use-your-free-azure-ad-subscription-in-office-365.md) que se incluye con la suscripción de Microsoft 365 no admite los conectores en el portal de cumplimiento.

- Las páginas del conector para empresas de Facebook pueden importar un total de 200 000 elementos en un solo día. Si hay más de 200 000 elementos de Facebook Business en un día, ninguno de esos elementos se importará a Microsoft 365.

- Al usuario que configura el conector personalizado en el portal de cumplimiento (en el paso 5) se le debe asignar el rol Administración Conector de datos. Este rol es necesario para agregar conectores en la página **Conectores de datos** del portal de cumplimiento. Este rol se agrega de forma predeterminada a varios grupos de roles. Para obtener una lista de estos grupos de roles, consulte la sección "Roles en los centros de seguridad y cumplimiento" de [Permisos en el Centro de cumplimiento de & seguridad](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center). Como alternativa, un administrador de su organización puede crear un grupo de roles personalizado, asignar el rol Administración conector de datos y, a continuación, agregar los usuarios adecuados como miembros. Para obtener instrucciones, consulte la sección "Crear un grupo de roles personalizado" en [Permisos en el portal de cumplimiento Microsoft Purview](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group).

## <a name="step-1-create-an-app-in-azure-active-directory"></a>Paso 1: Creación de una aplicación en Azure Active Directory

El primer paso es registrar una nueva aplicación en Azure Active Directory (AAD). Esta aplicación corresponde al recurso de aplicación web que implementa en los pasos 4 y 5 para el conector de Facebook.

Para obtener instrucciones paso a paso, consulte [Creación de una aplicación en Azure Active Directory](deploy-facebook-connector.md#step-1-create-an-app-in-azure-active-directory).

Durante la finalización de este paso (mediante las instrucciones paso a paso anteriores), guardará la siguiente información en un archivo de texto. Estos valores se usan en pasos posteriores en el proceso de implementación.

- Identificador de aplicación de AAD

- Secreto de aplicación de AAD

- Identificador de inquilino

## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a>Paso 2: Implementación del servicio web del conector desde GitHub en su cuenta de Azure

El siguiente paso consiste en implementar el código fuente de la aplicación conector de páginas empresariales de Facebook que usará la API de Facebook para conectarse a su cuenta de Facebook y extraer datos para que pueda importarlos a Microsoft 365. El conector de Facebook que implemente para su organización cargará los elementos de las páginas de Facebook Business en la ubicación de Azure Storage que se crea en este paso. Después de crear un conector de páginas empresariales de Facebook en el portal de cumplimiento (en el paso 5), el servicio de importación copiará los datos de las páginas empresariales de Facebook desde la ubicación de Azure Storage a un buzón de correo de la organización de Microsoft 365. Como se explicó anteriormente en la sección [Requisitos previos](#prerequisites-for-setting-up-a-connector-for-facebook-business-pages) , debe tener una suscripción de Azure válida para crear una cuenta de Azure Storage.

Para obtener instrucciones paso a paso, consulte [Implementación del servicio web del conector desde GitHub en su cuenta de Azure](deploy-facebook-connector.md#step-2-deploy-the-connector-web-service-from-github-to-your-azure-account).

En las instrucciones paso a paso para completar este paso, proporcionará la siguiente información:

- APISecretKey: este secreto se crea durante la finalización de este paso. Se usa en el paso 5.

- TenantId: el identificador de inquilino de la organización de Microsoft 365 que copió después de crear la aplicación del conector de Facebook en Azure Active Directory en el paso 1.

Después de completar este paso, asegúrese de copiar la dirección URL de Azure App Service (por ejemplo, https://fbconnector.azurewebsites.net). Debe usar esta dirección URL para completar los pasos 3, 4 y 5).

## <a name="step-3-register-the-web-app-on-facebook"></a>Paso 3: Registro de la aplicación web en Facebook

El siguiente paso es crear y configurar una nueva aplicación en Facebook. El conector de páginas empresariales de Facebook que crea en el paso 5 usa la aplicación web de Facebook para interactuar con la API de Facebook y obtener datos de las páginas de Facebook Business de su organización.

Para obtener instrucciones paso a paso, consulta [Registrar la aplicación de Facebook](deploy-facebook-connector.md#step-3-register-the-facebook-app).

Durante la finalización de este paso (siguiendo las instrucciones paso a paso), se guarda la siguiente información en un archivo de texto. Estos valores se usan para configurar la aplicación del conector de Facebook en el paso 4.

- Identificador de aplicación de Facebook

- Secreto de aplicación de Facebook

- Token de comprobación de webhooks de Facebook

## <a name="step-4-configure-the-facebook-connector-app"></a>Paso 4: Configurar la aplicación del conector de Facebook

El siguiente paso consiste en agregar la configuración a la aplicación del conector de Facebook que cargó al crear el recurso de aplicación web de Azure en el paso 1. Para ello, vaya a la página principal de la aplicación del conector y configurándola.

Para obtener instrucciones paso a paso, consulte [Configuración de la aplicación del conector de Facebook](archive-facebook-data-with-sample-connector.md#step-4-configure-the-facebook-connector-app).

Durante la finalización de este paso (siguiendo las instrucciones paso a paso), proporciona la siguiente información (que ha copiado en un archivo de texto después de completar los pasos anteriores):

- Id. de aplicación de Facebook (obtenido en el paso 3)

- Secreto de aplicación de Facebook (obtenido en el paso 3)

- Los webhooks de Facebook comprueban el token (obtenido en el paso 3)

- Identificador de aplicación de Azure Active Directory (el identificador de aplicación de AAD obtenido en el paso 1)

- Secreto de aplicación de Azure Active Directory (el secreto de aplicación de AAD obtenido en el paso 1)

## <a name="step-5-set-up-a-facebook-business-pages-connector-in-the-compliance-portal"></a>Paso 5: Configurar un conector de páginas empresariales de Facebook en el portal de cumplimiento

El último paso consiste en configurar el conector en el portal de cumplimiento que importará datos de las páginas de Facebook Business a un buzón especificado en Microsoft 365. Después de completar este paso, el servicio de importación de Microsoft 365 comenzará a importar datos de las páginas de Facebook Business a Microsoft 365.

Para obtener instrucciones paso a paso, consulte [Paso 5: Configurar un conector de Facebook en el portal de cumplimiento](deploy-facebook-connector.md#step-5-set-up-a-facebook-connector-in-the-compliance-portal).

Durante la finalización de este paso (siguiendo las instrucciones paso a paso), proporciona la siguiente información (que ha copiado en un archivo de texto después de completar los pasos).

- Id. de aplicación de AAD (obtenido en el paso 1)

- Dirección URL de Azure App Service (obtenida en el paso 1; por ejemplo, https://fbconnector.azurewebsites.net)

- APISecretKey (que creó en el paso 2)
