---
title: Agregar otros proveedores de contenido para Aprendizaje Microsoft Viva
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: 10/27/2021
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: MET150
ms.collection:
- enabler-strategic
- m365initiative-viva-learning
localization_priority: medium
description: Obtenga información sobre cómo configurar otros proveedores de contenido como un origen de contenido de aprendizaje para Aprendizaje Microsoft Viva.
ms.openlocfilehash: 4f1a8810f6b8615baa7e8b3fcd8d945ca08cf1d5
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2021
ms.locfileid: "60668269"
---
# <a name="add-other-content-providers-for-microsoft-viva-learning"></a>Agregar otros proveedores de contenido para Aprendizaje Microsoft Viva

Un conjunto creciente de proveedores de contenido de aprendizaje están disponibles a través de Viva Learning. Este conjunto puede cambiar en cualquier momento a medida que más proveedores se unan o cambien su estado con el programa.

Algunos orígenes de aprendizaje estarán habilitados de forma predeterminada y estarán disponibles sin una licencia viva Learning premium. Estos orígenes de aprendizaje incluyen:

- LinkedIn Learning 125 cursos
- Microsoft Learn
- Microsoft 365 Formación

Los orígenes de contenido de terceros no están habilitados de forma predeterminada. Para habilitar estos orígenes, [](content-sources-365-admin-center.md#configure-settings-for-the-learning-content-sources) deberá agregarlos en el Centro de administración de Microsoft 365 y seguir las instrucciones específicas que se muestran en la tabla siguiente.

>[!NOTE]
>Necesitará una licencia de Premium para conectar orígenes de contenido externos, a excepción de los cursos Learning LinkedIn seleccionados. [Obtenga más información sobre las licencias](https://www.microsoft.com/microsoft-viva/learning).

>[!NOTE]
>Los usuarios de Viva Learning pueden tardar de 24 a 48 horas en ver el contenido de los orígenes habilitados en el portal de administración. También puede tardar entre 24 y 48 horas en ocultar contenido de los cursos de LinkedIn Learning, Microsoft Learn y Microsoft 365 de Viva Learning después de deshabilitarlos en el portal de administración.

|Proveedor de contenido  |Instrucciones de configuración  |
|---------|---------|
|Go1     |[Configurar Go1 como origen de contenido](configure-go1-content-source.md)         |
|Skillsoft     |[Configurar Skillsoft como origen de contenido](configure-skillsoft-content-source.md)         |
|Udemy   |[Configurar Udemy como origen de contenido](configure-udemy-content-source.md)         |
|edX    |Siga los pasos siguientes para agregar edX en su Centro de administración de Microsoft 365.    |
|Coursera    |Siga los pasos siguientes para agregar Coursera a su Centro de administración de Microsoft 365.    |
|Pluralsight    |Siga los pasos siguientes para agregar Pluralsight en su Centro de administración de Microsoft 365.    |
|Infosec    |Siga los pasos siguientes para agregar Infosec en su Centro de administración de Microsoft 365.    |
|Academia de Josh Bersin    |Siga los pasos siguientes para agregar La Academia de Josh Bersin en su Centro de administración de Microsoft 365.    |

1. Inicie sesión en su [Centro de administración de Microsoft 365](https://admin.microsoft.com).
2. Vaya a **Configuración** y, a continuación, **configuración de la organización**. Seleccione Viva Learning y habilite el proveedor de contenido o el sistema de administración de aprendizaje elegidos en el panel.
3. Rellene los detalles.
4. Seleccione **Guardar**.

>[!NOTE]
>Los proveedores de contenido disponibles están sujetos a cambios. Según la organización, es posible que tenga acceso a más proveedores de contenido de los que se enumeran aquí.

## <a name="content-ingestion-errors"></a>Errores de ingesta de contenido

Si experimenta algún error en el Centro de administración de Microsoft 365 durante la ingesta de contenido, consulte la tabla siguiente para ver los pasos siguientes. Tenga en cuenta que se trata de una lista exhaustiva y puede contener más códigos de error en el futuro.

|Proveedor de contenido |Código de error |Descripción del código de error |
|:----------------|:----------|:----------------------|
|Todos los proveedores |USR_ERROR_INVALID_RESOURCE_CREDENTIALS |Las credenciales de autenticación proporcionadas no son válidas. Asegúrese de escribir las credenciales correctas. Para obtener más información, póngase en contacto con el servicio de soporte al cliente de Microsoft. |
|Todos los proveedores |USR_ERROR_ACCESS_DENIED |Acceso denegado por el partner. Confirme que las credenciales que ha especificado son correctas o póngase en contacto con el equipo de soporte técnico del proveedor de contenido. |

## <a name="content-consumption-for-end-users"></a>Consumo de contenido para usuarios finales

Una vez que haya agregado un proveedor de contenido como origen de contenido desde el Centro de administración de Microsoft 365, el contenido del proveedor fluirá a la aplicación Viva Learning y será visible para los usuarios finales.

Una vez que un usuario elige reproducir un curso en Viva Learning, se le dirigirá a la página web del proveedor de contenido y tendrá que escribir las credenciales de inicio de sesión en la página de inicio de sesión del proveedor. [Obtenga más información sobre cómo consumir contenido con Viva Learning](https://support.microsoft.com/office/01bfed12-c327-41e0-a68f-7fa527dcc98a).
