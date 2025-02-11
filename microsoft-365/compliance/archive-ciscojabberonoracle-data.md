---
title: Configuración de un conector para archivar los datos de Cisco Jabber en Oracle en Microsoft 365
description: Aprenda a configurar y usar un conector en el portal de cumplimiento Microsoft Purview para importar y archivar datos de Cisco Jabber en Oracle a Microsoft 365.
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
ms.openlocfilehash: f34907d68322a6de05a6fbb681cbb68143d6db81
ms.sourcegitcommit: ab45f2963e0635ff2cb9670f6f7b4c784f6a250e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2022
ms.locfileid: "68812265"
---
# <a name="set-up-a-connector-to-archive-cisco-jabber-on-oracle-data"></a>Configuración de un conector para archivar Cisco Jabber en datos de Oracle

Use un conector veritas en el portal de cumplimiento Microsoft Purview para importar y archivar datos de la plataforma Cisco Jabber en Oracle a los buzones de usuario de su organización de Microsoft 365. Veritas proporciona un conector [Cisco Jabber en Oracle](https://www.veritas.com/insights/merge1/jabber) que está configurado para capturar elementos del origen de datos de terceros (de forma regular) e importar esos elementos a Microsoft 365. El conector convierte el contenido como archivos y operaciones de archivos, comentarios y contenido compartido de Cisco Jabber en Oracle a un formato de mensaje de correo electrónico y, a continuación, importa esos elementos al buzón del usuario en Microsoft 365.

Después de que cisco Jabber en los datos de Oracle se almacena en los buzones de usuario, usted puede aplicar las características de Microsoft Purview tales como la suspensión por juicio, eDiscovery, las directivas de retención y las etiquetas de retención. El uso de un conector Cisco Jabber en Oracle para importar y archivar datos en Microsoft 365 puede ayudar a su organización a cumplir las directivas gubernamentales y normativas.

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="overview-of-archiving-cisco-jabber-on-oracle-data"></a>Introducción al archivado de Cisco Jabber en datos de Oracle

En la información general siguiente se explica el proceso de uso de un conector para archivar los datos de Cisco Jabber en Oracle en Microsoft 365.

![Flujo de trabajo de archivado de Cisco Jabber en datos de Oracle.](../media/CiscoJabberOnOracleConnectorWorkflow.png)

1. Su organización trabaja con Cisco Jabber en Oracle para configurar un Cisco Jabber en el sitio de Oracle.

2. Una vez cada 24 horas, los elementos del Cisco Jabber en Oracle se copian en el sitio de Veritas Merge1. El conector también convierte cisco jabber en los elementos de Oracle a un formato de mensaje de correo electrónico.

3. El conector Cisco Jabber on Oracle que se crea en el portal de cumplimiento, se conecta al sitio de Veritas Merge1 todos los días y transfiere el contenido del Jabber a una ubicación segura de Azure Storage en la nube de Microsoft.

4. El conector importa los elementos convertidos a los buzones de usuarios específicos mediante el valor de la propiedad *Email* de la asignación automática de usuarios, tal como se describe en [el paso 3](#step-3-map-users-and-complete-the-connector-setup). Se crea una subcarpeta en la carpeta Bandeja de entrada denominada **Cisco Jabber en Oracle** en los buzones de usuario, y los elementos se importan a esa carpeta. Para ello, el conector usa el valor de la propiedad *Email*. Cada elemento jabber contiene esta propiedad, que se rellena con la dirección de correo electrónico de cada participante del elemento.

## <a name="before-you-begin"></a>Antes de empezar

- Cree una cuenta de Merge1 para los conectores de Microsoft. Para ello, póngase en contacto con [el servicio de atención al cliente de Veritas](https://www.veritas.com/content/support/en_US). Debe iniciar sesión en esta cuenta al crear el conector en el paso 1.

- El usuario que crea el Cisco Jabber en el conector de Oracle en el paso 1 (y lo completa en el paso 3) debe ser asignado el rol Administración del conector de datos. Este rol es necesario para agregar conectores en la página **Conectores de datos** del portal de cumplimiento. Este rol se agrega de forma predeterminada a varios grupos de roles. Para obtener una lista de estos grupos de roles, consulte la sección "Roles en los portales de defender y cumplimiento" de [Roles y grupos de roles en los portales de cumplimiento de Microsoft 365 Defender y Microsoft Purview](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-defender-and-compliance-portals). Como alternativa, un administrador de su organización puede crear un grupo de roles personalizado, asignar el rol Administración conector de datos y, a continuación, agregar los usuarios adecuados como miembros. Para obtener instrucciones, consulte la sección "Crear un grupo de roles personalizado" en [Permisos en el portal de cumplimiento Microsoft Purview](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group).

- Este conector de datos de Veritas está en versión preliminar pública en entornos GCC en la nube de Microsoft 365 US Government. Las aplicaciones y servicios de terceros pueden implicar almacenar, transmitir y procesar los datos de clientes de su organización en sistemas de terceros que están fuera de la infraestructura de Microsoft 365 y, por lo tanto, no están cubiertos por los compromisos de protección de datos y Microsoft Purview. Microsoft no hace ninguna representación de que el uso de este producto para conectarse a aplicaciones de terceros implica que esas aplicaciones de terceros son compatibles con FEDRAMP.

## <a name="step-1-set-up-the-cisco-jabber-on-oracle-connector"></a>Paso 1: Configurar el Cisco Jabber en el conector de Oracle

El primer paso es acceder a la página **Conectores de datos** en el portal de cumplimiento y crear un conector para los datos del Jabber.

1. Vaya a <https://compliance.microsoft.com> y después seleccione Los **conectores** >  de datos **Cisco Jabber en Oracle**.

2. En la página de descripción del producto **Del Jabber de Cisco en Oracle** , seleccione **Agregar conector**.

3. En la página **Términos de servicio** , seleccione **Aceptar**.

4. Escriba un nombre único que identifique el conector y, a continuación, seleccione **Siguiente**.

5. Inicie sesión en su cuenta de Merge1 para configurar el conector.

## <a name="step-2-configure-the-cisco-jabber-on-oracle-on-the-veritas-merge1-site"></a>Paso 2: Configurar el Cisco Jabber en Oracle en el sitio de Veritas Merge1

El segundo paso es configurar cisco jabber en el conector de Oracle en el sitio de Veritas Merge1. Para obtener información sobre cómo configurar cisco jabber en el conector de Oracle, vea [la guía del usuario de los conectores de terceros merge1](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Cisco%20Jabber%20on%20Oracle%20User%20Guide.pdf).

Después de seleccionar **Guardar & Finalizar**, se muestra la página **Asignación** de usuarios en el Asistente para conectores en el portal de cumplimiento.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Paso 3: Asignar usuarios y completar la configuración del conector

Para asignar usuarios y completar la configuración del conector en el portal de cumplimiento, siga estos pasos:

1. En la página **Asignar Cisco Jabber en Oracle a los usuarios de Microsoft 365** , habilite la asignación automática de usuarios. El Jabber de Cisco en los elementos de Oracle incluye una propiedad llamada *Email*, que contiene direcciones de correo electrónico para los usuarios de su organización. Si el conector puede asociar esta dirección a un usuario de Microsoft 365, los elementos se importan al buzón de ese usuario.

2. Seleccione **Siguiente**, revise la configuración y, a continuación, vaya a la página **Conectores de datos** para ver el progreso del proceso de importación del nuevo conector.

## <a name="step-4-monitor-the-cisco-jabber-on-oracle-connector"></a>Paso 4: Supervisión del Cisco Jabber en el conector de Oracle

Después de crear cisco jabber en el conector de Oracle, usted puede ver el estado del conector en el portal de cumplimiento.

1. Vaya a <https://compliance.microsoft.com/> y seleccione **Conectores de datos** en el panel de navegación izquierdo.

2. Seleccione la pestaña **Conectores** y, después, seleccione el conector **Cisco Jabber on Oracle** para mostrar la página de control flotante, que contiene las propiedades y la información sobre el conector.

3. En **Estado del conector con origen**, seleccione el vínculo **Descargar registro** para abrir (o guardar) el registro de estado del conector. Este registro contiene información sobre los datos que se han importado a la nube de Microsoft. Para obtener más información, consulte [Visualización de registros de administración para conectores de datos](data-connector-admin-logs.md).

## <a name="known-issues"></a>Problemas conocidos

- En este momento, no se admiten la importación de datos adjuntos o elementos que superen los 10 MB. La compatibilidad con elementos más grandes estará disponible en una fecha posterior.
