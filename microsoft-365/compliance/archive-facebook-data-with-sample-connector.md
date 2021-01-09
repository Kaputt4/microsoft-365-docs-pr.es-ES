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
description: Obtenga información sobre cómo configurar & un conector en el Centro de cumplimiento de Microsoft 365 para importar datos de archivo de & de las páginas de Facebook Business a Microsoft 365.
ms.openlocfilehash: df86897defa92788399f704c53c00ebb9e4f4269
ms.sourcegitcommit: 7d4aa58ae9fc893825b6e648fa3f072c3ac59628
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2021
ms.locfileid: "49790154"
---
# <a name="set-up-a-connector-to-archive-facebook-data-preview"></a>Configurar un conector para archivar datos de Facebook (versión preliminar)

Use un conector en el Centro de cumplimiento de Microsoft 365 para importar y archivar datos de páginas empresariales de Facebook a Microsoft 365. Después de configurar y configurar el conector, se conecta a la página De Facebook Empresa (de forma programada), convierte el contenido de los elementos de Facebook en un formato de mensaje de correo electrónico y, a continuación, importa esos elementos a un buzón de Microsoft 365.

Después de importar los datos de Facebook, puede aplicar las características de cumplimiento de Microsoft 365, como retención por juicio, búsqueda de contenido, archivado de In-Place, auditoría, cumplimiento de comunicaciones y directivas de retención de Microsoft 365 a los datos de Facebook. Por ejemplo, cuando un buzón se coloca en retención por juicio o se asigna a una directiva de retención, se conservan los datos de Facebook. Puede buscar datos de terceros mediante la búsqueda de contenido o asociar el buzón donde se almacenan los datos de Facebook con un administrador en un caso de eDiscovery avanzado. El uso de un conector para importar y archivar datos de Facebook en Microsoft 365 puede ayudar a su organización a cumplir con las directivas gubernamentales y reglamentarias.

## <a name="prerequisites-for-setting-up-a-connector-for-facebook-business-pages"></a>Requisitos previos para configurar un conector para páginas empresariales de Facebook

Complete los siguientes requisitos previos antes de poder configurar un conector en el Centro de cumplimiento de Microsoft 365 para importar y archivar datos de las páginas de Facebook Business de su organización. 

- Necesita una cuenta de Facebook para las páginas empresariales de su organización (debe iniciar sesión en esta cuenta al configurar el conector). Actualmente, solo puede archivar datos de páginas de Facebook Business; no puede archivar datos de perfiles individuales de Facebook.

