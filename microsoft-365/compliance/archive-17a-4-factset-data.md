---
title: Configuración de un conector para archivar datos de FactSet en Microsoft 365
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
description: Obtenga información sobre cómo configurar y usar un conector DataParser FactSet 17a-4 para importar y archivar datos factSet en Microsoft 365.
ms.openlocfilehash: e477545f157d4e175d4db12db6192fe40e2877d1
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "66636929"
---
# <a name="set-up-a-connector-to-archive-factset-data"></a>Configuración de un conector para archivar datos de FactSet

Use [FactSet DataParser](https://www.17a-4.com/factset-dataparser/) de 17a-4 LLC para importar y archivar datos de la plataforma FactSet a buzones de usuario de su organización de Microsoft 365. DataParser incluye un conector FactSet configurado para capturar elementos de un origen de datos de terceros e importarlos a Microsoft 365. El conector FactSet DataParser convierte los datos de FactSet en un formato de mensaje de correo electrónico y, a continuación, importa esos elementos a buzones de usuario en Microsoft 365.

Una vez que los datos de FactSet se almacenan en buzones de usuario, puede aplicar características de Microsoft Purview como suspensión por juicio, exhibición de documentos electrónicos, directivas de retención y etiquetas de retención y cumplimiento de la comunicación. El uso de un conector FactSet para importar y archivar datos en Microsoft 365 puede ayudar a su organización a cumplir las directivas gubernamentales y normativas.

## <a name="overview-of-archiving-factset-data"></a>Información general sobre el archivado de datos factSet

En la información general siguiente se explica el proceso de uso de un conector de datos para archivar datos factSet en Microsoft 365.

![Flujo de trabajo de archivado de datos factSet de 17a-4.](../media/FactSetDataParserConnectorWorkflow.png)

1. Su organización funciona con 17a-4 para configurar y configurar FactSet DataParser.

2. De forma periódica, DataParser recopila los elementos FactSet. DataParser también convierte el contenido de un mensaje en un formato de mensaje de correo electrónico.

3. El conector FactSet DataParser que se crea en el portal de cumplimiento Microsoft Purview se conecta a DataParser y transfiere los mensajes a una ubicación segura de Azure Storage en la nube de Microsoft.

4. Se crea una subcarpeta en la carpeta Bandeja de entrada denominada **FactSet DataParser en los buzones** de usuario y los elementos FactSet se importan a esa carpeta. El conector determina a qué buzón se van a importar elementos mediante el valor de la propiedad *Email* . Cada elemento FactSet contiene esta propiedad, que se rellena con la dirección de correo electrónico de cada participante.

## <a name="before-you-set-up-a-connector"></a>Antes de configurar un conector

- Cree una cuenta de DataParser para los conectores de Microsoft. Para ello, póngase en contacto con [17a-4 LLC](https://www.17a-4.com/contact/). Debe iniciar sesión en esta cuenta al crear el conector en el paso 1.

- Al usuario que crea el conector FactSet DataParser en el paso 1 (y lo completa en el paso 3) se le debe asignar el rol Administración Conector de datos. Este rol es necesario para agregar conectores en la página **Conectores de datos** del portal de cumplimiento. Este rol se agrega de forma predeterminada a varios grupos de roles. Para obtener una lista de estos grupos de roles, consulte la sección "Roles en los centros de seguridad y cumplimiento" de [Permisos en el Centro de cumplimiento de & seguridad](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center). Como alternativa, un administrador de su organización puede crear un grupo de roles personalizado, asignar el rol Administración conector de datos y, a continuación, agregar los usuarios adecuados como miembros. Para obtener instrucciones, consulte la sección "Crear un grupo de roles personalizado" en [Permisos en el portal de cumplimiento Microsoft Purview](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group).

- Este conector de datos 17a-4 está disponible en entornos GCC en la nube de Microsoft 365 US Government. Las aplicaciones y servicios de terceros pueden implicar almacenar, transmitir y procesar los datos de clientes de su organización en sistemas de terceros que están fuera de la infraestructura de Microsoft 365 y, por lo tanto, no están cubiertos por los compromisos de protección de datos y Microsoft Purview. Microsoft no hace ninguna representación de que el uso de este producto para conectarse a aplicaciones de terceros implica que esas aplicaciones de terceros son compatibles con FEDRAMP.

## <a name="step-1-set-up-a-factset-dataparser-connector"></a>Paso 1: Configurar un conector DataParser de FactSet

El primer paso consiste en acceder a la página Conectores de datos del portal de cumplimiento y crear un conector 17a-4 para los datos de FactSet.

1. Vaya a y, a <https://compliance.microsoft.com> continuación, haga clic en **Data connectors** > **FactSet DataParser**.

2. En la página de descripción del producto **FactSet DataParser** , haga clic en **Agregar conector**.

3. En la página **Términos de servicio** , haga clic en **Aceptar**.

4. Escriba un nombre único que identifique el conector y, a continuación, haga clic en **Siguiente**.

5. Inicie sesión en su cuenta 17a-4 y complete los pasos del Asistente para conexión de DataParser de FactSet.

## <a name="step-2-configure-the-factset-dataparser-connector"></a>Paso 2: Configuración del conector DataParser de FactSet

Trabaje con compatibilidad con 17a-4 para configurar el conector DataParser de FactSet.

## <a name="step-3-map-users"></a>Paso 3: Asignar usuarios

El conector FactSet DataParser asignará automáticamente los usuarios a sus direcciones de correo electrónico de Microsoft 365 antes de importar datos a Microsoft 365.

## <a name="step-4-monitor-the-factset-dataparser-connector"></a>Paso 4: Supervisión del conector DataParser de FactSet

Después de crear un conector DataParser de FactSet, puede ver el estado del conector en el portal de cumplimiento.

1. Vaya a <https://compliance.microsoft.com> y haga clic en **Conectores de datos** en el panel de navegación izquierdo.

2. Haga clic en la pestaña **Conectores** y, a continuación, seleccione el conector FactSet DataParser que creó para mostrar la página de control flotante, que contiene las propiedades y la información sobre el conector.

3. En **Estado del conector con origen**, haga clic en el vínculo **Descargar registro** para abrir (o guardar) el registro de estado del conector. Este registro contiene información sobre los datos que se han importado a la nube de Microsoft. Para obtener más información, consulte [Visualización de registros de administración para conectores de datos](data-connector-admin-logs.md).

## <a name="known-issues"></a>Problemas conocidos

En este momento, no se admiten la importación de datos adjuntos o elementos que superen los 10 MB. La compatibilidad con elementos más grandes estará disponible en una fecha posterior.
