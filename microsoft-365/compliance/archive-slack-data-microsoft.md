---
title: Archivar datos de exhibición de documentos electrónicos de Slack Microsoft 365 mediante un conector de datos proporcionado por Microsoft
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
description: Obtenga información sobre cómo configurar y usar un conector de datos de exhibición de documentos electrónicos de Slack proporcionado por Microsoft para importar y archivar datos de mensajería instantánea.
ms.openlocfilehash: 58401130726a7211eaad5b5c25985b534b68b0b8
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63312367"
---
# <a name="set-up-a-connector-to-archive-slack-ediscovery-data-preview"></a>Configurar un conector para archivar datos de exhibición de documentos electrónicos de Slack (versión preliminar)

El conector de datos de exhibición de documentos electrónicos de Slack proporcionado por Microsoft le ayuda a importar y archivar datos de mensajería instantánea (como mensajes, datos adjuntos, vínculos y revisiones) desde las áreas de trabajo de Slack de su organización a Microsoft 365. El conector de datos extrae datos de la API de Slack, los convierte en un formato de mensaje de correo electrónico y, a continuación, importa esos elementos a buzones de usuario en Microsoft 365. Después de importar los datos de Slack, puede aplicar soluciones de cumplimiento, como retención por juicio, Advanced eDiscovery, cumplimiento de comunicaciones y configuración de retención al contenido de Slack. El uso de un conector de datos de exhibición de documentos electrónicos de Slack para importar y archivar datos en Microsoft 365 puede ayudar a su organización a cumplir con las directivas gubernamentales y reglamentarias.

## <a name="overview-of-archiving-slack-ediscovery-data"></a>Información general sobre el archivado de datos de exhibición de documentos electrónicos de Slack

En la siguiente introducción se explica el proceso de uso de un conector de datos de Microsoft para archivar los datos de Slack en Microsoft 365.

![Flujo de trabajo de archivado de exhibición de documentos electrónicos de Slack.](../media/SlackMSFTConnectorWorkflow.png)

1. Su organización trabaja con Slack para configurar y configurar un área de trabajo de Slack.

2. Una vez configurado el conector de datos, los mensajes de las áreas de trabajo de Slack de la organización se copian en buzones de usuario en Microsoft 365. El conector de datos también convierte el contenido de un mensaje de chat a un formato de mensaje de correo electrónico.

3. El conector importa los mensajes de chat convertidos a los buzones de usuarios específicos. Se crea una subcarpeta en la carpeta Bandeja de entrada denominada Exhibición de documentos electrónicos **de Slack** en los buzones de usuario y los elementos del mensaje de chat se importan a esa carpeta.

## <a name="before-you-set-up-a-connector"></a>Antes de configurar un conector

