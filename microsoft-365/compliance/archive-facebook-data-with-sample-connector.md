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
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: seo-marvel-apr2020
description: Obtenga información sobre cómo configurar & un conector en el Centro de cumplimiento de Microsoft 365 para importar datos & archivo de páginas de Facebook Empresa a Microsoft 365.
ms.openlocfilehash: f7cbc2b5a0f1ed55379224fc18b1be905e8a4cf0
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63319523"
---
# <a name="set-up-a-connector-to-archive-facebook-data-preview"></a>Configurar un conector para archivar datos de Facebook (versión preliminar)

Use un conector en el Centro de cumplimiento de Microsoft 365 importar y archivar datos de páginas de Facebook Empresa para Microsoft 365. Después de configurar y configurar el conector, se conecta a la página De Facebook Empresa (de forma programada), convierte el contenido de los elementos de Facebook en un formato de mensaje de correo electrónico y, a continuación, importa esos elementos a un buzón de correo de Microsoft 365.

Después de importar los datos de Facebook, puede aplicar Microsoft 365 características de cumplimiento como retención por juicio, búsqueda de contenido, archivado de In-Place, auditoría, cumplimiento de comunicaciones y directivas de retención de Microsoft 365 a los datos de Facebook. Por ejemplo, cuando un buzón se coloca en retención por juicio o se asigna a una directiva de retención, se conservan los datos de Facebook. Puede buscar datos de terceros mediante la búsqueda de contenido o asociar el buzón donde se almacenan los datos de Facebook con un custodio en un Advanced eDiscovery caso. El uso de un conector para importar y archivar datos de Facebook en Microsoft 365 puede ayudar a su organización a cumplir con las directivas gubernamentales y reglamentarias.

## <a name="prerequisites-for-setting-up-a-connector-for-facebook-business-pages"></a>Requisitos previos para configurar un conector para páginas de Facebook Empresa

Complete los siguientes requisitos previos antes de configurar y configurar un conector en el Centro de cumplimiento de Microsoft 365 importar y archivar datos de las páginas de Facebook Business de su organización. 

- Necesita una cuenta de Facebook para las páginas empresariales de su organización (debe iniciar sesión en esta cuenta al configurar el conector). Actualmente, solo puede archivar datos de páginas de Facebook Empresa; no puedes archivar datos de perfiles individuales de Facebook.

