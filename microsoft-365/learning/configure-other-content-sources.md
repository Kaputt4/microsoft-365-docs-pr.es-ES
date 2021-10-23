---
title: Agregar otros proveedores de contenido para Aprendizaje Microsoft Viva
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: 10/22/2021
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-learning
localization_priority: medium
description: Obtenga información sobre cómo configurar otros proveedores como un origen de contenido de aprendizaje para Aprendizaje Microsoft Viva.
ROBOTS: NOINDEX
ms.openlocfilehash: 006b3e6690df253f80bc8e47d93264b9bf19ea0f
ms.sourcegitcommit: 3140e2866de36d57a27d27f70d47e8167c9cc907
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/23/2021
ms.locfileid: "60557274"
---
# <a name="add-other-content-providers-for-microsoft-viva-learning"></a>Agregar otros proveedores de contenido para Aprendizaje Microsoft Viva

Un conjunto creciente de proveedores de contenido de aprendizaje y sistemas de administración de aprendizaje están disponibles a través de Viva Learning. Este conjunto puede cambiar en cualquier momento a medida que más proveedores se unan o cambien su estado con el programa.

Los orígenes de contenido de terceros no están habilitados de forma predeterminada. Para habilitar estos orígenes, [](content-sources-365-admin-center.md#configure-settings-for-the-learning-content-sources) deberá agregarlos en el Centro de administración de Microsoft 365 y seguir las instrucciones específicas que se muestran en la tabla siguiente.

|Proveedor de contenido  |Instrucciones de configuración  |
|---------|---------|
|Cornerstone OnDemand |[Configurar Cornerstone OnDemand como origen de contenido](configure-cornerstone-content-source.md)         |
|Go1     |[Configurar Go1 como origen de contenido](configure-go1-content-source.md)         |
|Saba    |[Configurar Saba como origen de contenido](configure-saba-content-source.md)         |
|Skillsoft     |[Configurar Skillsoft como origen de contenido](configure-skillsoft-content-source.md)         |
|SAP SuccessFactors   |[Configurar SAP SuccessFactors como origen de contenido](configure-successfactors-content-source.md)         |
|Udemy   |[Configurar Udemy como origen de contenido](configure-udemy-content-source.md)         |

## <a name="content-ingestion-errors"></a>Errores de ingesta de contenido

Si experimenta algún error en el Centro de administración de Microsoft 365 durante la ingesta de contenido, consulte la tabla siguiente para ver los pasos siguientes. Tenga en cuenta que se trata de una lista exhaustiva y puede contener más códigos de error en el futuro.

|Proveedor de contenido |Código de error |Descripción del código de error |
|:----------------|:----------|:----------------------|
|Todos los proveedores |USR_ERROR_INVALID_RESOURCE_CREDENTIALS |Las credenciales de autenticación proporcionadas no son válidas. Asegúrese de escribir las credenciales correctas. Para obtener más información, póngase en contacto con el servicio de soporte al cliente de Microsoft. |
|Todos los proveedores |USR_ERROR_ACCESS_DENIED |Acceso denegado por el partner. Confirme que las credenciales que ha especificado son correctas o póngase en contacto con el equipo de soporte técnico del proveedor de contenido. |
|SuccessFactors |USR_ERROR_SFTP_NO_FILES_FOUND |No hay contenido nuevo ingerido porque no había archivos presentes en el servidor SFTP de SuccessFactors. |
|SuccessFactors |USR_ERROR_SF_PACKAGE_NOT_FOUND |No se encontró ningún nuevo contenido ingerido como el paquete necesario en el servidor SFTP de SuccessFactors. |
|Cornerstone OnDemand |USR_ERROR_INVALID_RESOURCE_CREDENTIALS |Las credenciales de autenticación proporcionadas no son válidas. Asegúrese de que las credenciales se copian desde Viva Learning App en el portal de Cornerstone OnDemand. |

## <a name="third-party-content-consumption"></a>Consumo de contenido de terceros

Una vez que haya agregado un proveedor de contenido de terceros como origen de contenido desde el Centro de administración de Microsoft 365, el contenido del proveedor fluirá a la aplicación Viva Learning y será visible para los usuarios finales.

Una vez que un usuario elige reproducir un curso en Viva Learning, se le dirigirá a la página web del proveedor de contenido y tendrá que escribir las credenciales de inicio de sesión en la página de inicio de sesión del proveedor. [Obtenga más información sobre cómo consumir contenido con Viva Learning](https://support.microsoft.com/office/viva-learning-preview-01bfed12-c327-41e0-a68f-7fa527dcc98a).
