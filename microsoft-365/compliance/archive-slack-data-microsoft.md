---
title: Archivar datos de eDiscovery de Slack en Microsoft 365 mediante un conector de datos proporcionado por Microsoft
description: Obtenga información sobre cómo configurar y usar un conector de datos de Slack eDiscovery proporcionado por Microsoft para importar y archivar datos de mensajería instantánea.
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 07/15/2022
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- tier3
- purview-compliance
- data-connectors
ms.openlocfilehash: 8c117a8410af9774adf992f3559b10cf02158c28
ms.sourcegitcommit: ab45f2963e0635ff2cb9670f6f7b4c784f6a250e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2022
ms.locfileid: "68811817"
---
# <a name="set-up-a-connector-to-archive-slack-ediscovery-data-preview"></a>Configuración de un conector para archivar datos de Slack eDiscovery (versión preliminar)

El conector de datos de Slack eDiscovery proporcionado por Microsoft le ayuda a importar y archivar datos de mensajería instantánea (como mensajes, datos adjuntos, vínculos y revisiones) desde las áreas de trabajo de Slack de su organización a Microsoft 365. El conector de datos extrae datos de la API de Slack, los convierte a un formato de mensaje de correo electrónico y, a continuación, los importa a buzones de usuario en Microsoft 365. Una vez importados los datos de Slack, puede aplicar soluciones de cumplimiento, como suspensión por juicio, Microsoft Purview eDiscovery (Premium), cumplimiento de comunicaciones y configuración de retención al contenido de Slack. El uso de un conector de datos de Slack eDiscovery para importar y archivar datos en Microsoft 365 puede ayudar a su organización a cumplir las directivas gubernamentales y normativas.

Si desea participar en la versión preliminar, póngase en contacto con el equipo en dcfeedback@microsoft.com.

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="overview-of-archiving-slack-ediscovery-data"></a>Información general sobre el archivado de datos de eDiscovery de Slack

En la información general siguiente se explica el proceso de uso de un conector de datos de Microsoft para archivar los datos de Slack en Microsoft 365.

![Flujo de trabajo de archivado de eDiscovery de Slack.](../media/SlackMSFTConnectorWorkflow.png)

1. Su organización trabaja con Slack para configurar y configurar un área de trabajo de Slack.

2. Una vez configurado el conector de datos, los mensajes de las áreas de trabajo de Slack de la organización se copian en los buzones de usuario de Microsoft 365. El conector de datos también convierte el contenido de un mensaje de chat en un formato de mensaje de correo electrónico.

3. El conector importa los mensajes de chat convertidos a los buzones de correo de usuarios específicos. Se crea una subcarpeta en la carpeta Bandeja de entrada denominada **Slack eDiscovery** en los buzones de usuario y los elementos de mensaje de chat se importan a esa carpeta.

## <a name="before-you-set-up-a-connector"></a>Antes de configurar un conector

