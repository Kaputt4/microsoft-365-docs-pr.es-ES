---
title: Configuración de un conector para archivar datos dinámicos en Microsoft 365
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
ms.collection: purview-compliance
description: Los administradores pueden configurar un conector para importar y archivar datos dinámicos de Veritas en Microsoft 365. Este conector le permite archivar datos de orígenes de datos de terceros en Microsoft 365 para que pueda usar características de cumplimiento como la suspensión legal, la búsqueda de contenido y las directivas de retención para administrar los datos de terceros de su organización.
ms.openlocfilehash: a083cc8cabe07eb21ea6168926bf6a3a590f6b15
ms.sourcegitcommit: ab45f2963e0635ff2cb9670f6f7b4c784f6a250e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2022
ms.locfileid: "68815273"
---
# <a name="set-up-a-connector-to-archive-pivot-data"></a>Configuración de un conector para archivar datos dinámicos

Use un conector de Veritas en el portal de cumplimiento Microsoft Purview para importar y archivar datos de la plataforma dinámica en buzones de usuario de la organización de Microsoft 365. Veritas proporciona un conector [dinámico](https://globanet.com/pivot/) que está configurado para capturar elementos del origen de datos de terceros (de forma regular) y, a continuación, importarlos a Microsoft 365. Pivot es una plataforma de mensajería instantánea que permite la colaboración con los participantes del mercado financiero. El conector convierte elementos como mensajes de chat, de las cuentas dinámicas de un usuario a un formato de mensaje de correo electrónico y, a continuación, importa esos elementos a los buzones de usuario de Microsoft 365.

Una vez almacenados los datos dinámicos en buzones de usuario, puede aplicar características de Microsoft Purview, como suspensión por juicio, exhibición de documentos electrónicos, directivas de retención y etiquetas de retención y cumplimiento de comunicaciones. El uso de un conector dinámico para importar y archivar datos en Microsoft 365 puede ayudar a su organización a cumplir las directivas gubernamentales y normativas.

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="overview-of-archiving-pivot-data"></a>Introducción al archivado de datos dinámicos

En la información general siguiente se explica el proceso de uso de un conector para archivar los datos dinámicos en Microsoft 365.

![Flujo de trabajo de archivado de datos dinámicos.](../media/PivotConnectorWorkflow.png)

1. Su organización funciona con Pivot para configurar y configurar un sitio de origen dinámico.

2. Una vez cada 24 horas, los elementos dinámicos se copian en el sitio Veritas Merge1. El conector también convierte los elementos dinámicos en un formato de mensaje de correo electrónico.

3. El conector dinámico que se crea en el portal de cumplimiento, se conecta al sitio Veritas Merge1 todos los días y transfiere los elementos dinámicos a una ubicación segura de Azure Storage en la nube de Microsoft.

4. El conector importa los elementos dinámicos a los buzones de usuarios específicos mediante el valor de la propiedad *Email* de la asignación automática de usuarios, tal como se describe en [el paso 3](#step-3-map-users-and-complete-the-connector-setup). Se crea una subcarpeta en la carpeta Bandeja de entrada denominada **Dinámica** en los buzones de usuario y los elementos se importan a esa carpeta. Para ello, el conector usa el valor de la propiedad *Email*. Cada elemento dinámico contiene esta propiedad, que se rellena con la dirección de correo electrónico de cada participante del elemento.

## <a name="before-you-begin"></a>Antes de empezar

- Cree una cuenta de Veritas Merge1 para los conectores de Microsoft. Para crear esta cuenta, póngase en contacto con [el servicio de atención al cliente de Veritas](https://www.veritas.com/content/support/). Iniciará sesión en esta cuenta al crear el conector en el paso 1.

- Al usuario que crea el conector dinámico en el paso 1 (y lo completa en el paso 3) se le debe asignar el rol Administración Conector de datos. Este rol es necesario para agregar conectores en la página **Conectores de datos** del portal de cumplimiento. Este rol se agrega de forma predeterminada a varios grupos de roles. Para obtener una lista de estos grupos de roles, consulte la sección "Roles en los portales de defender y cumplimiento" de [Roles y grupos de roles en los portales de cumplimiento de Microsoft 365 Defender y Microsoft Purview](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-defender-and-compliance-portals). Como alternativa, un administrador de su organización puede crear un grupo de roles personalizado, asignar el rol Administración conector de datos y, a continuación, agregar los usuarios adecuados como miembros. Para obtener instrucciones, consulte la sección "Crear un grupo de roles personalizado" en [Permisos en el portal de cumplimiento Microsoft Purview](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group).

- Este conector de datos de Veritas está en versión preliminar pública en entornos GCC en la nube de Microsoft 365 US Government. Las aplicaciones y servicios de terceros pueden implicar almacenar, transmitir y procesar los datos de clientes de su organización en sistemas de terceros que están fuera de la infraestructura de Microsoft 365 y, por lo tanto, no están cubiertos por los compromisos de protección de datos y Microsoft Purview. Microsoft no hace ninguna representación de que el uso de este producto para conectarse a aplicaciones de terceros implica que esas aplicaciones de terceros son compatibles con FEDRAMP.

## <a name="step-1-set-up-the-pivot-connector"></a>Paso 1: Configurar el conector dinámico

El primer paso consiste en acceder a la página **Conectores de datos** del Centro de cumplimiento de Microsoft y crear un conector para datos dinámicos.

1. Vaya a y, a [https://compliance.microsoft.com](https://compliance.microsoft.com/) continuación, seleccione Data connectors **Pivot (Dinámica** **de conectores** >  de datos).

2. En la página **Descripción** dinámica del producto, seleccione **Agregar conector**.

3. En la página **Términos de servicio** , seleccione **Aceptar**.

4. Escriba un nombre único que identifique el conector y, a continuación, seleccione **Siguiente**.

5. Inicie sesión en su cuenta de Merge1 para configurar el conector.

## <a name="step-2-configure-the-pivot-connector-on-the-veritas-merge1-site"></a>Paso 2: Configurar el conector dinámico en el sitio de Veritas Merge1

El segundo paso es configurar el conector dinámico en el sitio Merge1. Para obtener información sobre cómo configurar el conector dinámico en el sitio Veritas Merge1, vea [Merge1 Third-Party Connectors User Guide(Guía del usuario de conectores de terceros de Merge1](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Pivot%20User%20Guide%20.pdf)).

Después de seleccionar **Guardar & Finalizar**, se muestra la página **Asignación** de usuarios en el Asistente para conectores en el portal de cumplimiento.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Paso 3: Asignar usuarios y completar la configuración del conector

Para asignar usuarios y completar la configuración del conector en el Centro de cumplimiento de Microsoft 356, siga estos pasos:

1. En la página **Asignar usuarios dinámicos a usuarios de Microsoft 365** , habilite la asignación automática de usuarios. Los elementos dinámicos incluyen una propiedad denominada *Email*, que contiene direcciones de correo electrónico para los usuarios de la organización. Si el conector puede asociar esta dirección a un usuario de Microsoft 365, los elementos se importan al buzón de ese usuario.

2. Seleccione **Siguiente**, revise la configuración y vaya a la página **Conectores de datos** para ver el progreso del proceso de importación del nuevo conector.

## <a name="step-4-monitor-the-pivot-connector"></a>Paso 4: Supervisión del conector dinámico

Después de crear el conector dinámico, puede ver el estado del conector en el portal de cumplimiento.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com) y seleccione **Conectores de datos** en el panel de navegación izquierdo.

2. Seleccione la pestaña **Conectores** y, a continuación, seleccione el conector **dinámico** para mostrar la página de control flotante. Esta página contiene las propiedades y la información sobre el conector.

3. En **Estado del conector con origen**, seleccione el vínculo **Descargar registro** para abrir (o guardar) el registro de estado del conector. Este registro contiene información sobre los datos que se han importado a la nube de Microsoft. Para obtener más información, consulte [Visualización de registros de administración para conectores de datos](data-connector-admin-logs.md).

## <a name="known-issues"></a>Problemas conocidos

- En este momento, no se admiten la importación de datos adjuntos o elementos que superen los 10 MB. La compatibilidad con elementos más grandes estará disponible en una fecha posterior.
