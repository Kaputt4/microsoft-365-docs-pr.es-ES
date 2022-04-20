---
title: Configuración de un conector en datos de Webex Teams en Microsoft 365
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
description: Los administradores pueden configurar un conector para importar y archivar datos desde el conector webex Teams de Veritas en Microsoft 365. Este conector le permite archivar datos de orígenes de datos de terceros en Microsoft 365 para que pueda usar características de cumplimiento como la suspensión legal, la búsqueda de contenido y las directivas de retención para administrar los datos de terceros de su organización.
ms.openlocfilehash: 1aa1a0ddd94aa2308c4884921138b12b0c152bab
ms.sourcegitcommit: 52eea2b65c0598ba4a1b930c58b42dbe62cdaadc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/19/2022
ms.locfileid: "64942873"
---
# <a name="set-up-a-connector-to-archive-webex-teams-data"></a>Configuración de un conector para archivar datos de Webex Teams

Use un conector veritas en el portal de cumplimiento de Microsoft Purview para importar y archivar datos de Webex Teams a buzones de usuario de su organización de Microsoft 365. Veritas proporciona un conector [de Teams Webex](https://globanet.com/webex-teams/) que está configurado para capturar elementos de comunicación Teams Webex e importarlos a Microsoft 365. El conector convierte el contenido de webex Teams, como chats 1:1, conversaciones de grupo, conversaciones de canal y datos adjuntos de la cuenta de webex Teams de su organización, a un formato de mensaje de correo electrónico y, a continuación, importa esos elementos al buzón del usuario en Microsoft 365.

Una vez que los datos de Webex Teams se almacenan en buzones de usuario, puede aplicar características de Microsoft Purview, como suspensión por juicio, exhibición de documentos electrónicos, directivas de retención y etiquetas de retención y cumplimiento de comunicaciones. El uso de un conector de webex Teams para importar y archivar datos en Microsoft 365 puede ayudar a su organización a cumplir las directivas gubernamentales y normativas.

## <a name="overview-of-archiving-webex-teams-data"></a>Información general sobre el archivado de datos de Webex Teams

En la información general siguiente se explica el proceso de uso de un conector para archivar los datos de Webex Teams en Microsoft 365.

![Flujo de trabajo de archivado de datos de webex Teams.](../media/WebexTeamsConnectorWorkflow.png)

1. Su organización funciona con Webex Teams para configurar y configurar un sitio de webex Teams.

2. Una vez cada 24 horas, webex Teams elementos se copian en el sitio de Veritas Merge1. El conector también convierte los elementos Teams Webex en un formato de mensaje de correo electrónico.

3. El conector webex Teams que se crea en el portal de cumplimiento, se conecta a Veritas Merge1 todos los días y transfiere los elementos de Webex Teams a una ubicación de Azure Storage segura en la nube de Microsoft.

4. El conector importa elementos a los buzones de usuarios específicos mediante el valor de la propiedad *Email* de la asignación automática de usuarios, como se describe en [el paso 3](#step-3-map-users-and-complete-the-connector-setup). Se crea una subcarpeta en la carpeta Bandeja de entrada denominada **Webex Teams** en los buzones de usuario y los elementos se importan a esa carpeta. Para ello, el conector usa el valor de la propiedad *Email* . Cada elemento Teams webex contiene esta propiedad, que se rellena con la dirección de correo electrónico de cada participante del elemento.

## <a name="before-you-begin"></a>Antes de empezar

- Cree una cuenta de Veritas Merge1 para los conectores de Microsoft. Para crear esta cuenta, póngase en contacto con [el servicio de atención al cliente de Veritas](https://globanet.com/ms-connectors-contact). Iniciará sesión en esta cuenta al crear el conector en el paso 1.

- Cree una aplicación en [https://developer.webex.com/](https://developer.webex.com) para capturar datos de su cuenta de Webex Teams. Para obtener instrucciones paso a paso sobre cómo crear la aplicación, consulte [la Guía del usuario de conectores de terceros Merge1](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Webex%20Teams%20User%20Guide%20.pdf).

   Al crear esta aplicación, la plataforma Webex genera un conjunto de credenciales únicas. Estas credenciales se usan en el paso 2 al configurar el conector webex Teams en el sitio Global Merge1.

- Al usuario que crea el conector de webex Teams en el paso 1 (y lo completa en el paso 3) se le debe asignar el rol Administrador del conector de datos. Este rol es necesario para agregar conectores en la página **Conectores de datos** del portal de cumplimiento. Este rol se agrega de forma predeterminada a varios grupos de roles. Para obtener una lista de estos grupos de roles, consulte la sección "Roles en los centros de seguridad y cumplimiento" de [Permisos en el Centro de cumplimiento de & seguridad](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center). Como alternativa, un administrador de su organización puede crear un grupo de roles personalizado, asignar el rol Administrador del conector de datos y, a continuación, agregar los usuarios adecuados como miembros. Para obtener instrucciones, consulte la sección "Crear un grupo de roles personalizado" en [Permisos en el portal de cumplimiento de Microsoft Purview](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group).

- Este conector de datos de Veritas está en versión preliminar pública en entornos de GCC en la nube Microsoft 365 administración pública de EE. UU. Las aplicaciones y servicios de terceros pueden implicar almacenar, transmitir y procesar los datos de clientes de su organización en sistemas de terceros que están fuera de la infraestructura de Microsoft 365 y, por tanto, no están cubiertos por los compromisos de protección de datos y Microsoft Purview. Microsoft no hace ninguna representación de que el uso de este producto para conectarse a aplicaciones de terceros implica que esas aplicaciones de terceros son compatibles con FEDRAMP.

## <a name="step-1-set-up-the-webex-teams-connector"></a>Paso 1: Configurar el conector de webex Teams

El primer paso consiste en obtener acceso a los **conectores de datos** y configurar el conector [webex Teams](https://globanet.com/webex-teams/).

1. Vaya a y, a [https://compliance.microsoft.com](https://compliance.microsoft.com/) continuación, haga clic en **Conectores** >  de **datosWebex Teams**.

2. En la página **Webex Teams** descripción del producto, haga clic en **Agregar conector**.

3. En la página **Términos de servicio** , haga clic en **Aceptar**.

4. Escriba un nombre único que identifique el conector y, a continuación, haga clic en **Siguiente**.

5. Inicie sesión en su cuenta de Merge1 para configurar el conector.

## <a name="step-2-configure-the-webex-teams-connector-on-the-veritas-merge1-site"></a>Paso 2: Configurar el conector de Teams Webex en el sitio de Veritas Merge1

El segundo paso consiste en configurar el conector webex Teams en el sitio Merge1. Para obtener información sobre cómo configurar el conector webex Teams, consulte [la Guía del usuario de conectores de terceros Merge1](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Webex%20Teams%20User%20Guide%20.pdf).

Después de hacer clic en **Guardar & finalizar**, se muestra la página **Asignación** de usuarios del asistente del conector en el portal de cumplimiento.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Paso 3: Asignar usuarios y completar la configuración del conector

Para asignar usuarios y completar la configuración del conector en el portal de cumplimiento, siga estos pasos:

1. En la página **Asignar webex Teams usuarios para Microsoft 365 usuarios**, habilite la asignación automática de usuarios. Los elementos Teams Webex incluyen una propiedad denominada *Email*, que contiene direcciones de correo electrónico para los usuarios de la organización. Si el conector puede asociar esta dirección a un usuario Microsoft 365, los elementos se importan al buzón de ese usuario.

2. Haga clic en **Siguiente**, revise la configuración y, a continuación, vaya a la página **Conectores de datos** para ver el progreso del proceso de importación del nuevo conector.

## <a name="step-4-monitor-the-webex-teams-connector"></a>Paso 4: Supervisión del conector de webex Teams

Después de crear el conector de webex Teams, puede ver el estado del conector en el portal de cumplimiento.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com) y haga clic en **Conectores de datos** en el panel de navegación izquierdo.

2. Haga clic en la pestaña **Conectores** y, a continuación, seleccione el conector **webex Teams** para mostrar la página de control flotante. Esta página contiene las propiedades y la información sobre el conector.

3. En **Estado del conector con origen**, haga clic en el vínculo **Descargar registro** para abrir (o guardar) el registro de estado del conector. Este registro contiene información sobre los datos que se han importado a la nube de Microsoft.

## <a name="known-issues"></a>Problemas conocidos

- En este momento, no se admiten la importación de datos adjuntos o elementos que superen los 10 MB. La compatibilidad con elementos más grandes estará disponible en una fecha posterior.