---
title: Configurar un conector para archivar Cisco Jabber en MS SQL datos en Microsoft 365
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
description: Los administradores pueden configurar un conector para importar y archivar Cisco Jabber en MS SQL datos de Veritas en Microsoft 365. Este conector permite archivar datos de orígenes de datos de terceros en Microsoft 365. Después de archivar estos datos, puede usar características de cumplimiento como retención legal, búsqueda de contenido y directivas de retención para administrar datos de terceros.
ms.openlocfilehash: 01899e4142d6e60fb10a101f7af8e9b4143a38c8
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764311"
---
# <a name="set-up-a-connector-to-archive-cisco-jabber-on-ms-sql-data"></a>Configurar un conector para archivar Cisco Jabber en datos de SQL MS

Use un conector Veritas en el centro de cumplimiento de Microsoft 365 para importar y archivar datos de la plataforma De Cisco Jabber a los buzones de usuario de su Microsoft 365 organización. Veritas le proporciona un conector [de Cisco Jabber](https://globanet.com/jabber/) configurado para capturar elementos del MS SQL Database de Jabber, como mensajes de chat 1:1 y chats de grupo y, a continuación, importar esos elementos a Microsoft 365. El conector recupera datos del MS SQL Database de Cisco Jabber, los procesa y convierte el contenido de la cuenta de Cisco Jabber de un usuario a un formato de mensaje de correo electrónico y, a continuación, importa esos elementos al buzón del usuario en Microsoft 365.

Una vez que los datos de Cisco Jabber se almacenan en buzones de usuario, puede aplicar Microsoft 365 características de cumplimiento como retención por juicio, exhibición de documentos electrónicos, directivas de retención y etiquetas de retención y cumplimiento de comunicaciones. El uso de un conector de Cisco Jabber para importar y archivar datos en Microsoft 365 puede ayudar a su organización a cumplir con las directivas gubernamentales y reglamentarias.

## <a name="overview-of-archiving-cisco-jabber-data"></a>Información general sobre el archivado de datos de Cisco Jabber

En la siguiente introducción se explica el proceso de uso de un conector para archivar Cisco Jabber en MS SQL datos en Microsoft 365.

![Flujo de trabajo de archivado para datos de Cisco Jabber](../media/CiscoJabberonMSSQLConnectorWorkflow.png)

1. Su organización trabaja con Cisco para configurar y configurar un Jabber de Cisco en MS SQL Database.

2. Una vez cada 24 horas, los elementos de Cisco Jabber se copian del MS SQL Database al sitio de Veritas Merge1. El conector también convierte el contenido de los mensajes de chat a un formato de mensaje de correo electrónico.

3. El conector de Cisco Jabber que crea en el centro de cumplimiento de Microsoft 365 se conecta al sitio Veritas Merge1 todos los días y transfiere los elementos a una ubicación Azure Storage segura en la nube de Microsoft.

4. La asignación automática de usuarios como conector importa elementos a los buzones de usuarios específicos mediante el valor de la propiedad *Email* del descrito en [el paso 3](#step-3-map-users-and-complete-the-connector-setup). Se crea una subcarpeta en la carpeta Bandeja de entrada denominada **Cisco Jabber en MS SQL** en los buzones de usuario y los elementos del mensaje se importan a esa carpeta. El conector determina a qué buzón se importarán los elementos mediante el valor de la *propiedad Email.* Cada elemento de Cisco Jabber contiene esta propiedad, que se rellena con la dirección de correo electrónico de cada participante.

## <a name="before-you-begin"></a>Antes de empezar

- Cree una cuenta de Veritas Merge1 para conectores de Microsoft. Para crear esta cuenta, póngase en contacto con [el servicio de soporte al cliente de Veritas](https://www.veritas.com/content/support/). Iniciará sesión en esta cuenta al crear el conector en el paso 1.

- Configure una MS SQL Database para recuperar elementos de Jabber desde antes de crear el conector en el paso 1. Especificará la configuración de conexión para el MS SQL Database configurar el conector de Cisco Jabber en el paso 2. Para obtener más información, vea la Guía del usuario de [Merge1 Third-Party Connectors](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Cisco%20Jabber%20on%20MS%20SQL%20User%20Guide%20.pdf).

- El usuario que crea el conector de Cisco Jabber en el paso 1 (y lo completa en el paso 3) debe estar asignado al rol De exportación de importación de buzones en Exchange Online. Este rol es necesario para agregar conectores en la página **Conectores** de datos del centro de Microsoft 365 cumplimiento. De forma predeterminada, este rol no se asigna a un grupo de roles en Exchange Online. Puede agregar el rol Exportación de importación de buzones al grupo de roles Administración de la organización en Exchange Online. O bien, puede crear un grupo de roles, asignar el rol Importación de buzones de correo Exportar y, a continuación, agregar los usuarios adecuados como miembros. Para obtener más información, vea [](/Exchange/permissions-exo/role-groups#modify-role-groups) las secciones [Crear](/Exchange/permissions-exo/role-groups#create-role-groups) grupos de roles o Modificar grupos de roles en el artículo "Administrar grupos de roles en Exchange Online".

## <a name="step-1-set-up-the-cisco-jabber-on-ms-sql-connector"></a>Paso 1: Configurar Cisco Jabber en el conector de SQL MS

El primer paso es  acceder a los conectores de datos en el centro de cumplimiento de Microsoft 365 y crear un conector para Cisco Jabber en MS SQL datos.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com/) y, a continuación, haga clic **en Conectores de datos** Cisco  >  **Jabber en MS SQL**.

2. En la página Descripción del producto de **Cisco Jabber on MS SQL,** haga clic **en Agregar conector**.

3. En la **página Términos de** servicio, haga clic **en Aceptar**.

4. Escriba un nombre único que identifique el conector y, a continuación, haga clic en **Siguiente**.

5. Inicie sesión en su cuenta merge1 para configurar el conector.

## <a name="step-2-configure-the-cisco-jabber-on-ms-sql-connector-on-the-veritas-merge1-site"></a>Paso 2: Configurar Cisco Jabber en el conector de SQL MS en el sitio de Veritas Merge1

El segundo paso es configurar cisco Jabber en el conector de SQL MS en el sitio de Veritas Merge1. Para obtener información acerca de cómo configurar cisco Jabber en el conector SQL MS, vea [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Cisco%20Jabber%20on%20MS%20SQL%20User%20Guide%20.pdf).

Después de hacer clic en Guardar  & **finalizar**, se muestra la página Asignación de usuario en el asistente para conectores en Microsoft 365 centro de cumplimiento.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Paso 3: Asignar usuarios y completar la configuración del conector

Para asignar usuarios y completar la configuración del conector en el centro de Microsoft 365 cumplimiento, siga estos pasos:

1. En la **página Asignar Cisco Jabber en MS SQL usuarios** a Microsoft 365, habilite la asignación automática de usuarios. El Jabber de Cisco en MS SQL elementos incluyen una propiedad denominada *Correo* electrónico , que contiene direcciones de correo electrónico para los usuarios de su organización. Si el conector puede asociar esta dirección a un Microsoft 365, los elementos se importan al buzón de ese usuario.

2. Haga **clic en** Siguiente, revise la configuración y vaya a la página **Conectores** de datos para ver el progreso del proceso de importación del nuevo conector.

## <a name="step-4-monitor-the-cisco-jabber-connector"></a>Paso 4: Supervisar el conector de Cisco Jabber

Después de crear cisco Jabber en el conector SQL MS, puede ver el estado del conector en el centro Microsoft 365 cumplimiento.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com) y haga clic en **Conectores de datos** en la navegación izquierda.

2. Haga clic **en la pestaña Conectores** y, a continuación, seleccione cisco **jabber en MS SQL** conector para mostrar la página desplegable. Esta página contiene las propiedades y la información sobre el conector.

3. En **Estado del conector con origen,** haga clic en el vínculo Descargar **registro** para abrir (o guardar) el registro de estado del conector. Este registro contiene datos que se han importado a la nube de Microsoft.

## <a name="known-issues"></a>Problemas conocidos

- En este momento, no se admite la importación de datos adjuntos o elementos de más de 10 MB. La compatibilidad con elementos más grandes estará disponible en una fecha posterior.
