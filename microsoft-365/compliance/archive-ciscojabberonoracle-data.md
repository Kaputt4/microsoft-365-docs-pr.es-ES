---
title: Configurar un conector para archivar datos de Cisco Jabber en Oracle en Microsoft 365
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
description: Obtenga información sobre cómo configurar y usar un conector en el Centro de cumplimiento de Microsoft 365 importar y archivar datos de Cisco Jabber en Oracle para Microsoft 365.
ms.openlocfilehash: 6d38abfbbb8380a6f7eb5bc617460a1a3b8e6e73
ms.sourcegitcommit: 36a19d80fe3f053df0fec398a7ff2dfc777f9730
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/30/2021
ms.locfileid: "61643115"
---
# <a name="set-up-a-connector-to-archive-cisco-jabber-on-oracle-data"></a>Configurar un conector para archivar datos de Cisco Jabber en Oracle

Use un conector Veritas en el Centro de cumplimiento de Microsoft 365 para importar y archivar datos de la plataforma Cisco Jabber en Oracle a los buzones de usuario de su Microsoft 365 organización. Veritas proporciona un [conector de Cisco Jabber en Oracle](https://www.veritas.com/insights/merge1/jabber) que está configurado para capturar elementos del origen de datos de terceros (de forma regular) e importar esos elementos a Microsoft 365. El conector convierte el contenido como archivos y operaciones de archivo, comentarios y contenido compartido de Cisco Jabber en Oracle a un formato de mensaje de correo electrónico y, a continuación, importa esos elementos al buzón del usuario en Microsoft 365.

Una vez que los datos de Cisco Jabber en Oracle se almacenan en buzones de usuario, puede aplicar características de cumplimiento Microsoft 365 como retención por juicio, exhibición de documentos electrónicos, directivas de retención y etiquetas de retención. El uso de un conector de Cisco Jabber en Oracle para importar y archivar datos en Microsoft 365 puede ayudar a su organización a cumplir con las directivas gubernamentales y reglamentarias.

## <a name="overview-of-archiving-cisco-jabber-on-oracle-data"></a>Información general sobre cómo archivar datos de Cisco Jabber en Oracle

En la siguiente introducción se explica el proceso de uso de un conector para archivar los datos de Cisco Jabber en Oracle en Microsoft 365.

![Flujo de trabajo de archivado para datos de Cisco Jabber en Oracle.](../media/CiscoJabberOnOracleConnectorWorkflow.png)

1. Su organización trabaja con Cisco Jabber en Oracle para configurar y configurar un Cisco Jabber en un sitio de Oracle.

2. Una vez cada 24 horas, los elementos de Cisco Jabber en Oracle se copian en el sitio Veritas Merge1. El conector también convierte los elementos de Cisco Jabber en Oracle a un formato de mensaje de correo electrónico.

3. El conector de Cisco Jabber en Oracle que crea en el Centro de cumplimiento de Microsoft 365, se conecta al sitio Veritas Merge1 todos los días y transfiere el contenido de Jabber a una ubicación de Azure Storage segura en la nube de Microsoft.

4. El conector importa los elementos convertidos a los buzones de usuarios específicos mediante el valor de la propiedad *Email* de la asignación automática de usuarios, tal como se describe en [el paso 3](#step-3-map-users-and-complete-the-connector-setup). Se crea una subcarpeta en la carpeta Bandeja de entrada denominada **Cisco Jabber en Oracle** en los buzones de usuario y los elementos se importan a esa carpeta. El conector hace esto mediante el valor de la *propiedad Email.* Cada elemento de Jabber contiene esta propiedad, que se rellena con la dirección de correo electrónico de cada participante del elemento.

## <a name="before-you-begin"></a>Antes de empezar

- Crear una cuenta Merge1 para conectores de Microsoft. Para ello, póngase en contacto [con el Servicio de soporte al cliente de Veritas](https://www.veritas.com/content/support/en_US). Debe iniciar sesión en esta cuenta al crear el conector en el paso 1.

- El usuario que crea el conector de Cisco Jabber en Oracle en el paso 1 (y lo completa en el paso 3) debe estar asignado al rol De exportación de importación de buzones en Exchange Online. Este rol es necesario para agregar conectores en la **página Conectores de datos** de la Centro de cumplimiento de Microsoft 365. De forma predeterminada, este rol no se asigna a ningún grupo de roles en Exchange Online. Puede agregar el rol Exportación de importación de buzones al grupo de roles Administración de la organización en Exchange Online. O bien, puede crear un grupo de roles, asignar el rol Importación de buzones de correo Exportar y, a continuación, agregar los usuarios adecuados como miembros. Para obtener más información, vea [](/Exchange/permissions-exo/role-groups#modify-role-groups) las secciones [Crear](/Exchange/permissions-exo/role-groups#create-role-groups) grupos de roles o Modificar grupos de roles en el artículo "Administrar grupos de roles en Exchange Online".

- Este conector de datos de Veritas se encuentra en versión preliminar pública en GCC entornos de la Microsoft 365 us government cloud. Las aplicaciones y servicios de terceros pueden implicar almacenar, transmitir y procesar los datos de clientes de su organización en sistemas de terceros que están fuera de la infraestructura de Microsoft 365 y, por lo tanto, no están cubiertos por los compromisos de cumplimiento y protección de datos de Microsoft 365. Microsoft no hace ninguna representación de que el uso de este producto para conectarse a aplicaciones de terceros implica que esas aplicaciones de terceros son compatibles con FEDRAMP.

## <a name="step-1-set-up-the-cisco-jabber-on-oracle-connector"></a>Paso 1: Configurar el conector de Cisco Jabber en Oracle

El primer paso es obtener acceso a la página **Conectores** de datos en el Centro de cumplimiento de Microsoft 365 y crear un conector para los datos de Jabber.

1. Vaya a <https://compliance.microsoft.com> y, a continuación, haga clic **en Conectores de datos** Cisco  >  **Jabber en Oracle**.

2. En la **página Descripción del producto de Cisco Jabber en Oracle,** haga clic en Agregar **conector**.

3. En la **página Términos de** servicio, haga clic **en Aceptar**.

4. Escriba un nombre único que identifique el conector y, a continuación, haga clic en **Siguiente**.

5. Inicie sesión en su cuenta merge1 para configurar el conector.

## <a name="step-2-configure-the-cisco-jabber-on-oracle-on-the-veritas-merge1-site"></a>Paso 2: Configurar Cisco Jabber en Oracle en el sitio de Veritas Merge1

El segundo paso es configurar el conector de Cisco Jabber en Oracle en el sitio Veritas Merge1. Para obtener información sobre cómo configurar el conector de Cisco Jabber en Oracle, vea [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Cisco%20Jabber%20on%20Oracle%20User%20Guide.pdf).

Después de hacer clic en Guardar  & **finalizar**, se muestra la página Asignación de usuario en el asistente para conector en Centro de cumplimiento de Microsoft 365.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Paso 3: Asignar usuarios y completar la configuración del conector

Para asignar usuarios y completar la configuración del conector en el Centro de cumplimiento de Microsoft 365, siga estos pasos:

1. En la **página Asignar usuarios de Cisco Jabber en Oracle** a Microsoft 365 usuarios, habilite la asignación automática de usuarios. Los elementos de Cisco Jabber en Oracle incluyen una propiedad denominada *Email*, que contiene direcciones de correo electrónico para los usuarios de su organización. Si el conector puede asociar esta dirección a un Microsoft 365, los elementos se importan al buzón de ese usuario.

2. Haga **clic en** Siguiente, revise la configuración y, a continuación, vaya a la página **Conectores** de datos para ver el progreso del proceso de importación del nuevo conector.

## <a name="step-4-monitor-the-cisco-jabber-on-oracle-connector"></a>Paso 4: Supervisar el conector de Cisco Jabber en Oracle

Después de crear el conector de Cisco Jabber en Oracle, puede ver el estado del conector en el Centro de cumplimiento de Microsoft 365.

1. Vaya a <https://compliance.microsoft.com/> y haga clic en **Conectores de datos** en la navegación izquierda.

2. Haga clic en la **pestaña Conectores** y, a continuación, seleccione el conector **de Cisco Jabber en Oracle** para mostrar la página desplegable, que contiene las propiedades e información sobre el conector.

3. En **Estado del conector con origen,** haga clic en el vínculo Descargar **registro** para abrir (o guardar) el registro de estado del conector. Este registro contiene datos que se han importado a la nube de Microsoft.

## <a name="known-issues"></a>Problemas conocidos

- En este momento, no se admite la importación de datos adjuntos o elementos de más de 10 MB. La compatibilidad con elementos más grandes estará disponible en una fecha posterior.