- Su organización debe tener una suscripción válida de Azure. Si no tiene una suscripción de Azure existente, puede registrarse en una de estas opciones:

    - [Registrarse para obtener una suscripción gratuita de Azure de un año](https://azure.microsoft.com/free)

    - [Registrarse para una suscripción de Azure de pago por uso](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/)

    > [!NOTE]
    > La [suscripción Azure Active Directory](use-your-free-azure-ad-subscription-in-office-365.md) gratuita que se incluye con la suscripción Microsoft 365 no admite los conectores de la Centro de cumplimiento de Microsoft 365.

- El conector para páginas de Facebook Empresa puede importar un total de 200 000 elementos en un solo día. Si hay más de 200 000 elementos de Facebook Business en un día, ninguno de esos elementos se importará a Microsoft 365.

- El usuario que configura el conector personalizado en el Centro de cumplimiento de Microsoft 365 (en el paso 5) debe tener asignado el rol de administrador del conector de datos. Este rol es necesario para agregar conectores en la **página Conectores de datos** de la Centro de cumplimiento de Microsoft 365. Este rol se agrega de forma predeterminada a varios grupos de roles. Para obtener una lista de estos grupos de roles, vea la sección "Roles en los centros de seguridad y cumplimiento" en Permisos en el [Centro de seguridad & cumplimiento](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center). Como alternativa, un administrador de la organización puede crear un grupo de roles personalizado, asignar el rol de administrador del conector de datos y, a continuación, agregar los usuarios adecuados como miembros. Para obtener instrucciones, vea la sección "Crear un grupo de roles personalizado" en [Permisos en el Centro de cumplimiento de Microsoft 365](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group).

## <a name="step-1-create-an-app-in-azure-active-directory"></a>Paso 1: Crear una aplicación en Azure Active Directory

El primer paso es registrar una nueva aplicación en Azure Active Directory (AAD). Esta aplicación corresponde al recurso de aplicación web que implementas en los pasos 4 y 5 para el conector de Facebook. 

Para obtener instrucciones paso a paso, consulta [Crear una aplicación en Azure Active Directory](deploy-facebook-connector.md#step-1-create-an-app-in-azure-active-directory).

Durante la finalización de este paso (mediante las instrucciones paso a paso anteriores), guardará la siguiente información en un archivo de texto. Estos valores se usan en pasos posteriores del proceso de implementación.

- AAD de aplicación

- AAD secreto de aplicación

- Identificador de inquilino

## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a>Paso 2: Implementar el servicio web del conector GitHub en su cuenta de Azure

El siguiente paso es implementar el código fuente de la aplicación conector de páginas de Facebook Empresa que usará la API de Facebook para conectarse a tu cuenta de Facebook y extraer datos para que puedas importarlo a Microsoft 365. El conector de Facebook que implemente para su organización cargará los elementos de las páginas de Facebook Empresa en la ubicación Azure Storage que se crea en este paso. Después de crear un conector de páginas empresariales de Facebook en el Centro de cumplimiento de Microsoft 365 (en el paso 5), el servicio de importación copiará los datos de las páginas empresariales de Facebook de la ubicación de Azure Storage en un buzón de correo de la organización Microsoft 365. Como se explicó anteriormente en la sección [Requisitos previos](#prerequisites-for-setting-up-a-connector-for-facebook-business-pages), debe tener una suscripción válida de Azure para crear una Azure Storage cuenta.

Para obtener instrucciones paso a paso, consulte [Deploy the connector web service from GitHub to your Azure account](deploy-facebook-connector.md#step-2-deploy-the-connector-web-service-from-github-to-your-azure-account).

En las instrucciones paso a paso para completar este paso, proporcionará la siguiente información:

- APISecretKey: este secreto se crea durante la finalización de este paso. Se usa en el paso 5.

- TenantId: el identificador de inquilino de la Microsoft 365 que copió después de crear la aplicación de conector de Facebook en Azure Active Directory en el paso 1.

Después de completar este paso, asegúrese de copiar la dirección URL del servicio de aplicaciones de Azure (por ejemplo, https://fbconnector.azurewebsites.net). Debe usar esta dirección URL para completar los pasos 3, 4 y 5).

## <a name="step-3-register-the-web-app-on-facebook"></a>Paso 3: Registrar la aplicación web en Facebook

El siguiente paso es crear y configurar una nueva aplicación en Facebook. El conector de páginas empresariales de Facebook que creas en el paso 5 usa la aplicación web de Facebook para interactuar con la API de Facebook para obtener datos de las páginas de Facebook Business de tu organización.

Para obtener instrucciones paso a paso, consulta [Registrar la aplicación de Facebook](deploy-facebook-connector.md#step-3-register-the-facebook-app).

Durante la finalización de este paso (siguiendo las instrucciones paso a paso), se guarda la siguiente información en un archivo de texto. Estos valores se usan para configurar la aplicación de conector de Facebook en el paso 4.

- Id. de aplicación de Facebook

- Secreto de aplicación de Facebook

- Webhooks de Facebook comprueban token

## <a name="step-4-configure-the-facebook-connector-app"></a>Paso 4: Configurar la aplicación conector de Facebook

El siguiente paso consiste en agregar opciones de configuración a la aplicación de conector de Facebook que ha cargado al crear el recurso de la aplicación web de Azure en el paso 1. Para ello, vaya a la página principal de la aplicación del conector y la configure.

Para obtener instrucciones paso a paso, consulta [Configurar la aplicación de conector de Facebook](archive-facebook-data-with-sample-connector.md#step-4-configure-the-facebook-connector-app).

Durante la finalización de este paso (siguiendo las instrucciones paso a paso), proporciona la siguiente información (que ha copiado en un archivo de texto después de completar los pasos anteriores):

- Id. de aplicación de Facebook (obtenido en el paso 3)

- Secreto de aplicación de Facebook (obtenido en el paso 3)

- Webhooks de Facebook comprueban el token (obtenido en el paso 3)

- Azure Active Directory de aplicación (el AAD de aplicación obtenido en el paso 1)

- Azure Active Directory secreto de aplicación (el secreto AAD de aplicación obtenido en el paso 1)

## <a name="step-5-set-up-a-facebook-business-pages-connector-in-the-microsoft-365-compliance-center"></a>Paso 5: Configurar un conector de páginas de Facebook Empresa en el Centro de cumplimiento de Microsoft 365

El último paso es configurar el conector en el Centro de cumplimiento de Microsoft 365 que importará datos de las páginas de Facebook Empresa a un buzón especificado en Microsoft 365. Después de completar este paso, el servicio Microsoft 365 importará datos de las páginas de Facebook Empresa a Microsoft 365.

Para obtener instrucciones paso a paso, consulta [Paso 5: Configurar un conector de Facebook en el Centro de cumplimiento de Microsoft 365](deploy-facebook-connector.md#step-5-set-up-a-facebook-connector-in-the-microsoft-365-compliance-center). 

Durante la finalización de este paso (siguiendo las instrucciones paso a paso), proporciona la siguiente información (que ha copiado en un archivo de texto después de completar los pasos).

- AAD de aplicación (obtenido en el paso 1)

- Dirección URL del servicio de aplicaciones de Azure (obtenida en el paso 1; por ejemplo, https://fbconnector.azurewebsites.net)

- APISecretKey (que creó en el paso 2)