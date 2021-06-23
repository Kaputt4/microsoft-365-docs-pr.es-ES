---
title: Configurar un conector para archivar datos de BlackBerry en Microsoft 365
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
ms.collection: M365-security-compliance
description: Obtenga información sobre cómo configurar y usar un conector BlackBerry DataParser de 17a-4 para importar y archivar datos de BlackBerry en Microsoft 365.
ms.openlocfilehash: 1e84a2c5273a503ccb5d88381e01160ae2abf3cd
ms.sourcegitcommit: 778103d20a2b4c43e524aa436775764d8d8d4c33
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2021
ms.locfileid: "53096484"
---
# <a name="set-up-a-connector-to-archive-blackberry-data-preview"></a>Configurar un conector para archivar datos de BlackBerry (versión preliminar)

Use [BlackBerry DataParser](https://www.17a-4.com/BlackBerry-dataparser/) de 17a-4 LLC para importar y archivar datos empresariales de BlackBerry en buzones de usuario de su Microsoft 365 organización. DataParser incluye un conector BlackBerry configurado para capturar elementos de un origen de datos de terceros e importar esos elementos a Microsoft 365. El conector DataParser de BlackBerry convierte los datos de BlackBerry en un formato de mensaje de correo electrónico y, a continuación, importa esos elementos a buzones de usuario en Microsoft 365.

Una vez que los datos de BlackBerry se almacenan en buzones de usuario, puede aplicar Microsoft 365 características de cumplimiento como retención por juicio, exhibición de documentos electrónicos, directivas de retención y etiquetas de retención y cumplimiento de comunicaciones. El uso de un conector BlackBerry para importar y archivar datos en Microsoft 365 puede ayudar a su organización a cumplir con las directivas gubernamentales y reglamentarias.

## <a name="overview-of-archiving-blackberry-data"></a>Información general sobre el archivado de datos de BlackBerry

En la siguiente introducción se explica el proceso de uso de un conector de datos para archivar datos de BlackBerry en Microsoft 365.

![Flujo de trabajo de archivado para datos de BlackBerry de 17a-4](../media/BlackBerryDataParserConnectorWorkflow.png)

1. Su organización trabaja con 17a-4 para configurar y configurar BlackBerry DataParser.

2. De forma regular, el DataParser recopila los elementos de BlackBerry. DataParser también convierte el contenido de un mensaje en un formato de mensaje de correo electrónico.

3. El conector DataParser de BlackBerry que cree en el Centro de cumplimiento de Microsoft 365 se conecta a DataParser y transfiere los mensajes a una ubicación Azure Storage segura en la nube de Microsoft.

4. Se crea una subcarpeta en la carpeta Bandeja de entrada denominada **BlackBerry DataParser** en los buzones de usuario y los elementos de BlackBerry se importan a esa carpeta. El conector determina a qué buzón se importarán los elementos mediante el valor de la *propiedad Email.* Cada elemento de BlackBerry contiene esta propiedad, que se rellena con la dirección de correo electrónico de cada participante.

## <a name="before-you-set-up-a-connector"></a>Antes de configurar un conector

- Crear una cuenta dataParser para conectores de Microsoft. Para ello, póngase en [contacto con 17a-4 LLC](https://www.17a-4.com/contact/). Debe iniciar sesión en esta cuenta al crear el conector en el paso 1.

- El usuario que crea el conector DataParser de BlackBerry en el paso 1 (y lo completa en el paso 3) debe estar asignado al rol De exportación de importación de buzones en Exchange Online. Este rol es necesario para agregar conectores en la **página Conectores de datos** de la Centro de cumplimiento de Microsoft 365. De forma predeterminada, este rol no se asigna a un grupo de roles en Exchange Online. Puede agregar el rol Exportación de importación de buzones al grupo de roles Administración de la organización en Exchange Online. O bien, puede crear un grupo de roles, asignar el rol Importación de buzones de correo Exportar y, a continuación, agregar los usuarios adecuados como miembros. Para obtener más información, vea [](/Exchange/permissions-exo/role-groups#modify-role-groups) las secciones [Crear](/Exchange/permissions-exo/role-groups#create-role-groups) grupos de roles o Modificar grupos de roles en el artículo "Administrar grupos de roles en Exchange Online".

## <a name="step-1-set-up-a-blackberry-dataparser-connector"></a>Paso 1: Configurar un conector DataParser de BlackBerry

El primer paso es obtener acceso a la página Conectores de datos de la Centro de cumplimiento de Microsoft 365 y crear un conector de 17a-4 para los datos de BlackBerry.

1. Vaya a <https://compliance.microsoft.com> y, a continuación, haga clic **en Conectores de datos**  >  **BlackBerry DataParser**.

2. En la página Descripción del producto **DataParser de BlackBerry,** haga clic **en Agregar conector**.

3. En la **página Términos de** servicio, haga clic **en Aceptar**.

4. Escriba un nombre único que identifique el conector y, a continuación, haga clic en **Siguiente**.

5. Inicie sesión en su cuenta de 17a-4 y complete los pasos del Asistente para la conexión de BlackBerry DataParser.

## <a name="step-2-configure-the-blackberry-dataparser-connector"></a>Paso 2: Configurar el conector DataParser de BlackBerry

Trabaje con la compatibilidad de 17a-4 para configurar el conector DataParser de BlackBerry.

## <a name="step-3-map-users"></a>Paso 3: Asignar usuarios

El conector DataParser de BlackBerry asignará automáticamente a los usuarios a sus Microsoft 365 de correo electrónico antes de importar datos a Microsoft 365.

## <a name="step-4-monitor-the-blackberry-dataparser-connector"></a>Paso 4: Supervisar el conector DataParser de BlackBerry

Después de crear un conector DataParser de BlackBerry, puede ver el estado del conector en el Centro de cumplimiento de Microsoft 365.

1. Vaya a <https://compliance.microsoft.com> y haga clic en **Conectores de datos** en la navegación izquierda.

2. Haga **clic** en la pestaña Conectores y, a continuación, seleccione el conector DataParser de BlackBerry que creó para mostrar la página desplegable, que contiene las propiedades y la información sobre el conector.

3. En **Estado del conector con origen,** haga clic en el vínculo Descargar **registro** para abrir (o guardar) el registro de estado del conector. Este registro contiene datos que se han importado a la nube de Microsoft.

## <a name="known-issues"></a>Problemas conocidos

En este momento, no se admite la importación de datos adjuntos o elementos de más de 10 MB. La compatibilidad con elementos más grandes estará disponible en una fecha posterior.