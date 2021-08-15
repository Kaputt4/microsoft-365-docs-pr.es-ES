---
title: Configurar un conector para archivar SQL datos en Microsoft 365
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
description: Obtenga información sobre cómo configurar y usar un conector DataParser de 17a-4 SQL para importar y archivar SQL datos en Microsoft 365.
ms.openlocfilehash: 6820400d215f2ed94f9741e877bee54c11ab746ebb0f6933840f3d5e9b3792dc
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "53872253"
---
# <a name="set-up-a-connector-to-archive-sql-data"></a>Configurar un conector para archivar SQL datos

Use [el SQL DataParser](https://www.17a-4.com/sql-dataparser/) de 17a-4 LLC para importar y archivar datos de una base de datos de SQL a buzones de usuario de su Microsoft 365 organización. DataParser incluye un conector SQL que está configurado para capturar elementos de un origen de datos de terceros e importar esos elementos a Microsoft 365. El SQL DataParser convierte los SQL a un formato de mensaje de correo electrónico y, a continuación, importa esos elementos a buzones de usuario en Microsoft 365.

Después SQL datos se almacenan en buzones de usuario, puede aplicar Microsoft 365 características de cumplimiento como retención por juicio, exhibición de documentos electrónicos, directivas de retención y etiquetas de retención y cumplimiento de comunicaciones. El uso de un SQL para importar y archivar datos en Microsoft 365 puede ayudar a su organización a cumplir con las directivas gubernamentales y reglamentarias.

## <a name="overview-of-archiving-sql-data"></a>Información general sobre el archivado SQL datos

En la siguiente introducción se explica el proceso de uso de un conector de datos para archivar SQL datos en Microsoft 365.

![Flujo de trabajo de archivado SQL datos de 17a-4](../media/SQLDatabaseDataParserConnectorWorkflow.png)

1. Su organización funciona con 17a-4 para configurar y configurar el SQL DataParser.

2. El DataParser recopila SQL elementos de forma periódica. DataParser también convierte el contenido de un mensaje en un formato de mensaje de correo electrónico.

3. El SQL DataParser que crea en el Centro de cumplimiento de Microsoft 365 se conecta a DataParser y transfiere los mensajes a una ubicación de Azure Storage segura en la nube de Microsoft.

4. Una subcarpeta de la carpeta Bandeja de entrada denominada **SQL DataParser** se crea en los buzones de usuario y los elementos SQL se importan a esa carpeta. El conector determina a qué buzón se importarán los elementos mediante el valor de la *propiedad Email.* Cada SQL contiene esta propiedad, que se rellena con la dirección de correo electrónico de cada participante.

## <a name="before-you-set-up-a-connector"></a>Antes de configurar un conector

- Crear una cuenta dataParser para conectores de Microsoft. Para ello, póngase en [contacto con 17a-4 LLC](https://www.17a-4.com/contact/). Debe iniciar sesión en esta cuenta al crear el conector en el paso 1.

- El usuario que crea el conector dataParser de SQL en el paso 1 (y lo completa en el paso 3) debe asignarse al rol De exportación de importación de buzones en Exchange Online. Este rol es necesario para agregar conectores en la **página Conectores de datos** de la Centro de cumplimiento de Microsoft 365. De forma predeterminada, este rol no se asigna a un grupo de roles en Exchange Online. Puede agregar el rol Exportación de importación de buzones al grupo de roles Administración de la organización en Exchange Online. O bien, puede crear un grupo de roles, asignar el rol Importación de buzones de correo Exportar y, a continuación, agregar los usuarios adecuados como miembros. Para obtener más información, vea [](/Exchange/permissions-exo/role-groups#modify-role-groups) las secciones [Crear](/Exchange/permissions-exo/role-groups#create-role-groups) grupos de roles o Modificar grupos de roles en el artículo "Administrar grupos de roles en Exchange Online".

## <a name="step-1-set-up-a-sql-dataparser-connector"></a>Paso 1: Configurar un conector SQL DataParser

El primer paso es obtener acceso a la página Conectores de datos en el Centro de cumplimiento de Microsoft 365 y crear un conector de 17a-4 para SQL datos.

1. Vaya a y, a continuación, haga clic <https://compliance.microsoft.com> en   >  **Conectores SQL DataParser**.

2. En la página SQL descripción del **producto DataParser,** haga clic **en Agregar conector**.

3. En la **página Términos de** servicio, haga clic **en Aceptar**.

4. Escriba un nombre único que identifique el conector y, a continuación, haga clic en **Siguiente**.

5. Inicie sesión en su cuenta de 17a-4 y complete los pasos del asistente para la conexión SQL DataParser.

## <a name="step-2-configure-the-sql-dataparser-connector"></a>Paso 2: Configurar el conector SQL DataParser

Trabaje con la compatibilidad de 17a-4 para configurar el SQL DataParser.

## <a name="step-3-map-users"></a>Paso 3: Asignar usuarios

El SQL DataParser asigna automáticamente a los usuarios a sus direcciones Microsoft 365 de correo electrónico antes de importar datos a Microsoft 365.

## <a name="step-4-monitor-the-sql-dataparser-connector"></a>Paso 4: Supervisar el conector SQL DataParser

Después de crear un SQL DataParser, puede ver el estado del conector en el Centro de cumplimiento de Microsoft 365.

1. Vaya a <https://compliance.microsoft.com> y haga clic en **Conectores de datos** en la navegación izquierda.

2. Haga clic en la pestaña **Conectores** y, a continuación, seleccione el SQL DataParser que creó para mostrar la página desplegable, que contiene las propiedades y la información sobre el conector.

3. En **Estado del conector con origen,** haga clic en el vínculo Descargar **registro** para abrir (o guardar) el registro de estado del conector. Este registro contiene datos que se han importado a la nube de Microsoft.

## <a name="known-issues"></a>Problemas conocidos

En este momento, no se admite la importación de datos adjuntos o elementos de más de 10 MB. La compatibilidad con elementos más grandes estará disponible en una fecha posterior.
