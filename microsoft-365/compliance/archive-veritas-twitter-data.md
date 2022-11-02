---
title: Configuración de un conector para archivar datos de Twitter en Microsoft 365
description: Los administradores pueden configurar un conector para importar y archivar datos de Twitter desde Veritas a Microsoft 365. Este conector le permite archivar datos de orígenes de datos de terceros en Microsoft 365. Después de archivar estos datos, puede usar características de cumplimiento como la suspensión legal, la exhibición de documentos electrónicos y las directivas de retención para administrar datos de terceros.
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
ms.openlocfilehash: d46b60dd355200e16cb65e90ae7c200b979ad3e7
ms.sourcegitcommit: ab45f2963e0635ff2cb9670f6f7b4c784f6a250e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2022
ms.locfileid: "68813311"
---
# <a name="set-up-a-connector-to-archive-twitter-data-preview"></a>Configuración de un conector para archivar datos de Twitter (versión preliminar)

Use un conector de Veritas en la portal de cumplimiento Microsoft Purview para importar y archivar datos de la plataforma twitter a buzones de usuario de su organización de Microsoft 365. Veritas proporciona un conector de [Twitter](https://www.veritas.com/insights/merge1/twitter) configurado para capturar elementos de un origen de datos de terceros e importarlos a Microsoft 365. El conector convierte contenido como tweets, retweets y comentarios de Twitter en un formato de mensaje de correo electrónico y, a continuación, importa esos elementos a los buzones de usuario de Microsoft 365.

Una vez que los datos de Twitter se almacenan en buzones de usuario, puede aplicar características de Microsoft Purview como suspensión por juicio, exhibición de documentos electrónicos, directivas de retención y etiquetas de retención. El uso de un conector de Twitter para importar y archivar datos en Microsoft 365 puede ayudar a su organización a cumplir las directivas gubernamentales y normativas.

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="overview-of-archiving-twitter-data"></a>Información general sobre el archivado de datos de Twitter

En la información general siguiente se explica el proceso de uso de un conector para archivar los datos de Twitter en Microsoft 365.

![Flujo de trabajo de archivado de datos de Twitter.](../media/VeritasTwitterConnectorWorkflow.png)

1. Su organización funciona con Twitter para configurar y configurar un sitio de Twitter. Su organización también trabaja con Veritas para configurar un sitio merge1.

2. Cada 24 horas, los elementos de Twitter se copian en el sitio de Veritas Merge1. El conector también convierte los elementos de Twitter en un formato de mensaje de correo electrónico.

3. El conector de Twitter que se crea en el portal de cumplimiento se conecta al sitio Veritas Merge1 todos los días y transfiere el contenido de Twitter a una ubicación segura de Azure Storage en la nube de Microsoft.

4. El conector importa los elementos convertidos a los buzones de usuarios específicos mediante el valor de la propiedad *Email* de la asignación automática de usuarios, tal como se describe en [el paso 3](#step-3-map-users-and-complete-the-connector-setup). Se crea una subcarpeta en la carpeta Bandeja de entrada denominada **Twitter** en los buzones de usuario y los elementos se importan a esa carpeta. El conector determina a qué buzón se van a importar elementos mediante el valor de la propiedad *Email*. Cada elemento de Twitter contiene esta propiedad, que se rellena con la dirección de correo electrónico de cada participante del elemento.

## <a name="before-you-set-up-a-connector"></a>Antes de configurar un conector

- Cree una cuenta de Merge1 para los conectores de Microsoft. Para crear esta cuenta, póngase en contacto con [el servicio de atención al cliente de Veritas](https://www.veritas.com/form/requestacall/ms-connectors-contact). Debe iniciar sesión en esta cuenta al crear el conector en el paso 1.

- Cree una aplicación de Twitter en <https://developer.twitter.com> para capturar datos de su cuenta de Twitter. Para obtener instrucciones paso a paso sobre cómo crear la aplicación, consulte [La Guía del usuario de conectores de terceros Merge1](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Twitter%20User%20Guide.pdf).

- Al usuario que crea el conector de YouTube en el paso 1 (y lo completa en el paso 3) se le debe asignar el rol Administración Conector de datos. Este rol es necesario para agregar conectores en la página **Conectores de datos** del portal de cumplimiento. Este rol se agrega de forma predeterminada a varios grupos de roles. Para obtener una lista de estos grupos de roles, consulte la sección "Roles en los portales de defender y cumplimiento" de [Roles y grupos de roles en los portales de cumplimiento de Microsoft 365 Defender y Microsoft Purview](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-defender-and-compliance-portals). Como alternativa, un administrador de su organización puede crear un grupo de roles personalizado, asignar el rol Administración conector de datos y, a continuación, agregar los usuarios adecuados como miembros. Para obtener instrucciones, consulte la sección "Crear un grupo de roles personalizado" en [Permisos en el portal de cumplimiento Microsoft Purview](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group).

- Este conector de datos de Veritas está en versión preliminar pública en entornos GCC en la nube de Microsoft 365 US Government. Las aplicaciones y servicios de terceros pueden implicar almacenar, transmitir y procesar los datos de clientes de su organización en sistemas de terceros que están fuera de la infraestructura de Microsoft 365 y, por lo tanto, no están cubiertos por los compromisos de protección de datos y Microsoft Purview. Microsoft no hace ninguna representación de que el uso de este producto para conectarse a aplicaciones de terceros implica que esas aplicaciones de terceros son compatibles con FEDRAMP.

## <a name="step-1-set-up-the-twitter-connector"></a>Paso 1: Configurar el conector de Twitter

El primer paso consiste en acceder a la página **Conectores de datos** del portal de cumplimiento y crear un conector para los datos de Twitter.

1. Vaya a y, a <https://compliance.microsoft.com> continuación, seleccione **Conectores** >  de **datos en Twitter**.

2. En la página Descripción del producto de **Twitter** , seleccione **Agregar conector**.

3. En la página **Términos de servicio** , seleccione **Aceptar**.

4. Escriba un nombre único que identifique el conector y, a continuación, seleccione **Siguiente**.

5. Inicie sesión en su cuenta de Merge1 para configurar el conector.

## <a name="step-2-configure-the-twitter-on-the-veritas-merge1-site"></a>Paso 2: Configuración de Twitter en el sitio de Veritas Merge1

El segundo paso es configurar el conector de Twitter en el sitio de Veritas Merge1. Para obtener información sobre cómo configurar el conector de Twitter, consulte [la Guía del usuario de conectores de terceros Merge1](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Twitter%20User%20Guide.pdf).

Después de seleccionar **Guardar & finalizar,** se muestra la página **Asignación** de usuarios en el asistente del conector en el portal de cumplimiento.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Paso 3: Asignar usuarios y completar la configuración del conector

Para asignar usuarios y completar la configuración del conector en el portal de cumplimiento, siga estos pasos:

1. En la página **Asignar usuarios de Twitter a usuarios de Microsoft 365** , habilite la asignación automática de usuarios. Los elementos de Twitter incluyen una propiedad denominada *Email*, que contiene direcciones de correo electrónico para los usuarios de la organización. Si el conector puede asociar esta dirección a un usuario de Microsoft 365, los elementos se importan al buzón de ese usuario.

2. Seleccione **Siguiente**, revise la configuración y, a continuación, vaya a la página **Conectores de datos** para ver el progreso del proceso de importación del nuevo conector.

## <a name="step-4-monitor-the-twitter-connector"></a>Paso 4: Supervisión del conector de Twitter

Después de crear el conector de Twitter, puede ver el estado del conector en el portal de cumplimiento.

1. Vaya a <https://compliance.microsoft.com/> y seleccione **Conectores de datos** en el panel de navegación izquierdo.

2. Seleccione la pestaña **Conectores** y, a continuación, seleccione el conector de **Twitter** para mostrar la página de control flotante, que contiene las propiedades y la información sobre el conector.

3. En **Estado del conector con origen**, seleccione el vínculo **Descargar registro** para abrir (o guardar) el registro de estado del conector. Este registro contiene información sobre los datos que se han importado a la nube de Microsoft. Para obtener más información, consulte [Visualización de registros de administración para conectores de datos](data-connector-admin-logs.md).

## <a name="known-issues"></a>Problemas conocidos

- En este momento, no se admiten la importación de datos adjuntos o elementos que superen los 10 MB. La compatibilidad con elementos más grandes estará disponible en una fecha posterior.
