---
title: Configurar un conector para archivar Cisco Jabber en datos de MS SQL en Microsoft 365
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
description: Los administradores pueden configurar un conector para importar y archivar datos de Cisco Jabber desde Globanet en Microsoft 365. Este conector le permite archivar datos de orígenes de datos de terceros en Microsoft 365 para poder usar las características de cumplimiento, como la retención legal, la búsqueda de contenido y las directivas de retención, para administrar los datos de terceros de su organización.
ms.openlocfilehash: c87449c35d588fd886d9d108f136eea0a4799ccf
ms.sourcegitcommit: ae3aa7f29be16d08950cf23cad489bc069aa8617
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2020
ms.locfileid: "48409220"
---
# <a name="set-up-a-connector-to-archive-cisco-jabber-data-preview"></a>Configurar un conector para archivar datos de Cisco Jabber (versión preliminar)

Use un conector de Globanet en el centro de cumplimiento de Microsoft 365 para importar y archivar datos desde la plataforma Jabber de Cisco a los buzones de usuario de la organización 365 de Microsoft. Globanet proporciona un conector de [Cisco Jabber](https://globanet.com/jabber/) que está configurado para capturar elementos de la base de datos de MS SQL del Jabber, como mensajes de chat de 1:1 y chats de grupo y, a continuación, importar dichos elementos a Microsoft 365. El conector recupera datos de la base de datos MS SQL de Cisco Jabber, los procesa y convierte el contenido de la cuenta Jabber de Cisco del usuario en un formato de mensaje de correo electrónico y, a continuación, importa dichos elementos en el buzón del usuario en Microsoft 365.

Una vez que los datos de Cisco Jabber se almacenan en buzones de usuario, puede aplicar características de cumplimiento de Microsoft 365 como retención por juicio, eDiscovery, directivas de retención y etiquetas de retención y cumplimiento de la comunicación. El uso de un conector de Cisco Jabber para importar y archivar datos en Microsoft 365 puede ayudar a su organización a cumplir con las directivas gubernamentales y regulatorias.

## <a name="overview-of-archiving-cisco-jabber-data"></a>Información general sobre el archivado de datos de Cisco Jabber

La siguiente descripción general explica el proceso de uso de un conector para archivar datos de Cisco Jabber en Microsoft 365.

![Flujo de trabajo de archivado para datos de Cisco Jabber](../media/CiscoJabberonMSSQLConnectorWorkflow.png)

1. Su organización trabaja con Cisco para configurar y configurar una Jabber? a de Cisco en base de datos MS SQL.

2. Una vez cada 24 horas, los elementos de Jabber de Cisco se copian desde la base de datos de MS SQL al sitio de Merge1 de Globanet. El conector también convierte el contenido de los mensajes de chat en un formato de mensaje de correo electrónico.

3. El conector Jabber de Cisco que se crea en el centro de cumplimiento de Microsoft 365 se conecta al sitio de Merge1 de Globanet todos los días y transfiere los elementos a una ubicación de almacenamiento seguro de Azure en la nube de Microsoft.

4. La asignación automática de usuarios como conector importa elementos a los buzones de usuarios específicos mediante el valor de la propiedad *email* del que se describe en el [paso 3](#step-3-map-users-and-complete-the-connector-setup). Se crea una subcarpeta en la carpeta Bandeja de entrada denominada **Cisco Jabber en MS SQL** en los buzones de usuario y los elementos de mensaje se importan a esa carpeta. El conector lo hace mediante el valor de la propiedad *email* . Cada elemento de Cisco Jabber contiene esta propiedad, que se rellena con la dirección de correo electrónico de cada participante de los mensajes.

## <a name="before-you-begin"></a>Antes de empezar

- Cree una cuenta de Globanet Merge1 para Microsoft Connectors. Para ello, póngase en contacto con el [soporte técnico de Globanet](https://globanet.com/ms-connectors-contact/). Debe iniciar sesión en esta cuenta cuando cree el conector en el paso 1.

- Debe configurar una base de datos de MS SQL para recuperar los elementos de Jabber antes de crear el conector en el paso 1. Deberá especificar la configuración de conexión para la base de datos MS SQL al configurar el conector Jabber de Cisco en el paso 2. Para obtener más información, consulte la guía del usuario de los [conectores de terceros de Merge1](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Cisco%20Jabber%20on%20MS%20SQL%20User%20Guide%20.pdf).

- El usuario que crea el conector Jabber de Cisco en el paso 1 (y lo completa en el paso 3) debe estar asignado a la función importación y exportación de buzones de correo en Exchange Online. Este rol es necesario para agregar conectores en la página **conectores de datos** del centro de cumplimiento de Microsoft 365. De forma predeterminada, este rol no está asignado a ningún grupo de roles en Exchange Online. Puede Agregar el rol importación y exportación de buzones al grupo de funciones de administración de la organización en Exchange Online. O bien, puede crear un grupo de roles, asignar el rol de importación y exportación de buzones de correo y, a continuación, agregar los usuarios adecuados como miembros. Para obtener más información, vea las secciones [crear grupos](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) de roles o [modificar grupos de roles](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) en el artículo sobre la administración de grupos de roles en Exchange Online.

## <a name="step-1-set-up-the-cisco-jabber-connector"></a>Paso 1: configurar el conector de Cisco Jabber

El primer paso es obtener acceso a los **conectores de datos** en el centro de cumplimiento de Microsoft 365 y crear un conector para Cisco Jabber en datos de MS SQL.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com/) y, a continuación, haga clic en **conectores**  >  **de datos Cisco Jabber en MS SQL**.

2. En la página Descripción del producto **de Cisco Jabber en MS SQL** , haga clic en **Agregar conector**.

3. En la página **condiciones de servicio** , haga clic en **Aceptar**.

4. Escriba un nombre único que identifique el conector y, a continuación, haga clic en **siguiente**.

5. Inicie sesión en su cuenta de Merge1 para configurar el conector.

## <a name="step-2-configure-the-cisco-jabber-connector-on-the-globanet-merge1-site"></a>Paso 2: configurar el conector de Cisco Jabber en el sitio de Merge1 de Globanet

El segundo paso consiste en configurar el Jabber de Cisco en MS SQL Connector en el sitio de Globanet Merge1. Para obtener información sobre cómo configurar el Jabber de Cisco en MS SQL Connector, consulte [Merge1 guía del usuario de conectores de terceros](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Cisco%20Jabber%20on%20MS%20SQL%20User%20Guide%20.pdf).

Después de hacer clic en **guardar & finalizar**, se le redirigirá al centro de cumplimiento de Microsoft 365 a la página **asignación de usuarios** del Asistente para conectores.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Paso 3: asignar usuarios y completar la configuración del conector

Para asignar usuarios y completar el conector configurado en el centro de cumplimiento de Microsoft 365, siga estos pasos:

1. En la página **asignar Cisco Jabber a los usuarios de MS SQL a los usuarios de microsoft 365** , habilite la asignación automática de usuarios. Los elementos de Cisco Jabber en MS SQL incluyen una propiedad denominada *email*, que contiene las direcciones de correo electrónico de los usuarios de la organización. Si el conector puede asociar esta dirección con un usuario de Microsoft 365, los elementos se importan al buzón de correo del usuario.

2. En la página **consentimiento del administrador** , haga clic en **proporcionar consentimiento**. Se le redirigirá al sitio de Microsoft. Haga clic en **Aceptar** para proporcionar el consentimiento.

   La organización debe permitir que el servicio de importación de Office 365 obtenga acceso a los datos de buzones de la organización. Para proporcionar el consentimiento del administrador, debe haber iniciado sesión con las credenciales de un administrador global de Microsoft 365 y aceptar la solicitud de consentimiento. Si no ha iniciado sesión como administrador global, puede ir a [esta página](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) e iniciar sesión con las credenciales de administrador global para aceptar la solicitud.

3. Haga clic en **siguiente**, revise la configuración y vaya a la página **conectores de datos** para ver el progreso del proceso de importación del nuevo conector.

## <a name="step-4-monitor-the-cisco-jabber-connector"></a>Paso 4: supervisar el conector de Cisco Jabber

Después de crear el Jabber de Cisco en MS SQL Connector, puede ver el estado del conector en el centro de cumplimiento de Microsoft 365.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com) y haga clic en **conectores de datos** en el panel de navegación izquierdo.

2. Haga clic en la ficha **conectores** y, a continuación, seleccione el **Jabber de Cisco en MS SQL** Connector para mostrar la página de flotante, que contiene las propiedades y la información sobre el conector.

3. En **Estado del conector con origen**, haga clic en el vínculo **Descargar registro** para abrir (o guardar) el registro de estado del conector. Este registro contiene datos que se han importado a la nube de Microsoft.

## <a name="known-issues"></a>Problemas conocidos

- En este momento, no se admite la importación de datos adjuntos o elementos de más de 10 MB. La compatibilidad con elementos más grandes estará disponible en una fecha posterior.
