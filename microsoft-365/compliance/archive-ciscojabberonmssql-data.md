---
title: Configurar un conector para archivar Cisco Jabber en datos de SQL MS en Microsoft 365
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
description: Los administradores pueden configurar un conector para importar y archivar datos de Cisco Jabber de Globanet en Microsoft 365. Este conector le permite archivar datos de orígenes de datos de terceros en Microsoft 365. Después de archivar estos datos, puede usar características de cumplimiento como retención legal, búsqueda de contenido y directivas de retención para administrar datos de terceros.
ms.openlocfilehash: ae94c7c48a229f7257f16deee391aade3413da53
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924006"
---
# <a name="set-up-a-connector-to-archive-cisco-jabber-data"></a>Configurar un conector para archivar datos de Cisco Jabber

Use un conector de Globanet en el Centro de cumplimiento de Microsoft 365 para importar y archivar datos desde la plataforma Cisco Jabber a los buzones de usuario de su organización de Microsoft 365. Globanet le proporciona un conector [de Cisco Jabber](https://globanet.com/jabber/) que está configurado para capturar elementos de la base de datos MS SQL de Jabber, como mensajes de chat 1:1 y chats de grupo y, a continuación, importar esos elementos a Microsoft 365. El conector recupera datos de la base de datos MS SQL de Cisco Jabber, los procesa y convierte el contenido de la cuenta de Cisco Jabber de un usuario a un formato de mensaje de correo electrónico y, a continuación, importa esos elementos al buzón del usuario en Microsoft 365.

Una vez que los datos de Cisco Jabber se almacenan en buzones de usuario, puede aplicar características de cumplimiento de Microsoft 365 como retención por juicio, exhibición de documentos electrónicos, directivas de retención y etiquetas de retención y cumplimiento de comunicaciones. El uso de un conector de Cisco Jabber para importar y archivar datos en Microsoft 365 puede ayudar a su organización a cumplir con las directivas gubernamentales y reglamentarias.

## <a name="overview-of-archiving-cisco-jabber-data"></a>Información general sobre el archivado de datos de Cisco Jabber

En la siguiente introducción se explica el proceso de uso de un conector para archivar datos de Cisco Jabber en Microsoft 365.

![Flujo de trabajo de archivado para datos de Cisco Jabber](../media/CiscoJabberonMSSQLConnectorWorkflow.png)

1. Su organización trabaja con Cisco para configurar y configurar un Cisco Jabber en MS SQL base de datos.

2. Una vez cada 24 horas, los elementos de Cisco Jabber se copian de la base de datos SQL MS al sitio de Globanet Merge1. El conector también convierte el contenido de los mensajes de chat a un formato de mensaje de correo electrónico.

3. El conector de Cisco Jabber que crea en el centro de cumplimiento de Microsoft 365 se conecta al sitio de Globanet Merge1 todos los días y transfiere los elementos a una ubicación segura de Azure Storage en la nube de Microsoft.

4. La asignación automática de usuarios como conector importa elementos a los buzones de usuarios específicos mediante el valor de la propiedad *Email* del descrito en [el paso 3](#step-3-map-users-and-complete-the-connector-setup). Se crea una subcarpeta en la carpeta Bandeja de entrada denominada **Cisco Jabber en MS SQL** en los buzones de usuario y los elementos del mensaje se importan a esa carpeta. El conector determina a qué buzón se importarán los elementos mediante el valor de la *propiedad Email.* Cada elemento de Cisco Jabber contiene esta propiedad, que se rellena con la dirección de correo electrónico de cada participante.

## <a name="before-you-begin"></a>Antes de empezar

- Crear una cuenta de Globanet Merge1 para conectores de Microsoft. Para crear esta cuenta, póngase en contacto [con el servicio de soporte al cliente de Globanet](https://globanet.com/ms-connectors-contact/). Iniciará sesión en esta cuenta al crear el conector en el paso 1.

- Configure una base de datos de SQL MS para recuperar elementos de Jabber de antes de crear el conector en el paso 1. Especificará la configuración de conexión de la base de datos de SQL MS al configurar el conector de Cisco Jabber en el paso 2. Para obtener más información, vea la Guía del usuario de [Merge1 Third-Party Connectors](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Cisco%20Jabber%20on%20MS%20SQL%20User%20Guide%20.pdf).

- El usuario que crea el conector de Cisco Jabber en el paso 1 (y lo completa en el paso 3) debe estar asignado al rol de exportación de importación de buzones en Exchange Online. Este rol es necesario para agregar conectores en la página **Conectores de datos** del Centro de cumplimiento de Microsoft 365. De forma predeterminada, este rol no se asigna a un grupo de roles en Exchange Online. Puede agregar el rol Exportación de importación de buzones al grupo de roles Administración de la organización en Exchange Online. O bien, puede crear un grupo de roles, asignar el rol Importación de buzones de correo Exportar y, a continuación, agregar los usuarios adecuados como miembros. Para obtener más información, vea [](/Exchange/permissions-exo/role-groups#modify-role-groups) las secciones [Crear](/Exchange/permissions-exo/role-groups#create-role-groups) grupos de roles o Modificar grupos de roles en el artículo "Administrar grupos de roles en Exchange Online".

## <a name="step-1-set-up-the-cisco-jabber-connector"></a>Paso 1: Configurar el conector de Cisco Jabber

El primer paso es acceder a **los** conectores de datos en el centro de cumplimiento de Microsoft 365 y crear un conector para Cisco Jabber en MS SQL datos.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com/) y, a continuación, haga clic **en Conectores de datos** Cisco  >  **Jabber en MS SQL**.

2. En la página Descripción del producto de **Cisco Jabber on MS SQL,** haga clic **en Agregar conector**.

3. En la **página Términos de** servicio, haga clic **en Aceptar**.

4. Escriba un nombre único que identifique el conector y, a continuación, haga clic en **Siguiente**.

5. Inicie sesión en su cuenta merge1 para configurar el conector.

## <a name="step-2-configure-the-cisco-jabber-connector-on-the-globanet-merge1-site"></a>Paso 2: Configurar el conector de Cisco Jabber en el sitio de Globanet Merge1

El segundo paso consiste en configurar cisco Jabber en el conector SQL MS en el sitio de Globanet Merge1. Para obtener información acerca de cómo configurar cisco Jabber en el conector SQL MS, vea [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Cisco%20Jabber%20on%20MS%20SQL%20User%20Guide%20.pdf).

Después de hacer clic en Guardar  & **finalizar**, se muestra la página Asignación de usuario en el asistente para conectores en el Centro de cumplimiento de Microsoft 365.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Paso 3: Asignar usuarios y completar la configuración del conector

Para asignar usuarios y completar la configuración del conector en el Centro de cumplimiento de Microsoft 365, siga estos pasos:

1. En la **página Asignar Cisco Jabber en MS SQL usuarios a usuarios de Microsoft 365,** habilite la asignación automática de usuarios. El Jabber de Cisco en MS SQL elementos incluyen una propiedad denominada *Correo* electrónico , que contiene direcciones de correo electrónico para los usuarios de su organización. Si el conector puede asociar esta dirección con un usuario de Microsoft 365, los elementos se importan al buzón de ese usuario.

2. Haga **clic en** Siguiente, revise la configuración y vaya a la página **Conectores** de datos para ver el progreso del proceso de importación del nuevo conector.

## <a name="step-4-monitor-the-cisco-jabber-connector"></a>Paso 4: Supervisar el conector de Cisco Jabber

Después de crear cisco Jabber en el conector de SQL MS, puede ver el estado del conector en el Centro de cumplimiento de Microsoft 365.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com) y haga clic en **Conectores de datos** en la navegación izquierda.

2. Haga clic **en la pestaña Conectores** y, a continuación, seleccione cisco **Jabber en MS SQL** conector para mostrar la página desplegable. Esta página contiene las propiedades y la información sobre el conector.

3. En **Estado del conector con origen,** haga clic en el vínculo Descargar **registro** para abrir (o guardar) el registro de estado del conector. Este registro contiene datos que se han importado a la nube de Microsoft.

## <a name="known-issues"></a>Problemas conocidos

- En este momento, no se admite la importación de datos adjuntos o elementos de más de 10 MB. La compatibilidad con elementos más grandes estará disponible en una fecha posterior.