- Su organización necesita la suscripción Enterprise Grid para Slack. Para obtener más información, consulta [Suscripciones y características de Slack](https://slack.com/intl/en-gb/help/articles/115003205446-Slack-subscriptions-and-features-).

- El usuario que crea el conector de datos debe tener asignado el rol de aplicación **Propietarios** de la organización en su organización Slack. Para obtener más información, consulta [Tipos de roles en Slack](https://slack.com/intl/en-gb/help/articles/360018112273-Types-of-roles-in-Slack).

- Obtenga el nombre de usuario y la contraseña de la cuenta de empresa de Slack de su organización. Estas credenciales se usan para iniciar sesión en esta cuenta al crear el conector de datos. También se recomienda que haya automatizado el aprovisionamiento de usuarios en la organización de Slack configurada para usar el inicio de sesión único (SSO). [Roles en el Centro de seguridad & cumplimiento](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center)

- El usuario que crea el conector de exhibición de documentos electrónicos de Slack debe tener asignado el rol de administrador del conector de datos. Este rol es necesario para agregar conectores en la **página Conectores de datos** de la Centro de cumplimiento de Microsoft 365. Este rol se agrega de forma predeterminada a varios grupos de roles. Para obtener una lista de estos grupos de roles, vea la sección "Roles en los centros de seguridad y cumplimiento" en Permisos en el [Centro de seguridad & cumplimiento](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center). Como alternativa, un administrador de la organización puede crear un grupo de roles personalizado, asignar el rol de administrador del conector de datos y, a continuación, agregar los usuarios adecuados como miembros. Para obtener instrucciones, vea la sección "Crear un grupo de roles personalizado" en [Permisos en el Centro de cumplimiento de Microsoft 365](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group).

## <a name="step-1-create-a-slack-ediscovery-connector"></a>Paso 1: Crear un conector de exhibición de documentos electrónicos de Slack

1. Vaya a y <https://compliance.microsoft.com> haga clic **en Conectores de datos** en el panel de navegación izquierdo.

2. En la **pestaña Información** general, haga clic **en Filtrar** y seleccione **Por Microsoft** y, a continuación, aplique el filtro.

3. Haga **clic en Exhibición de documentos electrónicos de Slack (versión preliminar).**

4. En la **página Descripción del producto de exhibición de documentos electrónicos de Slack (** versión preliminar), haga clic **en Agregar conector**.

5. En la página **Asistente para términos** de servicio, haga clic en **Aceptar**.

6. Escriba un nombre único que identifique el conector y, a continuación, haga clic en **Siguiente**. El nombre que escriba identificará el conector en la **página Conectores de** datos después de crearlo.

## <a name="step-2-sign-into-your-slack-organization"></a>Paso 2: Iniciar sesión en la organización de Slack

1. En la página **Asistente para iniciar sesión en Slack** , haga clic **en Iniciar sesión en Slack** para iniciar sesión en el área de trabajo de Slack de la organización.

2. En la página **Inicio de sesión de** Slack en el área de trabajo, escriba el nombre del área de trabajo desde la que desea archivar datos y, a continuación, haga clic en **Continuar**.

   Se muestra una página con el nombre del área de trabajo de Slack y un mensaje para iniciar sesión.

3. Haga clic en el vínculo de la cadena **Los propietarios de la organización también pueden iniciar sesión aquí**.

4. En la página de inicio de sesión del área de trabajo, escriba la dirección de correo electrónico y la contraseña de la cuenta empresarial de Slack de su organización y, a continuación, haga clic **en Iniciar sesión**.

   Después de iniciar sesión correctamente, se muestra una página que solicita permiso para acceder a la organización de Slack mediante la aplicación de conector.

5. Haz **clic en** Permitir para permitir que la aplicación administre tu organización.

   Después de hacer clic **en Permitir**, se cierra la página Slack y se muestra la página Asignar usuarios de exhibición de documentos electrónicos de **Slack Microsoft 365** usuarios en el asistente para conector.

## <a name="step-3-map-users-and-select-data-types-to-import"></a>Paso 3: Asignar usuarios y seleccionar tipos de datos para importar

1. Configure una o ambas de las siguientes opciones para asignar usuarios de Slack a sus Microsoft 365 de correo.

   - **Asignación automática de usuarios**. Seleccione esta opción para asignar automáticamente nombres de usuario de Slack a Microsoft 365 buzones de correo. El conector usa el valor de la *propiedad Email* , que contiene cada mensaje o elemento de Slack. Esta propiedad se rellena con una dirección de correo electrónico de cada participante del mensaje. Si el conector puede asociar las direcciones de correo electrónico con los usuarios Microsoft 365 correspondientes, el elemento se importa al buzón Microsoft 365 de esos usuarios. Para usar esta opción, debe tener sso configurado para la organización de Slack.

   - **Asignación de usuario personalizada**. También tiene la opción de usar la asignación de usuario personalizada en lugar de (o además de) la asignación automática de usuarios. Con esta opción, debe crear y cargar un archivo CSV que asigna el identificador de miembro de Slack de los usuarios a su Microsoft 365 de correo electrónico. Para ello, haga clic en Descargar plantilla de asignación **CSV**, rellene el archivo CSV con el identificador de miembro de Slack y una dirección de correo electrónico Microsoft 365 todos los usuarios de la organización y, a continuación, seleccione y cargue el archivo CSV en el asistente. Asegúrese de no cambiar los encabezados de columna en el archivo CSV. Este es un ejemplo del archivo de asignación CSV:

     |**ExternalUserId**  | **O365UserMailbox**   |
     |:-------------------|:-----------------------|
     | U01MDTF0QV6        | alexjones@contoso.onmicrosoft.com |
     | U02MDTF1RW7| pilarp@contoso.onmicrosoft.com|
     | U03MDTF2SX8 | sarad@contoso.onmicrosoft.com|
     |||

   > [!TIP]
   > Los IDs de miembros para los usuarios se pueden obtener haciendo clic en ... Botón Más en el perfil de un usuario y, a continuación, selecciona **Copiar id. de miembro**. Como alternativa, puedes usar el método [de la API de Slack users.list](https://api.slack.com/methods/users.list) para obtener los IDs de todos los miembros de un equipo de Slack.

   Si habilita la asignación automática de usuarios y proporciona un archivo de asignación personalizado, el conector primero buscará el archivo de asignación personalizado para asignar el usuario de Slack a un buzón Microsoft 365 usuario. Si el conector no encuentra un usuario Microsoft 365 válido que corresponda al usuario de Slack, el conector usará la propiedad *Email* del elemento Slack. Si el conector no encuentra un usuario Microsoft 365 válido en el archivo de asignación personalizado o en la propiedad *Email* del elemento de mensaje, el elemento no se importará.

2. En la **página Seleccionar tipos de datos para importar** el asistente, seleccione los tipos de datos de Slack que desea importar. Si desea importar mensajes de todos los canales, seleccione todas las opciones. De lo contrario, seleccione solo los tipos de datos que desea importar.

     Además de los mensajes de Slack, también puedes especificar otros tipos de contenido de Slack para importar a Microsoft 365. 

3. Después de configurar los tipos de datos que se importarán, haga clic en **Siguiente**, revise la configuración del conector y, a continuación, haga clic en **Finalizar para crear** el conector.

## <a name="step-4-monitor-the-slack-ediscovery-connector"></a>Paso 4: Supervisar el conector de exhibición de documentos electrónicos de Slack

Después de crear el conector de exhibición de documentos electrónicos de Slack, puede ver el estado del conector en el Centro de cumplimiento de Microsoft 365.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com/) y haga clic **en Conectores de datos** en la navegación izquierda.

2. Haga clic **en la pestaña Conectores** y, a continuación, seleccione el conector de exhibición de documentos electrónicos **de Slack** para mostrar la página desplegable, que contiene las propiedades e información sobre el conector.

3. En **Estado del conector con origen**, haga clic en el vínculo **Descargar registro** para abrir (o guardar) el registro de estado del conector. Este registro contiene datos que se han importado a la nube de Microsoft.

## <a name="known-issues"></a>Problemas conocidos

- En este momento, no se admite la importación de datos adjuntos o elementos de más de 10 MB. La compatibilidad con elementos más grandes estará disponible en una fecha posterior.
