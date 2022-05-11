---
title: Configurar un conector para archivar los datos de Symphony en Microsoft 365
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
description: Los administradores pueden configurar un conector para importar y archivar datos de Veritas Symphony en Microsoft 365. Este conector le permite archivar datos de orígenes de datos de terceros en Microsoft 365. Después de archivar estos datos, puede usar características de cumplimiento como la suspensión legal, la búsqueda de contenido y las directivas de retención para administrar datos de terceros.
ms.openlocfilehash: e9be8d28879c636f2cba9104bc5a5f7fa29eed2f
ms.sourcegitcommit: 7dc7e9fd76adf848f941919f86ca25eecc704015
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2022
ms.locfileid: "65319680"
---
# <a name="set-up-a-connector-to-archive-symphony-data"></a>Configuración de un conector para archivar datos de Symphony

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

Use un conector veritas en el portal de cumplimiento Microsoft Purview para importar y archivar datos de Symphony en buzones de correo de usuario de la organización de Microsoft 365. Symphony es una plataforma de mensajería y colaboración utilizada en la industria de servicios financieros. Veritas proporciona un conector de datos [symphony](https://globanet.com/symphony) en el portal de cumplimiento que puede configurar para capturar elementos del origen de datos de terceros (de forma periódica) y, a continuación, importar esos elementos a buzones de usuario. El conector convierte el contenido de un elemento de la cuenta de Symphony en un formato de mensaje de correo electrónico y, a continuación, importa el elemento a un buzón de Microsoft 365.

Después de almacenar las comunicaciones de Symphony en buzones de usuario, puede aplicar Microsoft Purview características como suspensión por juicio, exhibición de documentos electrónicos, directivas de retención y etiquetas de retención y cumplimiento de comunicaciones. El uso de un conector symphony para importar y archivar datos en Microsoft 365 puede ayudar a su organización a cumplir las directivas gubernamentales y normativas.

## <a name="overview-of-archiving-symphony-data"></a>Introducción al archivado de datos de Symphony

En la información general siguiente se explica el proceso de uso de un conector de datos para archivar las comunicaciones sinfónicas en Microsoft 365.

![Flujo de trabajo de archivado sinfónico.](../media/SymphonyConnectorWorkflow.png)

1. Su organización trabaja con Symphony para configurar y configurar un sitio sinfónico.

2. Una vez cada 24 horas, los mensajes de chat de Symphony se copian en el sitio de Veritas Merge1. El conector también convierte el contenido de un mensaje de chat en un formato de mensaje de correo electrónico.

3. El conector de Symphony que se crea en el portal de cumplimiento, se conecta al sitio de Veritas Merge1 todos los días y transfiere los mensajes a una ubicación de Azure Storage segura en la nube de Microsoft.

4. El conector importa los elementos de mensaje convertidos a los buzones de usuarios específicos mediante el valor de la propiedad *Email* de la asignación automática de usuarios, tal como se describe en el paso 3. Se crea una nueva subcarpeta en la carpeta Bandeja de entrada denominada **Symphony** en los buzones de usuario y los elementos de mensaje se importan a esa carpeta. El conector determina a qué buzón se van a importar elementos mediante el valor de la propiedad *Email* . Cada mensaje de chat contiene esta propiedad, que se rellena con la dirección de correo electrónico de cada participante.

## <a name="before-you-begin"></a>Antes de empezar

- Cree una cuenta de Veritas Merge1 para los conectores de Microsoft. Para crear una cuenta, póngase en contacto con [el servicio de atención al cliente de Veritas](https://globanet.com/ms-connectors-contact). Iniciará sesión en esta cuenta al crear el conector en el paso 1.

- Al usuario que crea el conector symphony en el paso 1 (y lo completa en el paso 3) se le debe asignar el rol Administrador del conector de datos. Este rol es necesario para agregar conectores en la página **Conectores de datos** del portal de cumplimiento. Este rol se agrega de forma predeterminada a varios grupos de roles. Para obtener una lista de estos grupos de roles, consulte la sección "Roles en los centros de seguridad y cumplimiento" de [Permisos en el Centro de cumplimiento de & seguridad](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center). Como alternativa, un administrador de su organización puede crear un grupo de roles personalizado, asignar el rol Administrador del conector de datos y, a continuación, agregar los usuarios adecuados como miembros. Para obtener instrucciones, consulte la sección "Crear un grupo de roles personalizado" en [Permisos en el portal de cumplimiento Microsoft Purview](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group).

- Este conector de datos de Veritas está en versión preliminar pública en entornos de GCC en la nube Microsoft 365 administración pública de EE. UU. Las aplicaciones y servicios de terceros pueden implicar almacenar, transmitir y procesar los datos de clientes de su organización en sistemas de terceros que están fuera de la infraestructura de Microsoft 365 y, por lo tanto, no están cubiertos por los compromisos de protección de datos y Microsoft Purview. Microsoft no hace ninguna representación de que el uso de este producto para conectarse a aplicaciones de terceros implica que esas aplicaciones de terceros son compatibles con FEDRAMP.

## <a name="step-1-set-up-the-symphony-connector"></a>Paso 1: Configurar el conector symphony

El primer paso consiste en acceder a la página **Conectores de datos** del portal de cumplimiento y crear un conector para los datos de Symphony.

1. Vaya a y, a [https://compliance.microsoft.com](https://compliance.microsoft.com/) continuación, haga clic en **Conectores** >  de **datosSymphony**.

2. En la página de descripción del producto **symphony** , haga clic en **Agregar conector**.

3. En la página **Términos de servicio** , haga clic en **Aceptar**.

4. Escriba un nombre único que identifique el conector y, a continuación, haga clic en **Siguiente**.

5. Inicie sesión en su cuenta de Merge1 para configurar el conector.

## <a name="configure-the-symphony-connector-on-the-veritas-merge1-site"></a>Configuración del conector symphony en el sitio de Veritas Merge1

El segundo paso es configurar el conector Symphony en el sitio Merge1. Para obtener información sobre cómo configurar el conector Symphony en el sitio de Veritas Merge1, vea [Merge1 Third-Party Connectors User Guide(Guía del usuario de conectores de terceros de Merge1](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Symphony%20User%20Guide%20.pdf)).

Después de hacer clic en **Guardar & finalizar**, se muestra la página **Asignación** de usuarios del asistente del conector en el portal de cumplimiento.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Paso 3: Asignar usuarios y completar la configuración del conector

Para asignar usuarios y completar la configuración del conector en el portal de cumplimiento, siga estos pasos:

1. En la página **Asignar usuarios externos a Microsoft 365 usuarios**, habilite la asignación automática de usuarios. Los elementos de Symphony incluyen una propiedad denominada *Email*, que contiene direcciones de correo electrónico para los usuarios de la organización. Si el conector puede asociar esta dirección a un usuario Microsoft 365, los elementos se importan al buzón de ese usuario.

2. Haga clic en **Siguiente**, revise la configuración y, a continuación, vaya a la página **Conectores de datos** para ver el progreso del proceso de importación del nuevo conector.

## <a name="step-4-monitor-the-symphony-connector"></a>Paso 4: Supervisar el conector symphony

Después de crear el conector symphony, puede ver el estado del conector en el portal de cumplimiento.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com) y haga clic en **Conectores de datos** en el panel de navegación izquierdo.

2. Haga clic en la pestaña **Conectores** y, a continuación, seleccione el conector **symphony** para mostrar la página de control flotante. Esta página contiene las propiedades y la información sobre el conector.

3. En **Estado del conector con origen**, haga clic en el vínculo **Descargar registro** para abrir (o guardar) el registro de estado del conector. Este registro contiene información sobre los datos que se han importado a la nube de Microsoft. Para obtener más información, consulte [Visualización de registros de administración para conectores de datos](data-connector-admin-logs.md).

## <a name="known-issues"></a>Problemas conocidos

- En este momento, no se admiten la importación de datos adjuntos o elementos que superen los 10 MB. La compatibilidad con elementos más grandes estará disponible en una fecha posterior.