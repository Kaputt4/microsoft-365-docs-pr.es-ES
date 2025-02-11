---
title: Configuración de un conector para archivar Skype Empresarial datos en Microsoft 365
description: Obtenga información sobre cómo configurar y usar un conector en el portal de cumplimiento Microsoft Purview para importar y archivar datos de Skype Empresarial a Microsoft 365.
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
ms.openlocfilehash: aeefa9ca1d60c7892e9831c9f7cae4e5c12685b0
ms.sourcegitcommit: ab45f2963e0635ff2cb9670f6f7b4c784f6a250e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2022
ms.locfileid: "68811841"
---
# <a name="set-up-a-connector-to-archive-skype-for-business-data"></a>Configuración de un conector para archivar datos Skype Empresarial

Use un conector de Veritas en la portal de cumplimiento Microsoft Purview para importar y archivar datos de la plataforma de Skype Empresarial a buzones de usuario de la organización de Microsoft 365. Veritas proporciona un conector [de Skype Empresarial](https://www.veritas.com/en/au/insights/merge1/skype-for-business) que está configurado para capturar elementos del origen de datos de terceros (de forma periódica) e importarlos a Microsoft 365. El conector convierte el contenido, como mensajes entre usuarios, chats persistentes y mensajes de conferencia de Skype Empresarial a un formato de mensaje de correo electrónico y, a continuación, importa esos elementos al buzón del usuario en Microsoft 365.

Después de Skype Empresarial datos se almacenan en buzones de usuario, puede aplicar características de Microsoft Purview como suspensión por juicio, exhibición de documentos electrónicos, directivas de retención y etiquetas de retención. El uso de un conector de Skype Empresarial para importar y archivar datos en Microsoft 365 puede ayudar a su organización a cumplir las directivas gubernamentales y normativas.

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="overview-of-archiving-skype-for-business-data"></a>Introducción al archivado de datos Skype Empresarial

En la información general siguiente se explica el proceso de uso de un conector para archivar los datos de Skype Empresarial en Microsoft 365.

![Flujo de trabajo de archivado de datos de Skype Empresarial.](../media/SkypeforBusinessConnectorWorkflow.png)

1. Su organización trabaja con Skype Empresarial para configurar y configurar un sitio de Skype Empresarial.

2. Una vez cada 24 horas, Skype Empresarial elementos se copian en el sitio de Veritas Merge1. El conector también convierte Skype Empresarial elementos en un formato de mensaje de correo electrónico.

3. El conector Skype Empresarial que se crea en el portal de cumplimiento, se conecta al sitio de Veritas Merge1 todos los días y transfiere el contenido Skype Empresarial a una ubicación segura de Azure Storage en la nube de Microsoft.

4. El conector importa los elementos convertidos a los buzones de usuarios específicos mediante el valor de la propiedad *Email* de la asignación automática de usuarios, tal como se describe en [el paso 3](#step-3-map-users-and-complete-the-connector-setup). Se crea una subcarpeta de la carpeta Bandeja de entrada denominada **Skype Empresarial** en los buzones de usuario y los elementos se importan a esa carpeta. Para ello, el conector usa el valor de la propiedad *Email*. Cada elemento Skype Empresarial contiene esta propiedad, que se rellena con la dirección de correo electrónico de cada participante del elemento.

## <a name="before-you-set-up-a-connector"></a>Antes de configurar un conector

- Cree una cuenta de Merge1 para los conectores de Microsoft. Para ello, póngase en contacto con [el servicio de atención al cliente de Veritas](https://www.veritas.com/form/requestacall/ms-connectors-contact.html). Debe iniciar sesión en esta cuenta al crear el conector en el paso 1.

- Al usuario que crea el conector de Skype Empresarial en el paso 1 (y lo completa en el paso 3) se le debe asignar el rol Administración Conector de datos. Este rol es necesario para agregar conectores en la página **Conectores de datos** del portal de cumplimiento. Este rol se agrega de forma predeterminada a varios grupos de roles. Para obtener una lista de estos grupos de roles, consulte la sección "Roles en los portales de defender y cumplimiento" de [Roles y grupos de roles en los portales de cumplimiento de Microsoft 365 Defender y Microsoft Purview](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-defender-and-compliance-portals). Como alternativa, un administrador de su organización puede crear un grupo de roles personalizado, asignar el rol Administración conector de datos y, a continuación, agregar los usuarios adecuados como miembros. Para obtener instrucciones, consulte la sección "Crear un grupo de roles personalizado" en [Permisos en el portal de cumplimiento Microsoft Purview](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group).

- Este conector de datos de Veritas está en versión preliminar pública en entornos GCC en la nube de Microsoft 365 US Government. Las aplicaciones y servicios de terceros pueden implicar almacenar, transmitir y procesar los datos de clientes de su organización en sistemas de terceros que están fuera de la infraestructura de Microsoft 365 y, por lo tanto, no están cubiertos por los compromisos de protección de datos y Microsoft Purview. Microsoft no hace ninguna representación de que el uso de este producto para conectarse a aplicaciones de terceros implica que esas aplicaciones de terceros son compatibles con FEDRAMP.

## <a name="step-1-set-up-the-skype-for-business-connector"></a>Paso 1: Configurar el conector de Skype Empresarial

El primer paso consiste en acceder a la página **Conectores de datos** del portal de cumplimiento y crear un conector para Skype Empresarial datos.

1. Vaya a <https://compliance.microsoft.com> y seleccione **Conectores** >  **de datos Skype Empresarial**.

2. En la página **Skype Empresarial** descripción del producto, seleccione **Agregar conector**.

3. En la página **Términos de servicio** , seleccione **Aceptar**.

4. Escriba un nombre único que identifique el conector y, a continuación, seleccione **Siguiente**.

5. Inicie sesión en su cuenta de Merge1 para configurar el conector.

## <a name="step-2-configure-the-skype-for-business-on-the-veritas-merge1-site"></a>Paso 2: Configurar el Skype Empresarial en el sitio de Veritas Merge1

El segundo paso es configurar el conector de Skype Empresarial en el sitio de Veritas Merge1. Para obtener información sobre cómo configurar el conector de Skype Empresarial, consulte [la Guía del usuario de conectores de terceros Merge1](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Skype%20for%20Business%20%20User%20Guide.pdf).

Después de seleccionar **Guardar & Finalizar**, se muestra la página **Asignación** de usuarios en el Asistente para conectores en el portal de cumplimiento.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Paso 3: Asignar usuarios y completar la configuración del conector

Para asignar usuarios y completar la configuración del conector en el portal de cumplimiento, siga estos pasos:

1. En la página **Asignar usuarios Skype Empresarial a usuarios de Microsoft 365**, habilite la asignación automática de usuarios. Los elementos Skype Empresarial incluyen una propiedad denominada *Email*, que contiene direcciones de correo electrónico para los usuarios de la organización. Si el conector puede asociar esta dirección a un usuario de Microsoft 365, los elementos se importan al buzón de ese usuario.

2. Seleccione **Siguiente**, revise la configuración y, a continuación, vaya a la página **Conectores de datos** para ver el progreso del proceso de importación del nuevo conector.

## <a name="step-4-monitor-the-skype-for-business-connector"></a>Paso 4: Supervisión del conector de Skype Empresarial

Después de crear el conector de Skype Empresarial, puede ver el estado del conector en el portal de cumplimiento.

1. Vaya a <https://compliance.microsoft.com/> y seleccione **Conectores de datos** en el panel de navegación izquierdo.

2. Seleccione la pestaña **Conectores** y, a continuación, seleccione el conector **Skype Empresarial** para mostrar la página de control flotante, que contiene las propiedades y la información sobre el conector.

3. En **Estado del conector con origen**, seleccione el vínculo **Descargar registro** para abrir (o guardar) el registro de estado del conector. Este registro contiene información sobre los datos que se han importado a la nube de Microsoft. Para obtener más información, consulte [Visualización de registros de administración para conectores de datos](data-connector-admin-logs.md).

## <a name="known-issues"></a>Problemas conocidos

- En este momento, no se admiten la importación de datos adjuntos o elementos que superen los 10 MB. La compatibilidad con elementos más grandes estará disponible en una fecha posterior.
