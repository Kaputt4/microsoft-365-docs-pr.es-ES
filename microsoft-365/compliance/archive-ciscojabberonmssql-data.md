---
title: Configuración de un conector para archivar Cisco Jabber en datos de MS SQL en Microsoft 365
description: Los administradores pueden configurar un conector para importar y archivar Cisco Jabber en datos de MS SQL de Veritas en Microsoft 365. Este conector le permite archivar datos de orígenes de datos de terceros en Microsoft 365. Después de archivar estos datos, puede usar características de cumplimiento como la suspensión legal, la búsqueda de contenido y las directivas de retención para administrar datos de terceros.
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- tier3
- purview-compliance
- data-connectors
ms.openlocfilehash: 2c0eb6ad56705829c7973d1d94714b0fdc3a3b0d
ms.sourcegitcommit: 8d3c027592a638f411f87d89772dd3d39e92aab0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/12/2022
ms.locfileid: "68535545"
---
# <a name="set-up-a-connector-to-archive-cisco-jabber-on-ms-sql-data"></a>Configuración de un conector para archivar Cisco Jabber en datos de MS SQL

Use un conector Veritas en el portal de cumplimiento Microsoft Purview para importar y archivar datos de la plataforma Cisco Jabber a buzones de usuario de su organización de Microsoft 365. Veritas le proporciona un conector [del Cisco Jabber](https://globanet.com/jabber/) que está configurado para capturar los elementos de la SQL Database MS del Jabber, tales como mensajes de chat 1:1 y chats de grupo y luego importar esos elementos a Microsoft 365. El conector recupera los datos de la SQL Database MS del Cisco Jabber, los procesa, y convierte el contenido de la cuenta de Cisco Jabber de un usuario a un formato de mensaje de correo electrónico y luego importa esos elementos al buzón del usuario en Microsoft 365.

Una vez que los datos del Cisco Jabber se almacenan en buzones de usuario, puede aplicar características de Microsoft Purview como suspensión por juicio, exhibición de documentos electrónicos, directivas de retención y etiquetas de retención, y cumplimiento de la comunicación. El uso de un conector Cisco Jabber para importar y archivar datos en Microsoft 365 puede ayudar a su organización a cumplir las directivas gubernamentales y reglamentarias.

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="overview-of-archiving-cisco-jabber-data"></a>Introducción al archivado de datos de Cisco Jabber

En la información general siguiente se explica el proceso de uso de un conector para archivar Cisco Jabber en datos de MS SQL en Microsoft 365.

![Flujo de trabajo de archivado para datos de Cisco Jabber.](../media/CiscoJabberonMSSQLConnectorWorkflow.png)

1. Su organización trabaja con Cisco para configurar un Cisco Jabber en MS SQL Database.

2. Una vez cada 24 horas, los elementos del Cisco Jabber se copian del MS SQL Database al sitio de Veritas Merge1. El conector también convierte el contenido de los mensajes de chat en un formato de mensaje de correo electrónico.

3. El conector Cisco Jabber que se crea en el portal de cumplimiento se conecta al sitio de Veritas Merge1 todos los días y transfiere los elementos a una ubicación segura de Azure Storage en la nube de Microsoft.

4. La asignación automática de usuarios como conector importa elementos a los buzones de usuarios específicos mediante el valor de la propiedad *Email* del descrito en el [paso 3](#step-3-map-users-and-complete-the-connector-setup). Una subcarpeta en la carpeta bandeja de entrada denominada **Cisco Jabber en MS SQL** se crea en los buzones de usuario, y los elementos del mensaje se importan a esa carpeta. El conector determina a qué buzón se van a importar elementos mediante el valor de la propiedad *Email*. Cada elemento del Jabber de Cisco contiene esta propiedad, que se rellena con la dirección de correo electrónico de cada participante.

## <a name="before-you-begin"></a>Antes de empezar

- Cree una cuenta de Veritas Merge1 para los conectores de Microsoft. Para crear esta cuenta, póngase en contacto con [el servicio de atención al cliente de Veritas](https://www.veritas.com/content/support/). Iniciará sesión en esta cuenta al crear el conector en el paso 1.

- Configure una SQL Database MS para recuperar elementos del Jabber antes de crear el conector en el paso 1. Usted especificará las configuraciones de conexión para el MS SQL Database al configurar el conector del Jabber de Cisco en el paso 2. Para obtener más información, consulte la [Guía del usuario de conectores de terceros merge1](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Cisco%20Jabber%20on%20MS%20SQL%20User%20Guide%20.pdf).

- El usuario que crea el conector del Jabber de Cisco en el paso 1 (y lo completa en el paso 3) debe ser asignado el rol Administración del conector de datos. Este rol es necesario para agregar conectores en la página **Conectores de datos** del portal de cumplimiento. Este rol se agrega de forma predeterminada a varios grupos de roles. Para obtener una lista de estos grupos de roles, consulte la sección "Roles en los centros de seguridad y cumplimiento" de [Permisos en el Centro de cumplimiento de & seguridad](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center). Como alternativa, un administrador de su organización puede crear un grupo de roles personalizado, asignar el rol Administración conector de datos y, a continuación, agregar los usuarios adecuados como miembros. Para obtener instrucciones, consulte la sección "Crear un grupo de roles personalizado" en [Permisos en el portal de cumplimiento Microsoft Purview](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group).

- Este conector de datos de Veritas está en versión preliminar pública en entornos GCC en la nube de Microsoft 365 US Government. Las aplicaciones y servicios de terceros pueden implicar almacenar, transmitir y procesar los datos de clientes de su organización en sistemas de terceros que están fuera de la infraestructura de Microsoft 365 y, por lo tanto, no están cubiertos por los compromisos de protección de datos y Microsoft Purview. Microsoft no hace ninguna representación de que el uso de este producto para conectarse a aplicaciones de terceros implica que esas aplicaciones de terceros son compatibles con FEDRAMP.

## <a name="step-1-set-up-the-cisco-jabber-on-ms-sql-connector"></a>Paso 1: Configurar el Cisco Jabber en el conector MS SQL

El primer paso es acceder a los **conectores de datos** en el portal de cumplimiento y crear un conector para Cisco Jabber en los datos de MS SQL.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com/)y después seleccione el Cisco Jabber **de los conectores** >  de datos **en MS SQL**.

2. En la página de descripción del producto **del Jabber de Cisco en MS SQL** , seleccione **Agregar conector**.

3. En la página **Términos de servicio** , seleccione **Aceptar**.

4. Escriba un nombre único que identifique el conector y, a continuación, seleccione **Siguiente**.

5. Inicie sesión en su cuenta de Merge1 para configurar el conector.

## <a name="step-2-configure-the-cisco-jabber-on-ms-sql-connector-on-the-veritas-merge1-site"></a>Paso 2: Configurar el Cisco Jabber en el conector MS SQL en el sitio de Veritas Merge1

El segundo paso es configurar el Cisco Jabber en el conector MS SQL en el sitio de Veritas Merge1. Para obtener información sobre cómo configurar el Cisco Jabber en el conector MS SQL, vea [la guía del usuario de los conectores de terceros merge1](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Cisco%20Jabber%20on%20MS%20SQL%20User%20Guide%20.pdf).

Después de seleccionar **Guardar & Finalizar**, se muestra la página **Asignación** de usuarios en el Asistente para conectores en el portal de cumplimiento.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Paso 3: Asignar usuarios y completar la configuración del conector

Para asignar usuarios y completar la configuración del conector en el portal de cumplimiento, siga estos pasos:

1. En la página **Map Cisco Jabber on MS SQL users to Microsoft 365 users (Asignar cisco jabber en MS SQL a usuarios de Microsoft 365** ), habilite la asignación automática de usuarios. El Cisco Jabber en los elementos de MS SQL incluye una propiedad llamada *Email*, que contiene direcciones de correo electrónico para los usuarios de su organización. Si el conector puede asociar esta dirección a un usuario de Microsoft 365, los elementos se importan al buzón de ese usuario.

2. Seleccione **Siguiente**, revise la configuración y vaya a la página **Conectores de datos** para ver el progreso del proceso de importación del nuevo conector.

## <a name="step-4-monitor-the-cisco-jabber-connector"></a>Paso 4: Supervisar el conector de Cisco Jabber

Después de que usted cree el Jabber de Cisco en el conector MS SQL, usted puede ver el estado del conector en el portal de cumplimiento.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com) y seleccione **Conectores de datos** en el panel de navegación izquierdo.

2. Seleccione la pestaña **Conectores** y, después, seleccione el **Cisco Jabber en el conector MS SQL** para mostrar la página de control flotante. Esta página contiene las propiedades y la información sobre el conector.

3. En **Estado del conector con origen**, seleccione el vínculo **Descargar registro** para abrir (o guardar) el registro de estado del conector. Este registro contiene información sobre los datos que se han importado a la nube de Microsoft. Para obtener más información, consulte [Visualización de registros de administración para conectores de datos](data-connector-admin-logs.md).

## <a name="known-issues"></a>Problemas conocidos

- En este momento, no se admiten la importación de datos adjuntos o elementos que superen los 10 MB. La compatibilidad con elementos más grandes estará disponible en una fecha posterior.
