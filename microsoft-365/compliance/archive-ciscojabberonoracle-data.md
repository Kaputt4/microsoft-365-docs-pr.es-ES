---
title: Configurar un conector para archivar los datos de Cisco Jabber en Oracle en Microsoft 365
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
description: Aprenda a configurar y usar un conector en el portal de cumplimiento de Microsoft Purview para importar y archivar datos de Cisco Jabber en Oracle para Microsoft 365.
ms.openlocfilehash: 7668defd3ef7157da185de7e51ef97e3127e67a4
ms.sourcegitcommit: 52eea2b65c0598ba4a1b930c58b42dbe62cdaadc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/19/2022
ms.locfileid: "64946690"
---
# <a name="set-up-a-connector-to-archive-cisco-jabber-on-oracle-data"></a>Configuración de un conector para archivar Cisco Jabber en datos de Oracle

Use un conector veritas en el portal de cumplimiento de Microsoft Purview para importar y archivar datos de la plataforma Cisco Jabber en Oracle a los buzones de usuario de su organización Microsoft 365. Veritas proporciona un [conector Cisco Jabber en Oracle](https://www.veritas.com/insights/merge1/jabber) que está configurado para capturar elementos del origen de datos de terceros (de forma regular) e importar esos elementos a Microsoft 365. El conector convierte el contenido como archivos y operaciones de archivos, comentarios y contenido compartido de Cisco Jabber en Oracle a un formato de mensaje de correo electrónico y, a continuación, importa esos elementos al buzón del usuario en Microsoft 365.

Después de que cisco Jabber en los datos de Oracle se almacena en los buzones de usuario, usted puede aplicar las características de Microsoft Purview tales como la suspensión por juicio, eDiscovery, las directivas de retención y las etiquetas de retención. El uso de un conector Cisco Jabber en Oracle para importar y archivar datos en Microsoft 365 puede ayudar a su organización a cumplir con las directivas gubernamentales y reglamentarias.

## <a name="overview-of-archiving-cisco-jabber-on-oracle-data"></a>Introducción al archivado de Cisco Jabber en datos de Oracle

La siguiente información general explica el proceso de uso de un conector para archivar el Cisco Jabber en los datos de Oracle en Microsoft 365.

![Flujo de trabajo de archivado de Cisco Jabber en datos de Oracle.](../media/CiscoJabberOnOracleConnectorWorkflow.png)

1. Su organización trabaja con Cisco Jabber en Oracle para configurar un Cisco Jabber en el sitio de Oracle.

2. Una vez cada 24 horas, los elementos del Cisco Jabber en Oracle se copian en el sitio de Veritas Merge1. El conector también convierte cisco jabber en los elementos de Oracle a un formato de mensaje de correo electrónico.

3. Cisco Jabber en el conector de Oracle que usted crea en el portal de cumplimiento, conecta con el sitio de Veritas Merge1 cada día y transfiere el contenido del Jabber a una ubicación segura Azure Storage en la nube de Microsoft.

4. El conector importa los elementos convertidos a los buzones de usuarios específicos mediante el valor de la propiedad *Email* de la asignación automática de usuarios, tal como se describe en [el paso 3](#step-3-map-users-and-complete-the-connector-setup). Se crea una subcarpeta en la carpeta Bandeja de entrada denominada **Cisco Jabber en Oracle** en los buzones de usuario, y los elementos se importan a esa carpeta. Para ello, el conector usa el valor de la propiedad *Email* . Cada elemento jabber contiene esta propiedad, que se rellena con la dirección de correo electrónico de cada participante del elemento.

## <a name="before-you-begin"></a>Antes de empezar

- Cree una cuenta de Merge1 para los conectores de Microsoft. Para ello, póngase en contacto con [el servicio de atención al cliente de Veritas](https://www.veritas.com/content/support/en_US). Debe iniciar sesión en esta cuenta al crear el conector en el paso 1.

- El usuario que crea el Cisco Jabber en el conector de Oracle en el paso 1 (y lo completa en el paso 3) debe ser asignado el rol de administrador del conector de datos. Este rol es necesario para agregar conectores en la página **Conectores de datos** del portal de cumplimiento. Este rol se agrega de forma predeterminada a varios grupos de roles. Para obtener una lista de estos grupos de roles, consulte la sección "Roles en los centros de seguridad y cumplimiento" de [Permisos en el Centro de cumplimiento de & seguridad](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center). Como alternativa, un administrador de su organización puede crear un grupo de roles personalizado, asignar el rol Administrador del conector de datos y, a continuación, agregar los usuarios adecuados como miembros. Para obtener instrucciones, consulte la sección "Crear un grupo de roles personalizado" en [Permisos en el portal de cumplimiento de Microsoft Purview](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group).

- Este conector de datos de Veritas está en versión preliminar pública en entornos de GCC en la nube Microsoft 365 administración pública de EE. UU. Las aplicaciones y servicios de terceros pueden implicar almacenar, transmitir y procesar los datos de clientes de su organización en sistemas de terceros que están fuera de la infraestructura de Microsoft 365 y, por tanto, no están cubiertos por los compromisos de protección de datos y Microsoft Purview. Microsoft no hace ninguna representación de que el uso de este producto para conectarse a aplicaciones de terceros implica que esas aplicaciones de terceros son compatibles con FEDRAMP.

## <a name="step-1-set-up-the-cisco-jabber-on-oracle-connector"></a>Paso 1: Configurar el Cisco Jabber en el conector de Oracle

El primer paso es acceder a la página **Conectores de datos** en el portal de cumplimiento y crear un conector para los datos del Jabber.

1. Vaya a <https://compliance.microsoft.com> y haga clic en **Conectores** >  de **datosCisco Jabber en Oracle**.

2. En la página de descripción del producto **Cisco Jabber on Oracle** , haga clic en **Agregar conector**.

3. En la página **Términos de servicio** , haga clic en **Aceptar**.

4. Escriba un nombre único que identifique el conector y, a continuación, haga clic en **Siguiente**.

5. Inicie sesión en su cuenta de Merge1 para configurar el conector.

## <a name="step-2-configure-the-cisco-jabber-on-oracle-on-the-veritas-merge1-site"></a>Paso 2: Configurar el Cisco Jabber en Oracle en el sitio de Veritas Merge1

El segundo paso es configurar cisco jabber en el conector de Oracle en el sitio de Veritas Merge1. Para obtener información sobre cómo configurar cisco jabber en el conector de Oracle, vea [la guía del usuario de los conectores de terceros merge1](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Cisco%20Jabber%20on%20Oracle%20User%20Guide.pdf).

Después de hacer clic en **Guardar & finalizar**, se muestra la página **Asignación** de usuarios del asistente del conector en el portal de cumplimiento.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Paso 3: Asignar usuarios y completar la configuración del conector

Para asignar usuarios y completar la configuración del conector en el portal de cumplimiento, siga estos pasos:

1. En el **Cisco Jabber del mapa en los usuarios de Oracle para Microsoft 365 página de los usuarios**, habilite la asignación automática de usuarios. El Jabber de Cisco en los elementos de Oracle incluye una propiedad llamada *Correo electrónico*, que contiene direcciones de correo electrónico para los usuarios de su organización. Si el conector puede asociar esta dirección a un usuario Microsoft 365, los elementos se importan al buzón de ese usuario.

2. Haga clic en **Siguiente**, revise la configuración y, a continuación, vaya a la página **Conectores de datos** para ver el progreso del proceso de importación del nuevo conector.

## <a name="step-4-monitor-the-cisco-jabber-on-oracle-connector"></a>Paso 4: Supervisión del Cisco Jabber en el conector de Oracle

Después de crear cisco jabber en el conector de Oracle, usted puede ver el estado del conector en el portal de cumplimiento.

1. Vaya a <https://compliance.microsoft.com/> y haga clic en **Conectores de datos** en el panel de navegación izquierdo.

2. Haga clic en la pestaña **Conectores** y, después, seleccione cisco **jabber en** el conector de Oracle para mostrar la página de control flotante, que contiene las propiedades y la información sobre el conector.

3. En **Estado del conector con origen**, haga clic en el vínculo **Descargar registro** para abrir (o guardar) el registro de estado del conector. Este registro contiene datos que se han importado a la nube de Microsoft.

## <a name="known-issues"></a>Problemas conocidos

- En este momento, no se admiten la importación de datos adjuntos o elementos que superen los 10 MB. La compatibilidad con elementos más grandes estará disponible en una fecha posterior.
