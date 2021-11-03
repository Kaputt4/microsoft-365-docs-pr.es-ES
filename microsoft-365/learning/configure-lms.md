---
title: Agregar sistemas de administración de aprendizaje para Aprendizaje Microsoft Viva
ms.author: daisyfeller
author: daisyfell
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: 11/01/2021
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: MET150
ms.collection:
- enabler-strategic
- m365initiative-viva-learning
localization_priority: medium
description: Obtenga información sobre cómo configurar los sistemas de administración de aprendizaje como un origen de contenido de aprendizaje para Aprendizaje Microsoft Viva.
ms.openlocfilehash: 84f2e0d50b36f7fe54d82db9fb5564dcbbcbe9fa
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2021
ms.locfileid: "60677273"
---
# <a name="add-learning-management-systems-for-microsoft-viva-learning"></a>Agregar sistemas de administración de aprendizaje para Aprendizaje Microsoft Viva

Un conjunto creciente de sistemas de administración de aprendizaje están disponibles a través de Viva Learning. Este conjunto puede cambiar en cualquier momento a medida que más proveedores se unan o cambien su estado con el programa.

Learning los sistemas de administración no están habilitados de forma predeterminada. Para habilitar estos orígenes, [](content-sources-365-admin-center.md#configure-settings-for-the-learning-content-sources) deberá agregarlos en el Centro de administración de Microsoft 365 y seguir las instrucciones específicas que se muestran en la tabla siguiente.

>[!NOTE]
>Necesitará una licencia de Premium para conectar sistemas de administración de aprendizaje. [Obtenga más información sobre las licencias](https://www.microsoft.com/microsoft-viva/learning).

>[!NOTE]
>Los usuarios de Viva Learning pueden tardar de 24 a 48 horas en ver el contenido de los orígenes habilitados en el portal de administración.

## <a name="learning-management-systems"></a>Learning de administración

|Learning de administración  |Instrucciones de configuración  |
|---------|---------|
|Cornerstone OnDemand |[Configurar Cornerstone OnDemand como origen de contenido](configure-cornerstone-content-source.md)         |
|Saba    |[Configurar Saba como origen de contenido](configure-saba-content-source.md)         |
|SAP SuccessFactors   |[Configurar SAP SuccessFactors como origen de contenido](configure-successfactors-content-source.md)         |

>[!NOTE]
>Los sistemas de administración de aprendizaje disponibles están sujetos a cambios. Según la organización, es posible que tenga acceso a diferentes sistemas de administración de aprendizaje de los que se enumeran aquí.

## <a name="content-ingestion-errors"></a>Errores de ingesta de contenido

Si experimenta algún error en el Centro de administración de Microsoft 365 durante la ingesta de contenido, consulte la tabla siguiente para ver los pasos siguientes. Tenga en cuenta que se trata de una lista exhaustiva y puede contener más códigos de error en el futuro.

|Learning de administración |Código de error |Descripción del código de error |
|:----------------|:----------|:----------------------|
|Todos los LMS |USR_ERROR_INVALID_RESOURCE_CREDENTIALS |Las credenciales de autenticación proporcionadas no son válidas. Asegúrese de escribir las credenciales correctas. Para obtener más información, póngase en contacto con el servicio de soporte al cliente de Microsoft. |
|Todos los LMS |USR_ERROR_ACCESS_DENIED |Acceso denegado por el partner. Confirme que las credenciales que ha especificado son correctas o póngase en contacto con el equipo de soporte técnico del proveedor de contenido. |
|SuccessFactors |USR_ERROR_SFTP_NO_FILES_FOUND |No hay contenido nuevo ingerido porque no había archivos presentes en el servidor SFTP de SuccessFactors. |
|SuccessFactors |USR_ERROR_SF_PACKAGE_NOT_FOUND |No se encontró ningún nuevo contenido ingerido como el paquete necesario en el servidor SFTP de SuccessFactors. |
|Cornerstone OnDemand |USR_ERROR_INVALID_RESOURCE_CREDENTIALS |Las credenciales de autenticación proporcionadas no son válidas. Asegúrese de que las credenciales se copian Aprendizaje Microsoft Viva en el portal de Cornerstone OnDemand. |

## <a name="content-consumption-for-end-users"></a>Consumo de contenido para usuarios finales

Una vez que haya agregado un sistema de administración de aprendizaje como origen de contenido desde el Centro de administración de Microsoft 365, el contenido del LMS fluirá a la aplicación Viva Learning y será visible para los usuarios finales.

Una vez que un usuario elige reproducir un curso en Viva Learning, se le dirigirá a la página web de LMS y tendrá que escribir las credenciales de inicio de sesión en la página de inicio de sesión de LMS. [Obtenga más información sobre cómo consumir contenido con Viva Learning](https://support.microsoft.com/office/01bfed12-c327-41e0-a68f-7fa527dcc98a).
