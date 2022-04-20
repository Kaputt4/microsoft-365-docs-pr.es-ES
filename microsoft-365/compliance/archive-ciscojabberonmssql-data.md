---
title: Configure un conector para archivar el Cisco Jabber en los datos de SQL MS en Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
description: Los administradores pueden configurar un conector para importar y archivar Cisco Jabber en MS SQL datos de Veritas en Microsoft 365. Este conector le permite archivar datos de orígenes de datos de terceros en Microsoft 365. Después de archivar estos datos, puede usar características de cumplimiento como la suspensión legal, la búsqueda de contenido y las directivas de retención para administrar datos de terceros.
ms.openlocfilehash: 691b27b59b6ade98523f0324e22e0e0cb533fabd
ms.sourcegitcommit: 52eea2b65c0598ba4a1b930c58b42dbe62cdaadc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/19/2022
ms.locfileid: "64946756"
---
# <a name="set-up-a-connector-to-archive-cisco-jabber-on-ms-sql-data"></a>Configurar un conector para archivar Cisco Jabber en datos de SQL MS

Use un conector veritas en el portal de cumplimiento de Microsoft Purview para importar y archivar datos de la plataforma Cisco Jabber a los buzones de usuario de su organización Microsoft 365. Veritas le proporciona un conector [del Jabber de Cisco](https://globanet.com/jabber/) que se configura para capturar los elementos de la SQL Database MS del Jabber, tales como mensajes de chat 1:1 y chats de grupo y luego importar esos elementos a Microsoft 365. El conector recupera los datos de la SQL Database MS del Cisco Jabber, los procesa, y convierte el contenido de la cuenta del Cisco Jabber de un usuario a un formato de mensaje de correo electrónico y luego importa esos elementos al buzón del usuario en Microsoft 365.

Una vez que los datos del Cisco Jabber se almacenan en buzones de usuario, puede aplicar características de Microsoft Purview como suspensión por juicio, exhibición de documentos electrónicos, directivas de retención y etiquetas de retención, y cumplimiento de la comunicación. El uso de un conector Cisco Jabber para importar y archivar datos en Microsoft 365 puede ayudar a su organización a cumplir con las directivas gubernamentales y reglamentarias.

## <a name="overview-of-archiving-cisco-jabber-data"></a>Introducción al archivado de datos de Cisco Jabber

La siguiente información general explica el proceso de uso de un conector para archivar el Cisco Jabber en los datos de SQL MS en Microsoft 365.

![Flujo de trabajo de archivado para datos de Cisco Jabber.](../media/CiscoJabberonMSSQLConnectorWorkflow.png)

1. Su organización trabaja con Cisco para configurar un Cisco Jabber en MS SQL Database.

2. Una vez cada 24 horas, los elementos del Cisco Jabber se copian del MS SQL Database al sitio de Veritas Merge1. El conector también convierte el contenido de los mensajes de chat en un formato de mensaje de correo electrónico.

3. El conector Cisco Jabber que usted crea en el portal de cumplimiento se conecta al sitio de Veritas Merge1 todos los días y transfiere los elementos a una ubicación segura Azure Storage en la nube de Microsoft.

4. La asignación automática de usuarios como conector importa elementos a los buzones de usuarios específicos mediante el valor de la propiedad *Email* del descrito en el [paso 3](#step-3-map-users-and-complete-the-connector-setup). Una subcarpeta en la carpeta bandeja de entrada denominada **Cisco Jabber en MS SQL** se crea en los buzones de usuario, y los elementos del mensaje se importan a esa carpeta. El conector determina a qué buzón se van a importar elementos mediante el valor de la propiedad *Email* . Cada elemento del Jabber de Cisco contiene esta propiedad, que se rellena con la dirección de correo electrónico de cada participante.

## <a name="before-you-begin"></a>Antes de empezar

- Cree una cuenta de Veritas Merge1 para los conectores de Microsoft. Para crear esta cuenta, póngase en contacto con [el servicio de atención al cliente de Veritas](https://www.veritas.com/content/support/). Iniciará sesión en esta cuenta al crear el conector en el paso 1.

- Configure una SQL Database MS para recuperar elementos del Jabber antes de crear el conector en el paso 1. Usted especificará las configuraciones de conexión para el MS SQL Database al configurar el conector del Jabber de Cisco en el paso 2. Para obtener más información, consulte la [Guía del usuario de conectores de terceros merge1](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Cisco%20Jabber%20on%20MS%20SQL%20User%20Guide%20.pdf).

- El usuario que crea el conector del Jabber de Cisco en el paso 1 (y lo completa en el paso 3) debe ser asignado el rol de administrador del conector de datos. Este rol es necesario para agregar conectores en la página **Conectores de datos** del portal de cumplimiento. Este rol se agrega de forma predeterminada a varios grupos de roles. Para obtener una lista de estos grupos de roles, consulte la sección "Roles en los centros de seguridad y cumplimiento" de [Permisos en el Centro de cumplimiento de & seguridad](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center). Como alternativa, un administrador de su organización puede crear un grupo de roles personalizado, asignar el rol Administrador del conector de datos y, a continuación, agregar los usuarios adecuados como miembros. Para obtener instrucciones, consulte la sección "Crear un grupo de roles personalizado" en [Permisos en el portal de cumplimiento de Microsoft Purview](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group).

- Este conector de datos de Veritas está en versión preliminar pública en entornos de GCC en la nube Microsoft 365 administración pública de EE. UU. Las aplicaciones y servicios de terceros pueden implicar almacenar, transmitir y procesar los datos de clientes de su organización en sistemas de terceros que están fuera de la infraestructura de Microsoft 365 y, por tanto, no están cubiertos por los compromisos de protección de datos y Microsoft Purview. Microsoft no hace ninguna representación de que el uso de este producto para conectarse a aplicaciones de terceros implica que esas aplicaciones de terceros son compatibles con FEDRAMP.

## <a name="step-1-set-up-the-cisco-jabber-on-ms-sql-connector"></a>Paso 1: Configurar el Cisco Jabber en el conector de SQL MS

El primer paso es acceder a los **conectores de datos** en el portal de cumplimiento y crear un conector para Cisco Jabber en los datos SQL MS.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com/)y luego haga clic en **Conectores** >  de **datosCisco Jabber en MS SQL**.

2. En la página de descripción del producto **del Jabber de Cisco en MS SQL**, haga clic en **Agregar conector**.

3. En la página **Términos de servicio** , haga clic en **Aceptar**.

4. Escriba un nombre único que identifique el conector y, a continuación, haga clic en **Siguiente**.

5. Inicie sesión en su cuenta de Merge1 para configurar el conector.

## <a name="step-2-configure-the-cisco-jabber-on-ms-sql-connector-on-the-veritas-merge1-site"></a>Paso 2: Configure el Cisco Jabber en el conector de SQL MS en el sitio de Veritas Merge1

El segundo paso es configurar el Cisco Jabber en el conector de SQL MS en el sitio de Veritas Merge1. Para obtener información sobre cómo configurar el Cisco Jabber en el conector de SQL MS, vea [la guía del usuario de los conectores de terceros merge1](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Cisco%20Jabber%20on%20MS%20SQL%20User%20Guide%20.pdf).

Después de hacer clic en **Guardar & finalizar**, se muestra la página **Asignación** de usuarios del asistente del conector en el portal de cumplimiento.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Paso 3: Asignar usuarios y completar la configuración del conector

Para asignar usuarios y completar la configuración del conector en el portal de cumplimiento, siga estos pasos:

1. En el **Cisco Jabber del mapa en el MS SQL los usuarios para Microsoft 365 página de los usuarios**, habilite la asignación automática de usuarios. El Cisco Jabber en MS SQL elementos incluyen una propiedad llamada *Correo electrónico*, que contiene direcciones de correo electrónico para los usuarios de su organización. Si el conector puede asociar esta dirección a un usuario Microsoft 365, los elementos se importan al buzón de ese usuario.

2. Haga clic en **Siguiente**, revise la configuración y vaya a la página **Conectores de datos** para ver el progreso del proceso de importación del nuevo conector.

## <a name="step-4-monitor-the-cisco-jabber-connector"></a>Paso 4: Supervisar el conector de Cisco Jabber

Después de que usted cree el Jabber de Cisco en el conector del SQL MS, usted puede ver el estado del conector en el portal de cumplimiento.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com) y haga clic en **Conectores de datos** en el panel de navegación izquierdo.

2. Haga clic en la pestaña **Conectores** y después seleccione el **Cisco Jabber en el conector de SQL MS** para mostrar la página de control flotante. Esta página contiene las propiedades y la información sobre el conector.

3. En **Estado del conector con origen**, haga clic en el vínculo **Descargar registro** para abrir (o guardar) el registro de estado del conector. Este registro contiene datos que se han importado a la nube de Microsoft.

## <a name="known-issues"></a>Problemas conocidos

- En este momento, no se admiten la importación de datos adjuntos o elementos que superen los 10 MB. La compatibilidad con elementos más grandes estará disponible en una fecha posterior.
