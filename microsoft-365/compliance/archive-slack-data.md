---
title: Configurar un conector para archivar datos de eDiscovery de demora en Microsoft 365
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
description: Los administradores pueden configurar un conector para importar y archivar datos de la exhibición de documentos electrónicos de Globanet de demora en Microsoft 365. Este conector le permite archivar datos de orígenes de datos de terceros en Microsoft 365. Después de archivar estos datos, puede usar las características de cumplimiento, como directivas de retención legal, búsqueda de contenido y retención para administrar datos de terceros.
ms.openlocfilehash: 70230b12c33b0aec6a80b5b8e5349026c3ef9916
ms.sourcegitcommit: 3c39866865c8c61bce2169818d8551da65033cfe
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2020
ms.locfileid: "48816593"
---
# <a name="set-up-a-connector-to-archive-slack-ediscovery-data"></a>Configurar un conector para archivar datos de eDiscovery de demora

Use un conector de Globanet en el centro de cumplimiento de Microsoft 365 para importar y archivar datos de terceros desde plataformas de medios sociales, mensajería instantánea y colaboración de documentos a los buzones de la organización 365 de Microsoft. Globanet proporciona un conector de [demora](https://globanet.com/slack/) que está configurado para capturar elementos del origen de datos de terceros (de forma regular) y, a continuación, importar dichos elementos a Microsoft 365. El margen de demora extrae mensajes y archivos de la API de demora y los convierte a un formato de mensaje de correo electrónico y, a continuación, importa el elemento a los buzones de usuario.

Tras el margen de demora los datos de eDiscovery se almacenan en buzones de usuario, puede aplicar características de cumplimiento de Microsoft 365, como retención por juicio, eDiscovery, directivas de retención y etiquetas de retención y cumplimiento de la comunicación. El uso de un conector de margen de demora para importar y archivar datos en Microsoft 365 puede ayudar a su organización a cumplir las directivas gubernamentales y regulatorias.

## <a name="overview-of-archiving-slack-ediscovery-data"></a>Información general sobre el margen de archivado datos de eDiscovery

En la siguiente introducción se explica el proceso de uso de un conector para archivar la información de demora en Microsoft 365.

![Flujo de trabajo de archivado de margen de demora](../media/SlackConnectorWorkflow.png)

1. Su organización trabaja con la demora para configurar y configurar un sitio de margen de demora.

2. Una vez cada 24 horas, los mensajes de chat de la exhibición de documentos electrónicos de demora se copian en el sitio de Merge1 de Globanet. El conector también convierte el contenido de un mensaje de chat en un formato de mensaje de correo electrónico.

3. El conector eDiscovery de demora que crea en el centro de cumplimiento de Microsoft 365, se conecta al sitio de Globanet Merge1 todos los días y transfiere los mensajes de chat a una ubicación de almacenamiento seguro de Azure en la nube de Microsoft.

4. El conector importa los elementos de mensaje de chat convertidos a los buzones de usuarios específicos usando el valor de la propiedad *email* y la asignación automática de usuarios, como se describe en el paso 3. En los buzones de usuario se crea una subcarpeta nueva en la carpeta Bandeja de entrada con el nombre **eDiscovery** , y los elementos de mensajes de chat se importan a esa carpeta. El conector determina a qué buzón se importarán los elementos mediante el valor de la propiedad *email* . Todos los mensajes de chat contienen esta propiedad, que se rellena con la dirección de correo electrónico de cada participante del mensaje de chat.

## <a name="before-you-begin"></a>Antes de empezar

- Cree una cuenta de Globanet Merge1 para Microsoft Connectors. Para crear una cuenta, póngase en contacto [con el soporte técnico de Globanet](https://globanet.com/ms-connectors-contact). Iniciará sesión en esta cuenta cuando cree el conector en el paso 1.

- Obtenga el nombre de usuario y la contraseña de la cuenta de empresa del margen de demora de su organización. Deberá iniciar sesión en esta cuenta en el paso 2 cuando configure el margen de demora.

- El usuario que crea el conector eDiscovery de demora en el paso 1 (y lo completa en el paso 3) debe asignarse a la función importación y exportación de buzones de correo en Exchange Online. Este rol es necesario para agregar conectores en la página **conectores de datos** del centro de cumplimiento de Microsoft 365. De forma predeterminada, este rol no está asignado a un grupo de roles en Exchange Online. Puede Agregar el rol importación y exportación de buzones al grupo de funciones de administración de la organización en Exchange Online. O bien, puede crear un grupo de roles, asignar el rol de importación y exportación de buzones de correo y, a continuación, agregar los usuarios adecuados como miembros. Para obtener más información, vea las secciones [crear grupos](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) de roles o [modificar grupos de roles](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) en el artículo sobre la administración de grupos de roles en Exchange Online.

## <a name="step-1-set-up-the-slack-ediscovery-connector"></a>Paso 1: configurar el conector de eDiscovery de demora

El primer paso es obtener acceso a la página **conectores de datos** en el centro de cumplimiento de Microsoft 365 y crear un conector para los datos de demora.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com/) y haga clic en eDiscovery de demora de conectores de **datos**  >  **Slack eDiscovery** .

2. En la página Descripción del producto de **eDiscovery de demora** , haga clic en **Agregar conector** .

3. En la página **condiciones de servicio** , haga clic en **Aceptar** .

4. Escriba un nombre único que identifique el conector y, a continuación, haga clic en **siguiente** .

5. Inicie sesión en su cuenta de Merge1 para configurar el conector.

## <a name="step-2-configure-slack-ediscovery"></a>Paso 2: configurar la exhibición de documentos electrónicos de demora

El segundo paso consiste en configurar el conector eDiscovery de demora en el sitio de Merge1. Para obtener más información sobre cómo configurar el conector eDiscovery de demora en el sitio de Merge1 de Globanet, consulte [Merge1 guía del usuario de conectores de terceros](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Slack%20eDiscovery%20User%20Guide.pdf).

Después de hacer clic en **guardar & finalizar** , se muestra la página **asignación de usuarios** en el Asistente para conectores del centro de cumplimiento de Microsoft 365.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Paso 3: asignar usuarios y completar la configuración del conector

1. En la página **asignar usuarios externos a Microsoft 365 usuarios** , habilite la asignación automática de usuarios.

   Los elementos de eDiscovery de demora incluyen una propiedad denominada *email* , que contiene las direcciones de correo electrónico de los usuarios de la organización. Si el conector puede asociar esta dirección con un usuario de Microsoft 365, los elementos se importan al buzón de correo del usuario.

2. En la página **consentimiento del administrador** , haga clic en **proporcionar consentimiento** . Se le redirigirá al sitio de Microsoft. Haga clic en **Aceptar** para proporcionar el consentimiento.

   La organización debe permitir que el servicio de importación de Office 365 obtenga acceso a los datos de buzones de la organización. Para proporcionar el consentimiento del administrador, debe haber iniciado sesión con las credenciales de un administrador global de Microsoft 365 y aceptar la solicitud de consentimiento. Si no ha iniciado sesión como administrador global, puede ir a [esta página](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) e iniciar sesión con las credenciales de administrador global para aceptar la solicitud.

3. Haga clic en **siguiente** , revise la configuración y vaya a la página **conectores de datos** para ver el progreso del proceso de importación del nuevo conector.

## <a name="step-4-monitor-the-slack-ediscovery-connector"></a>Paso 4: supervisar el margen de demora del conector de exhibición de documentos electrónicos

Después de crear el conector eDiscovery de demora, puede ver el estado del conector en el centro de cumplimiento de Microsoft 365.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com) y haga clic en **conectores de datos** en el panel de navegación izquierdo.

2. Haga clic en la pestaña **conectores** y seleccione el conector **eDiscovery de demora** para mostrar la página de flotante. Esta página contiene las propiedades y la información sobre el conector.

3. En **Estado del conector con origen** , haga clic en el vínculo **Descargar registro** para abrir (o guardar) el registro de estado del conector. Este registro contiene información sobre los datos que se han importado a la nube de Microsoft.

## <a name="known-issues"></a>Problemas conocidos

- En este momento, no se admite la importación de datos adjuntos o elementos de más de 10 MB. La compatibilidad con elementos más grandes estará disponible en una fecha posterior.
