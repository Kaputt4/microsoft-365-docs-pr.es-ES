---
title: Configurar un conector en Webex Teams datos en Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: Los administradores pueden configurar un conector para importar y archivar datos del conector webex de Veritas Teams en Microsoft 365. Este conector le permite archivar datos de orígenes de datos de terceros en Microsoft 365 para que pueda usar características de cumplimiento como retención legal, búsqueda de contenido y directivas de retención para administrar los datos de terceros de la organización.
ms.openlocfilehash: 654ca53fd4cd7c6091ff74360545ba335f753ffd
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163905"
---
# <a name="set-up-a-connector-to-archive-webex-teams-data"></a>Configurar un conector para archivar datos Teams Webex

Use un conector Veritas en el centro de cumplimiento Microsoft 365 para importar y archivar datos de webex Teams buzones de usuario de su Microsoft 365 organización. Veritas proporciona un conector [Teams webex](https://globanet.com/webex-teams/) configurado para capturar elementos de comunicación webex Teams importarlos a Microsoft 365. El conector convierte contenido de Webex Teams, como chats 1:1, conversaciones de grupo, conversaciones de canal y datos adjuntos de la cuenta webex Teams de la organización, a un formato de mensaje de correo electrónico y, a continuación, importa esos elementos al buzón del usuario en Microsoft 365.

Después de almacenar Teams webex en buzones de usuario, puede aplicar características de cumplimiento de Microsoft 365 como retención por juicio, exhibición de documentos electrónicos, directivas de retención y etiquetas de retención y cumplimiento de comunicaciones. El uso de un conector Teams Webex para importar y archivar datos en Microsoft 365 puede ayudar a su organización a cumplir con las directivas gubernamentales y reglamentarias.

## <a name="overview-of-archiving-webex-teams-data"></a>Información general sobre el archivado de datos Teams Webex

En la siguiente introducción se explica el proceso de uso de un conector para archivar webex Teams datos en Microsoft 365.

![Flujo de trabajo de archivado para datos Teams Webex](../media/WebexTeamsConnectorWorkflow.png)

1. Su organización trabaja con Webex Teams configurar y configurar un sitio webex Teams web.

2. Una vez cada 24 horas, los elementos Teams Webex se copian en el sitio Veritas Merge1. El conector también convierte los elementos webex Teams a un formato de mensaje de correo electrónico.

3. El conector Teams webex que crea en el centro de cumplimiento de Microsoft 365, se conecta a Veritas Merge1 todos los días y transfiere los elementos de webex Teams a una ubicación de Azure Storage segura en la nube de Microsoft.

4. El conector importa elementos a los buzones de usuarios específicos mediante el valor de la propiedad *Email* de la asignación automática de usuarios, tal como se describe en [el paso 3](#step-3-map-users-and-complete-the-connector-setup). Se crea una subcarpeta en la carpeta Bandeja de entrada denominada **Webex Teams** en los buzones de usuario y los elementos se importan a esa carpeta. El conector hace esto mediante el valor de la *propiedad Email.* Cada elemento Teams webex contiene esta propiedad, que se rellena con la dirección de correo electrónico de cada participante del elemento.

## <a name="before-you-begin"></a>Antes de empezar

- Cree una cuenta de Veritas Merge1 para conectores de Microsoft. Para crear esta cuenta, póngase en contacto con [el servicio de soporte al cliente de Veritas](https://globanet.com/ms-connectors-contact). Iniciará sesión en esta cuenta al crear el conector en el paso 1.

- Cree una aplicación para [https://developer.webex.com/](https://developer.webex.com) capturar datos de su cuenta webex Teams web. Para obtener instrucciones paso a paso sobre cómo crear la aplicación, consulte [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Webex%20Teams%20User%20Guide%20.pdf)

   Al crear esta aplicación, la plataforma Webex genera un conjunto de credenciales únicas. Estas credenciales se usan en el paso 2 al configurar el conector Teams Webex en el sitio Global Merge1.

- El usuario que crea el conector Teams webex en el paso 1 (y lo completa en el paso 3) debe estar asignado al rol Importar exportación de buzones en Exchange Online. Este rol es necesario para agregar conectores en la página **Conectores** de datos del centro de Microsoft 365 cumplimiento. De forma predeterminada, este rol no se asigna a un grupo de roles en Exchange Online. Puede agregar el rol Exportación de importación de buzones al grupo de roles Administración de la organización en Exchange Online. O bien, puede crear un grupo de roles, asignar el rol Importación de buzones de correo Exportar y, a continuación, agregar los usuarios adecuados como miembros. Para obtener más información, vea [](/Exchange/permissions-exo/role-groups#modify-role-groups) las secciones [Crear](/Exchange/permissions-exo/role-groups#create-role-groups) grupos de roles o Modificar grupos de roles en el artículo "Administrar grupos de roles en Exchange Online".

## <a name="step-1-set-up-the-webex-teams-connector"></a>Paso 1: Configurar el conector de Teams Webex

El primer paso es obtener acceso a **los conectores** de datos y configurar el conector Teams [Webex.](https://globanet.com/webex-teams/)

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com/) y, a continuación, haga clic **en Conectores de**  >  **datos Webex Teams**.

2. En la **página Webex Teams** descripción del producto, haga clic **en Agregar conector**.

3. En la **página Términos de** servicio, haga clic **en Aceptar**.

4. Escriba un nombre único que identifique el conector y, a continuación, haga clic en **Siguiente**.

5. Inicie sesión en su cuenta merge1 para configurar el conector.

## <a name="step-2-configure-the-webex-teams-connector-on-the-veritas-merge1-site"></a>Paso 2: Configurar el conector de Teams Webex en el sitio de Veritas Merge1

El segundo paso es configurar el conector Teams Webex en el sitio Merge1. Para obtener información sobre cómo configurar el conector Teams Webex, vea [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Webex%20Teams%20User%20Guide%20.pdf).

Después de hacer clic en Guardar  & **finalizar**, se muestra la página Asignación de usuario en el asistente para conectores en Microsoft 365 centro de cumplimiento.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Paso 3: Asignar usuarios y completar la configuración del conector

Para asignar usuarios y completar la configuración del conector en el centro de Microsoft 365 cumplimiento, siga estos pasos:

1. En la página Asignar **webex Teams a Microsoft 365 usuarios,** habilite la asignación automática de usuarios. Los elementos Teams webex incluyen una propiedad denominada *Email*, que contiene direcciones de correo electrónico para los usuarios de la organización. Si el conector puede asociar esta dirección a un Microsoft 365, los elementos se importan al buzón de ese usuario.

2. Haga **clic en** Siguiente, revise la configuración y, a continuación, vaya a la página **Conectores** de datos para ver el progreso del proceso de importación del nuevo conector.

## <a name="step-4-monitor-the-webex-teams-connector"></a>Paso 4: Supervisar el conector Teams Webex

Después de crear el conector Teams webex, puede ver el estado del conector en el centro de Microsoft 365 cumplimiento.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com) y haga clic en **Conectores de datos** en la navegación izquierda.

2. Haga clic **en la pestaña Conectores** y, a continuación, seleccione el conector **Teams Webex** para mostrar la página desplegable. Esta página contiene las propiedades y la información sobre el conector.

3. En **Estado del conector con origen,** haga clic en el vínculo Descargar **registro** para abrir (o guardar) el registro de estado del conector. Este registro contiene información sobre los datos que se han importado a la nube de Microsoft.

## <a name="known-issues"></a>Problemas conocidos

- En este momento, no se admite la importación de datos adjuntos o elementos de más de 10 MB. La compatibilidad con elementos más grandes estará disponible en una fecha posterior.