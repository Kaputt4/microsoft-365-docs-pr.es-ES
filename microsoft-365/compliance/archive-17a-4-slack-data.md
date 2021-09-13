---
title: Configurar un conector para archivar datos de Slack en Microsoft 365
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
description: Obtenga información sobre cómo configurar y usar un conector de Slack DataParser de 17a-4 para importar y archivar datos de Slack en Microsoft 365.
ms.openlocfilehash: 0d94a86b32fbd7269b8fc9d6a47990c29278c5d2
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2021
ms.locfileid: "59193257"
---
# <a name="set-up-a-connector-to-archive-slack-data"></a>Configurar un conector para archivar datos de Slack

Use [DataParser de 17a-4 LLC](https://www.17a-4.com/slack-dataparser/) para importar y archivar datos desde la plataforma Slack a buzones de usuario de su Microsoft 365 organización. DataParser incluye un conector Slack configurado para capturar elementos de un origen de datos de terceros e importarlos a Microsoft 365. El conector Slack DataParser convierte los datos de Slack en un formato de mensaje de correo electrónico y, a continuación, importa esos elementos a buzones de usuario en Microsoft 365.

Una vez que los datos de Slack se almacenan en buzones de usuario, puede aplicar Microsoft 365 características de cumplimiento como retención por juicio, exhibición de documentos electrónicos, directivas de retención y etiquetas de retención y cumplimiento de comunicaciones. El uso de un conector de Slack para importar y archivar datos en Microsoft 365 puede ayudar a su organización a cumplir con las directivas gubernamentales y reglamentarias.

## <a name="overview-of-archiving-slack-data"></a>Información general sobre el archivado de datos de Slack

En la siguiente introducción se explica el proceso de uso de un conector de datos para archivar datos de Slack en Microsoft 365.

![Flujo de trabajo de archivado para datos de Slack de 17a-4.](../media/SlackDataParserConnectorWorkflow.png)

1. Su organización trabaja con 17a-4 para configurar y configurar Slack DataParser.

2. De forma regular, el DataParser recopila los elementos de Slack. DataParser también convierte el contenido de un mensaje en un formato de mensaje de correo electrónico.

3. El conector Slack DataParser que cree en el Centro de cumplimiento de Microsoft 365 se conecta a DataParser y transfiere los mensajes a una ubicación Azure Storage segura en la nube de Microsoft.

4. Se crea una subcarpeta en la carpeta Bandeja de entrada denominada **Slack DataParser** en los buzones de usuario y los elementos de Slack se importan a esa carpeta. El conector determina a qué buzón se importarán los elementos mediante el valor de la *propiedad Email.* Cada elemento de Slack contiene esta propiedad, que se rellena con la dirección de correo electrónico de cada participante.

## <a name="before-you-set-up-a-connector"></a>Antes de configurar un conector

- Crear una cuenta dataParser para conectores de Microsoft. Para ello, póngase en [contacto con 17a-4 LLC](https://www.17a-4.com/contact/). Debe iniciar sesión en esta cuenta al crear el conector en el paso 1.

- El usuario que crea el conector Slack DataParser en el paso 1 (y lo completa en el paso 3) debe estar asignado al rol Exportación de importación de buzones en Exchange Online. Este rol es necesario para agregar conectores en la **página Conectores de datos** de la Centro de cumplimiento de Microsoft 365. De forma predeterminada, este rol no se asigna a un grupo de roles en Exchange Online. Puede agregar el rol Exportación de importación de buzones al grupo de roles Administración de la organización en Exchange Online. O bien, puede crear un grupo de roles, asignar el rol Importación de buzones de correo Exportar y, a continuación, agregar los usuarios adecuados como miembros. Para obtener más información, vea [](/Exchange/permissions-exo/role-groups#modify-role-groups) las secciones [Crear](/Exchange/permissions-exo/role-groups#create-role-groups) grupos de roles o Modificar grupos de roles en el artículo "Administrar grupos de roles en Exchange Online".

## <a name="step-1-set-up-a-slack-dataparser-connector"></a>Paso 1: Configurar un conector de Slack DataParser

El primer paso es obtener acceso a la página Conectores de datos de la Centro de cumplimiento de Microsoft 365 y crear un conector de 17a-4 para datos de Slack.

1. Vaya a <https://compliance.microsoft.com> y, a continuación, haga clic en **Conectores de datos**  >  **Slack DataParser**.

2. En la página Descripción del producto **Slack DataParser,** haga clic **en Agregar conector**.

3. En la **página Términos de** servicio, haga clic **en Aceptar**.

4. Escriba un nombre único que identifique el conector y, a continuación, haga clic en **Siguiente**.

5. Inicie sesión en su cuenta de 17a-4 y complete los pasos del Asistente para la conexión de Slack DataParser.

## <a name="step-2-configure-the-slack-dataparser-connector"></a>Paso 2: Configurar el conector Slack DataParser

Trabaje con la compatibilidad de 17a-4 para configurar el conector Slack DataParser.

## <a name="step-3-map-users"></a>Paso 3: Asignar usuarios

El conector Slack DataParser asignará automáticamente a los usuarios a sus Microsoft 365 de correo electrónico antes de importar datos a Microsoft 365.

## <a name="step-4-monitor-the-slack-dataparser-connector"></a>Paso 4: Supervisar el conector Slack DataParser

Después de crear un conector Slack DataParser, puede ver el estado del conector en el Centro de cumplimiento de Microsoft 365.

1. Vaya a <https://compliance.microsoft.com> y haga clic en **Conectores de datos** en la navegación izquierda.

2. Haga **clic** en la pestaña Conectores y, a continuación, seleccione el conector Slack DataParser que creó para mostrar la página desplegable, que contiene las propiedades y la información sobre el conector.

3. En **Estado del conector con origen,** haga clic en el vínculo Descargar **registro** para abrir (o guardar) el registro de estado del conector. Este registro contiene datos que se han importado a la nube de Microsoft.

## <a name="known-issues"></a>Problemas conocidos

En este momento, no se admite la importación de datos adjuntos o elementos de más de 10 MB. La compatibilidad con elementos más grandes estará disponible en una fecha posterior.