- Su organización necesita la suscripción de Enterprise Grid para Slack. Para obtener más información, consulte [Suscripciones y características de Slack](https://slack.com/intl/en-gb/help/articles/115003205446-Slack-subscriptions-and-features-).

- Al usuario que crea el conector de datos se le debe asignar el rol de aplicación **Propietarios** de la organización en su organización de Slack. Para obtener más información, consulte [Tipos de roles en Slack](https://slack.com/intl/en-gb/help/articles/360018112273-Types-of-roles-in-Slack).

- Obtenga el nombre de usuario y la contraseña de la cuenta empresarial de Slack de su organización. Estas credenciales se usan para iniciar sesión en esta cuenta al crear el conector de datos. También se recomienda que haya configurado el aprovisionamiento de usuarios automatizado en su organización de Slack para usar el inicio de sesión único (SSO). [Roles en el Centro de cumplimiento de & de seguridad](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-defender-and-compliance-portals)

- Al usuario que crea el conector de Slack eDiscovery se le debe asignar el rol Administración Conector de datos. Este rol es necesario para agregar conectores en la página **Conectores de datos** de la portal de cumplimiento Microsoft Purview. Este rol se agrega de forma predeterminada a varios grupos de roles. Para obtener una lista de estos grupos de roles, consulte la sección "Roles en los portales de defender y cumplimiento" de [Roles y grupos de roles en los portales de cumplimiento de Microsoft 365 Defender y Microsoft Purview](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-defender-and-compliance-portals). Como alternativa, un administrador de su organización puede crear un grupo de roles personalizado, asignar el rol Administración conector de datos y, a continuación, agregar los usuarios adecuados como miembros. Para obtener instrucciones, consulte la sección "Crear un grupo de roles personalizado" en [Permisos en el portal de cumplimiento Microsoft Purview](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group).

## <a name="step-1-create-a-slack-ediscovery-connector"></a>Paso 1: Crear un conector de eDiscovery de Slack

1. Vaya a <https://compliance.microsoft.com> y seleccione **Conectores de datos** en el panel de navegación izquierdo.

2. En la pestaña **Información general** , seleccione **Filtrar** y seleccione **Por Microsoft** y, a continuación, aplique el filtro.

3. Seleccione **Slack eDiscovery (versión preliminar).**

4. En la página de descripción **del producto Slack eDiscovery (versión preliminar),** seleccione **Agregar conector**.

5. En la página **Asistente para términos de servicio** , seleccione **Aceptar**.

6. Escriba un nombre único que identifique el conector y, a continuación, seleccione **Siguiente**. El nombre que escriba identificará el conector en la página **Conectores de datos** después de crearlo.

## <a name="step-2-sign-into-your-slack-organization"></a>Paso 2: Iniciar sesión en su organización de Slack

1. En la página **Iniciar sesión en** el asistente de Slack, seleccione **Iniciar sesión en Slack** para iniciar sesión en el área de trabajo de Slack de su organización.

2. En la página **Slack Sign into your workspace (Iniciar sesión en el área de trabajo** ), escriba el nombre del área de trabajo desde la que desea archivar los datos y, a continuación, seleccione **Continuar**.

   Se muestra una página con el nombre del área de trabajo de Slack y un mensaje para iniciar sesión.

3. Seleccione el vínculo en la cadena **Los propietarios de la organización también pueden iniciar sesión aquí**.

4. En la página de inicio de sesión del área de trabajo, escriba la dirección de correo electrónico y la contraseña de la cuenta empresarial de Slack de su organización y, a continuación, seleccione **Iniciar sesión**.

   Después de iniciar sesión correctamente, se muestra una página que solicita permiso para acceder a la organización de Slack mediante la aplicación del conector.

5. Seleccione **Permitir** para permitir que la aplicación administre su organización.

   Después de seleccionar **Permitir**, se cierra la página slack y se muestra la página **Asignar usuarios de eDiscovery de Slack a usuarios de Microsoft 365** en el asistente del conector.

## <a name="step-3-specify-the-users-to-import-data-for"></a>Paso 3: Especificar los usuarios para los que se van a importar datos

Seleccione una de las siguientes opciones para especificar qué usuarios cuyos datos de eDiscovery de Slack desea importar.

- **Todos los usuarios de la organización**. Seleccione esta opción para importar datos para todos los usuarios.

- **Solo usuarios en suspensión por juicio**. Seleccione esta opción para importar datos solo para los usuarios cuyos buzones están en suspensión por juicio. Esta opción importa datos a buzones de usuario que tienen la propiedad LitigationHoldEnabled establecida en True. Para obtener más información, consulte [Creación de una suspensión por litigio](create-a-litigation-hold.md).

## <a name="step-4-map-users-and-select-data-types-to-import"></a>Paso 4: Asignar usuarios y seleccionar tipos de datos para importar

1. Configure una o ambas opciones para asignar usuarios de Slack a sus buzones de Microsoft 365.

   - **Asignación automática de usuarios**. Seleccione esta opción para asignar automáticamente nombres de usuario de Slack a buzones de Microsoft 365. El conector usa el valor de la propiedad *Email*, que contiene cada mensaje o elemento de Slack. Esta propiedad se rellena con una dirección de correo electrónico de cada participante del mensaje. Si el conector puede asociar las direcciones de correo electrónico a los usuarios de Microsoft 365 correspondientes, el elemento se importa al buzón de Microsoft 365 de esos usuarios. Para usar esta opción, debe tener el inicio de sesión único configurado para su organización de Slack.

   - **Asignación de usuarios personalizada**. También tiene la opción de usar la asignación de usuarios personalizada en lugar de (o además de) la asignación automática de usuarios. Con esta opción, debe crear y cargar un archivo CSV que asigne el identificador de miembro de Slack de los usuarios a su dirección de correo electrónico de Microsoft 365. Para ello, seleccione **Descargar plantilla de asignación CSV**, rellene el archivo CSV con el identificador de miembro de Slack y la dirección de correo electrónico de Microsoft 365 para todos los usuarios de su organización y, a continuación, seleccione y cargue el archivo CSV en el asistente. Asegúrese de no cambiar los encabezados de columna en el archivo CSV. Este es un ejemplo del archivo de asignación CSV:

     |**ExternalUserId**  | **O365UserMailbox**   |
     |:-------------------|:-----------------------|
     | U01MDTF0QV6        | alexjones@contoso.onmicrosoft.com |
     | U02MDTF1RW7| pilarp@contoso.onmicrosoft.com|
     | U03MDTF2SX8 | sarad@contoso.onmicrosoft.com|
     |||

   > [!TIP]
   > Los identificadores de miembro para los usuarios se pueden obtener seleccionando ... Botón Más en el perfil de un usuario y, a continuación, seleccione **Copiar identificador de miembro**. Como alternativa, puede usar el [método de API users.list](https://api.slack.com/methods/users.list) de Slack para obtener los identificadores de todos los miembros de un equipo de Slack.

   Si habilita la asignación automática de usuarios y proporciona un archivo de asignación personalizado, el conector examinará primero el archivo de asignación personalizado para asignar el usuario de Slack a un buzón de Microsoft 365. Si el conector no encuentra un usuario válido de Microsoft 365 que se corresponda con el usuario de Slack, el conector usará la propiedad *Email* del elemento de Slack. Si el conector no encuentra un usuario válido de Microsoft 365 en el archivo de asignación personalizado o en la propiedad *Email* del elemento de mensaje, el elemento no se importará.

2. En la página **Seleccionar tipos de datos para importar** el asistente, seleccione los tipos de datos de Slack que desea importar. Si desea importar mensajes de todos los canales, seleccione todas las opciones. De lo contrario, seleccione solo los tipos de datos que desea importar.

     Además de los mensajes de Slack, también puede especificar otros tipos de contenido de Slack para importar a Microsoft 365. 

3. Después de configurar los tipos de datos que se van a importar, seleccione **Siguiente**, revise la configuración del conector y, a continuación, seleccione **Finalizar** para crear el conector.

## <a name="step-5-monitor-the-slack-ediscovery-connector"></a>Paso 5: Supervisión del conector de Slack eDiscovery

Después de crear el conector de Slack eDiscovery, puede ver el estado del conector en el portal de cumplimiento.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com/) y seleccione **Conectores de datos** en el panel de navegación izquierdo.

2. Seleccione la pestaña **Conectores** y, a continuación, seleccione el conector **de Slack eDiscovery** para mostrar la página de control flotante, que contiene las propiedades y la información sobre el conector.

3. En **Estado del conector con origen**, seleccione el vínculo **Descargar registro** para abrir (o guardar) el registro de estado del conector. Este registro contiene información sobre los datos que se han importado a la nube de Microsoft. Para obtener más información, consulte [Visualización de registros de administración para conectores de datos](data-connector-admin-logs.md).

## <a name="known-issues"></a>Problemas conocidos

- En este momento, no se admiten la importación de datos adjuntos o elementos que superen los 10 MB. La compatibilidad con elementos más grandes estará disponible en una fecha posterior.