- Su organización debe tener una suscripción válida de Azure. Si no tiene una suscripción de Azure existente, puede registrarse para obtener una de estas opciones:

    - [Registrarse para obtener una suscripción gratuita de Azure de un año](https://azure.microsoft.com/free)

    - [Registrarse para obtener una suscripción de Azure de pago por uso](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/)

    > [!NOTE]
    > La suscripción gratuita de [Azure Active Directory](use-your-free-azure-ad-subscription-in-office-365.md) que se incluye con su suscripción de Microsoft 365 no admite los conectores en el Centro de seguridad & cumplimiento.

- El conector para páginas de Facebook Business puede importar un total de 200 000 elementos en un solo día. Si hay más de 200 000 elementos de Facebook Business en un día, ninguno de esos elementos se importará a Microsoft 365.

- El usuario que configura el conector personalizado en el Centro de cumplimiento de Microsoft 365 (en el paso 5) debe tener asignado el rol de importación y exportación de buzones en Exchange Online. Este rol no está asignado a ningún grupo de roles de Exchange Online de forma predeterminada. Puede agregar el rol De importación y exportación de buzones al grupo de roles Administración de la organización en Exchange Online. O bien, puede crear un grupo de roles, asignar el rol de importación y exportación de buzones de correo y, a continuación, agregar los usuarios adecuados como miembros. Para obtener más información, vea [](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) las secciones Crear grupos de [roles](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) o Modificar grupos de roles en el artículo "Administrar grupos de roles en Exchange Online".

## <a name="step-1-create-an-app-in-azure-active-directory"></a>Paso 1: Crear una aplicación en Azure Active Directory

El primer paso es registrar una nueva aplicación en Azure Active Directory (AAD). Esta aplicación corresponde al recurso de aplicación web que implementa en los pasos 4 y 5 para el conector de Facebook. 

Para obtener instrucciones paso a paso, consulte [Crear una aplicación en Azure Active Directory.](deploy-facebook-connector.md#step-1-create-an-app-in-azure-active-directory)

Durante la finalización de este paso (mediante las instrucciones paso a paso anteriores), guardará la siguiente información en un archivo de texto. Estos valores se usan en pasos posteriores del proceso de implementación.

- Id. de aplicación de AAD

- Secreto de aplicación de AAD

- Id. de inquilino

## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a>Paso 2: Implementar el servicio web del conector desde GitHub en su cuenta de Azure

El siguiente paso es implementar el código fuente para la aplicación conector de páginas de Facebook Business que usará la API de Facebook para conectarse a su cuenta de Facebook y extraer datos para poder importarlos a Microsoft 365. El conector de Facebook que implemente para su organización cargará los elementos de las páginas de Facebook Business en la ubicación de Azure Storage que se crea en este paso. Después de crear un conector de páginas empresariales de Facebook en el Centro de cumplimiento de Microsoft 365 (en el paso 5), el servicio de importación copiará los datos de las páginas empresariales de Facebook desde la ubicación de Azure Storage a un buzón de correo de su organización de Microsoft 365. Como se explicó anteriormente en la sección [Requisitos previos,](#prerequisites-for-setting-up-a-connector-for-facebook-business-pages) debe tener una suscripción válida de Azure para crear una cuenta de Azure Storage.

Para obtener instrucciones paso a paso, vea Implementar el servicio web del conector [de GitHub en su cuenta de Azure.](deploy-facebook-connector.md#step-2-deploy-the-connector-web-service-from-github-to-your-azure-account)

En las instrucciones paso a paso para completar este paso, proporcionará la siguiente información:

- APISecretKey: este secreto se crea durante la finalización de este paso. Se usa en el paso 5.

- TenantId: id. de inquilino de la organización de Microsoft 365 que copió después de crear la aplicación conector de Facebook en Azure Active Directory en el paso 1.

Después de completar este paso, asegúrese de copiar la dirección URL del servicio de aplicaciones de Azure (por ejemplo, https://fbconnector.azurewebsites.net) . Debe usar esta dirección URL para completar los pasos 3, 4 y 5).

## <a name="step-3-register-the-web-app-on-facebook"></a>Paso 3: Registrar la aplicación web en Facebook

El siguiente paso es crear y configurar una nueva aplicación en Facebook. El conector de páginas empresariales de Facebook que crea en el paso 5 usa la aplicación web de Facebook para interactuar con la API de Facebook para obtener datos de las páginas empresariales de Facebook de su organización.

Para obtener instrucciones paso a paso, consulta [Registrar la aplicación de Facebook.](deploy-facebook-connector.md#step-3-register-the-facebook-app)

Durante la finalización de este paso (siguiendo las instrucciones paso a paso), se guarda la siguiente información en un archivo de texto. Estos valores se usan para configurar la aplicación conector de Facebook en el paso 4.

- Id. de aplicación de Facebook

- Secreto de aplicación de Facebook

- Token de comprobación de webhooks de Facebook

## <a name="step-4-configure-the-facebook-connector-app"></a>Paso 4: Configurar la aplicación conector de Facebook

El siguiente paso es agregar opciones de configuración a la aplicación conector de Facebook que carró al crear el recurso de aplicación web de Azure en el paso 1. Para ello, vaya a la página principal de la aplicación del conector y la configure.

Para obtener instrucciones paso a paso, vea [Configurar la aplicación del conector de Facebook.](archive-facebook-data-with-sample-connector.md#step-4-configure-the-facebook-connector-app)

Durante la finalización de este paso (siguiendo las instrucciones paso a paso), proporciona la siguiente información (que ha copiado en un archivo de texto después de completar los pasos anteriores):

- Id. de aplicación de Facebook (obtenido en el paso 3)

- Secreto de aplicación de Facebook (obtenido en el paso 3)

- Token de comprobación de webhooks de Facebook (obtenido en el paso 3)

- Identificador de aplicación de Azure Active Directory (el identificador de aplicación de AAD obtenido en el paso 1)

- Secreto de aplicación de Azure Active Directory (el secreto de aplicación de AAD obtenido en el paso 1)

## <a name="step-5-set-up-a-facebook-business-pages-connector-in-the-microsoft-365-compliance-center"></a>Paso 5: Configurar un conector de páginas de Facebook Business en el Centro de cumplimiento de Microsoft 365

El último paso es configurar el conector en el Centro de cumplimiento de Microsoft 365 que importará datos de las páginas de Facebook Business a un buzón especificado en Microsoft 365. Después de completar este paso, el servicio de importación de Microsoft 365 empezará a importar datos de sus páginas de Facebook Business a Microsoft 365.

Para obtener instrucciones paso a paso, consulte Paso 5: Configurar un conector de Facebook en el Centro de cumplimiento de [Microsoft 365.](deploy-facebook-connector.md#step-5-set-up-a-facebook-connector-in-the-microsoft-365-compliance-center) 

Durante la finalización de este paso (siguiendo las instrucciones paso a paso), proporciona la siguiente información (que ha copiado en un archivo de texto después de completar los pasos).

- Identificador de aplicación de AAD (obtenido en el paso 1)

- Dirección URL del servicio de aplicaciones de Azure (obtenida en el paso 1; por ejemplo, https://fbconnector.azurewebsites.net)

- APISecretKey (que creó en el paso 2)
