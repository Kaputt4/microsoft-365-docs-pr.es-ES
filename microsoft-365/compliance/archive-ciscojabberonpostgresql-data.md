---
title: Configurar un conector para archivar datos de Cisco Jabber en PostgreSQL en Microsoft 365
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
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: seo-marvel-apr2020
description: Obtenga información sobre cómo configurar y usar un conector en el Centro de cumplimiento de Microsoft 365 importar y archivar datos de Cisco Jabber en PostgreSQL para Microsoft 365.
ms.openlocfilehash: 946a43155ed085575e9aef97b04f0828338963e5
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63328839"
---
# <a name="set-up-a-connector-to-archive-cisco-jabber-on-postgresql-data"></a>Configurar un conector para archivar datos de Cisco Jabber en PostgreSQL

Use un conector Veritas en el Centro de cumplimiento de Microsoft 365 para importar y archivar datos de la plataforma De Cisco Jabber a buzones de usuario de su Microsoft 365 organización. Veritas proporciona un conector [de Cisco Jabber en PostgreSQL](https://www.veritas.com/insights/merge1/jabber) que está configurado para capturar elementos del origen de datos de terceros (de forma regular) e importar esos elementos a Microsoft 365. El conector convierte el contenido como mensajes, chats y contenido compartido de Cisco Jabber en PostgreSQL a un formato de mensaje de correo electrónico y, a continuación, importa esos elementos al buzón del usuario en Microsoft 365.

Una vez que los datos de Cisco Jabber en PostgreSQL se almacenan en buzones de usuario, puede aplicar Microsoft 365 de cumplimiento, como retención por juicio, exhibición de documentos electrónicos, directivas de retención y etiquetas de retención. El uso de un conector de Cisco Jabber en PostgreSQL para importar y archivar datos en Microsoft 365 puede ayudar a su organización a cumplir con las directivas gubernamentales y reglamentarias.

## <a name="overview-of-archiving-cisco-jabber-on-postgresql-data"></a>Información general sobre el archivado de datos de Cisco Jabber en PostgreSQL

En la siguiente introducción se explica el proceso de uso de un conector para archivar los datos de Cisco Jabber en PostgreSQL en Microsoft 365.

![Flujo de trabajo de archivado para datos de Cisco Jabber en PostgreSQL.](../media/CiscoJabberonPostgreSQLConnectorWorkflow.png)

1. Su organización trabaja con Cisco Jabber en PostgreSQL para configurar y configurar un sitio de Cisco Jabber en PostgreSQL.

2. Una vez cada 24 horas, los elementos de Cisco Jabber on PostgreSQL se copian en el sitio Veritas Merge1. El conector también convierte elementos de Cisco Jabber en PostgreSQL a un formato de mensaje de correo electrónico.

3. El conector de Cisco Jabber on PostgreSQL que crea en el Centro de cumplimiento de Microsoft 365, se conecta al sitio Veritas Merge1 todos los días y transfiere el contenido de Jabber a una ubicación Azure Storage segura en la nube de Microsoft.

4. El conector importa los elementos convertidos a los buzones de usuarios específicos mediante el valor de la propiedad *Email* de la asignación automática de usuarios, tal como se describe en [el paso 3](#step-3-map-users-and-complete-the-connector-setup). Se crea una subcarpeta en la carpeta Bandeja de entrada denominada **Cisco Jabber en PostgreSQL** en los buzones de usuario y los elementos se importan a esa carpeta. El conector hace esto mediante el valor de la *propiedad Email* . Cada elemento de Jabber contiene esta propiedad, que se rellena con la dirección de correo electrónico de cada participante del elemento.

## <a name="before-you-begin"></a>Antes de empezar

- Crear una cuenta Merge1 para conectores de Microsoft. Para ello, póngase en contacto con [el Servicio de soporte al cliente de Veritas](https://www.veritas.com/content/support/en_US). Debe iniciar sesión en esta cuenta al crear el conector en el paso 1.

- El usuario que crea el conector de Cisco Jabber on PostgreSQL en el paso 1 (y lo completa en el paso 3) debe tener asignado el rol de administrador del conector de datos. Este rol es necesario para agregar conectores en la **página Conectores de datos** de la Centro de cumplimiento de Microsoft 365. Este rol se agrega de forma predeterminada a varios grupos de roles. Para obtener una lista de estos grupos de roles, vea la sección "Roles en los centros de seguridad y cumplimiento" en Permisos en el [Centro de seguridad & cumplimiento](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center). Como alternativa, un administrador de la organización puede crear un grupo de roles personalizado, asignar el rol de administrador del conector de datos y, a continuación, agregar los usuarios adecuados como miembros. Para obtener instrucciones, vea la sección "Crear un grupo de roles personalizado" en [Permisos en el Centro de cumplimiento de Microsoft 365](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group).

- Este conector de datos de Veritas se encuentra en versión preliminar pública en GCC entornos de la Microsoft 365 us government cloud. Las aplicaciones y servicios de terceros pueden implicar almacenar, transmitir y procesar los datos de clientes de su organización en sistemas de terceros que están fuera de la infraestructura de Microsoft 365 y, por lo tanto, no están cubiertos por los compromisos de cumplimiento y protección de datos de Microsoft 365. Microsoft no hace ninguna representación de que el uso de este producto para conectarse a aplicaciones de terceros implica que esas aplicaciones de terceros son compatibles con FEDRAMP.

## <a name="step-1-set-up-the-cisco-jabber-on-postgresql-connector"></a>Paso 1: Configurar el conector de Cisco Jabber en PostgreSQL

El primer paso es obtener acceso a la página **Conectores** de datos de la Centro de cumplimiento de Microsoft 365 y crear un conector para los datos de Jabber.

1. Vaya a <https://compliance.microsoft.com> y, a continuación, **haga clic en Conectores de datos** &gt; **Cisco Jabber en PostgreSQL**.

2. En la **página Descripción del producto de Cisco Jabber on PostgreSQL** , haga clic **en Agregar conector**.

3. En la **página Términos de** servicio, haga clic en **Aceptar**.

4. Escriba un nombre único que identifique el conector y, a continuación, haga clic en **Siguiente**.

5. Inicie sesión en su cuenta merge1 para configurar el conector.

## <a name="step-2-configure-the-cisco-jabber-on-postgresql-on-the-veritas-merge1-site"></a>Paso 2: Configurar Cisco Jabber en PostgreSQL en el sitio Veritas Merge1

El segundo paso consiste en configurar el conector de Cisco Jabber on PostgreSQL en el sitio Veritas Merge1. Para obtener información sobre cómo configurar el conector de Cisco Jabber on PostgreSQL, consulte [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Cisco%20Jabber%20on%20PostgreSQL%20User%20Guide.pdf).

Después de hacer **clic en Guardar & finalizar**, se muestra  la página Asignación de usuario en el asistente para conector en Centro de cumplimiento de Microsoft 365.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Paso 3: Asignar usuarios y completar la configuración del conector

Para asignar usuarios y completar la configuración del conector en el Centro de cumplimiento de Microsoft 365, siga estos pasos:

1. En la **página Asignar usuarios de Cisco Jabber en PostgreSQL a Microsoft 365** usuarios, habilite la asignación automática de usuarios. Los elementos de Cisco Jabber on PostgreSQL incluyen una propiedad denominada *Email*, que contiene direcciones de correo electrónico para los usuarios de su organización. Si el conector puede asociar esta dirección a un Microsoft 365, los elementos se importan al buzón de ese usuario.

2. Haga **clic en** Siguiente, revise la configuración y, a continuación, vaya a la página **Conectores** de datos para ver el progreso del proceso de importación del nuevo conector.

## <a name="step-4-monitor-the-cisco-jabber-on-postgresql-connector"></a>Paso 4: Supervisar el conector de Cisco Jabber en PostgreSQL

Después de crear el conector de Cisco Jabber en PostgreSQL, puede ver el estado del conector en el Centro de cumplimiento de Microsoft 365.

1. Vaya a <https://compliance.microsoft.com/> y haga clic **en Conectores de datos** en la navegación izquierda.

2. Haga clic **en la pestaña Conectores** y, a continuación, seleccione el conector **Cisco Jabber on PostgreSQL** para mostrar la página desplegable, que contiene las propiedades e información sobre el conector.

3. En **Estado del conector con origen**, haga clic en el vínculo **Descargar registro** para abrir (o guardar) el registro de estado del conector. Este registro contiene datos que se han importado a la nube de Microsoft.

## <a name="known-issues"></a>Problemas conocidos

- En este momento, no se admite la importación de datos adjuntos o elementos de más de 10 MB. La compatibilidad con elementos más grandes estará disponible en una fecha posterior.
