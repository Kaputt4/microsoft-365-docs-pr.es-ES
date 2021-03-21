---
title: Configurar un conector para datos de Webex Teams en Microsoft 365
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
description: Los administradores pueden configurar un conector para importar y archivar datos del conector de Webex Teams de Globanet en Microsoft 365. Este conector le permite archivar datos de orígenes de datos de terceros en Microsoft 365 para que pueda usar características de cumplimiento como retención legal, búsqueda de contenido y directivas de retención para administrar los datos de terceros de su organización.
ms.openlocfilehash: d284ea9688af325d95b9e2b6d5fc455acc5fca68
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920814"
---
# <a name="set-up-a-connector-to-archive-webex-teams-data"></a>Configurar un conector para archivar datos de Webex Teams

Use un conector de Globanet en el Centro de cumplimiento de Microsoft 365 para importar y archivar datos de Webex Teams a buzones de usuario de su organización de Microsoft 365. Globanet proporciona un conector [de Webex Teams](https://globanet.com/webex-teams/) configurado para capturar elementos de comunicación de Webex Teams e importarlos a Microsoft 365. El conector convierte el contenido de Webex Teams, como chats 1:1, conversaciones de grupo, conversaciones de canal y datos adjuntos de la cuenta de Webex Teams de la organización, a un formato de mensaje de correo electrónico y, a continuación, importa esos elementos al buzón del usuario en Microsoft 365.

Una vez que los datos de Webex Teams se almacenan en buzones de usuario, puede aplicar características de cumplimiento de Microsoft 365 como retención por juicio, exhibición de documentos electrónicos, directivas de retención y etiquetas de retención y cumplimiento de comunicaciones. El uso de un conector de Webex Teams para importar y archivar datos en Microsoft 365 puede ayudar a su organización a cumplir con las directivas gubernamentales y reglamentarias.

## <a name="overview-of-archiving-webex-teams-data"></a>Información general sobre el archivado de datos de Webex Teams

En la siguiente introducción se explica el proceso de uso de un conector para archivar datos de Webex Teams en Microsoft 365.

![Flujo de trabajo de archivado para datos de Webex Teams](../media/WebexTeamsConnectorWorkflow.png)

1. Su organización trabaja con Webex Teams para configurar y configurar un sitio de Webex Teams.

2. Una vez cada 24 horas, los elementos de Webex Teams se copian en el sitio de Globanet Merge1. El conector también convierte los elementos de Webex Teams a un formato de mensaje de correo electrónico.

3. El conector de Webex Teams que crea en el Centro de cumplimiento de Microsoft 365, se conecta a Globanet Merge1 todos los días y transfiere los elementos de Webex Teams a una ubicación segura de Azure Storage en la nube de Microsoft.

4. El conector importa elementos a los buzones de usuarios específicos mediante el valor de la propiedad *Email* de la asignación automática de usuarios, tal como se describe en [el paso 3](#step-3-map-users-and-complete-the-connector-setup). Se crea una subcarpeta en la carpeta Bandeja de entrada denominada **Webex Teams** en los buzones de usuario y los elementos se importan a esa carpeta. El conector hace esto mediante el valor de la *propiedad Email.* Cada elemento de Webex Teams contiene esta propiedad, que se rellena con la dirección de correo electrónico de cada participante del elemento.

## <a name="before-you-begin"></a>Antes de empezar

- Crear una cuenta de Globanet Merge1 para conectores de Microsoft. Para crear esta cuenta, póngase en contacto [con el servicio de soporte al cliente de Globanet](https://globanet.com/ms-connectors-contact). Iniciará sesión en esta cuenta al crear el conector en el paso 1.

- Cree una aplicación para [https://developer.webex.com/](https://developer.webex.com) capturar datos de su cuenta de Webex Teams. Para obtener instrucciones paso a paso sobre cómo crear la aplicación, consulte [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Webex%20Teams%20User%20Guide%20.pdf)

   Al crear esta aplicación, la plataforma Webex genera un conjunto de credenciales únicas. Estas credenciales se usan en el paso 2 al configurar el conector de Webex Teams en el sitio Global Merge1.

- El usuario que crea el conector de Webex Teams en el paso 1 (y lo completa en el paso 3) debe estar asignado al rol De exportación de importación de buzones en Exchange Online. Este rol es necesario para agregar conectores en la página **Conectores de datos** del Centro de cumplimiento de Microsoft 365. De forma predeterminada, este rol no se asigna a un grupo de roles en Exchange Online. Puede agregar el rol Exportación de importación de buzones al grupo de roles Administración de la organización en Exchange Online. O bien, puede crear un grupo de roles, asignar el rol Importación de buzones de correo Exportar y, a continuación, agregar los usuarios adecuados como miembros. Para obtener más información, vea [](/Exchange/permissions-exo/role-groups#modify-role-groups) las secciones [Crear](/Exchange/permissions-exo/role-groups#create-role-groups) grupos de roles o Modificar grupos de roles en el artículo "Administrar grupos de roles en Exchange Online".

## <a name="step-1-set-up-the-webex-teams-connector"></a>Paso 1: Configurar el conector de Webex Teams

El primer paso es obtener acceso a **los conectores de datos** y configurar el conector de [Webex Teams.](https://globanet.com/webex-teams/)

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com/) y, a continuación, haga clic **en Conectores de datos**  >  **Webex Teams**.

2. En la página Descripción del producto de **Webex Teams,** haga clic **en Agregar conector**.

3. En la **página Términos de** servicio, haga clic **en Aceptar**.

4. Escriba un nombre único que identifique el conector y, a continuación, haga clic en **Siguiente**.

5. Inicie sesión en su cuenta merge1 para configurar el conector.

## <a name="step-2-configure-the-webex-teams-connector-on-the-globanet-merge1-site"></a>Paso 2: Configurar el conector de Webex Teams en el sitio de Globanet Merge1

El segundo paso es configurar el conector de Webex Teams en el sitio Merge1. Para obtener información sobre cómo configurar el conector de Webex Teams, vea [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Webex%20Teams%20User%20Guide%20.pdf).

Después de hacer clic en Guardar  & **finalizar**, se muestra la página Asignación de usuario en el asistente para conectores en el Centro de cumplimiento de Microsoft 365.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Paso 3: Asignar usuarios y completar la configuración del conector

Para asignar usuarios y completar la configuración del conector en el Centro de cumplimiento de Microsoft 365, siga estos pasos:

1. En la página Asignar usuarios de Webex Teams a usuarios de **Microsoft 365,** habilite la asignación automática de usuarios. Los elementos de Webex Teams incluyen una propiedad denominada *Email*, que contiene direcciones de correo electrónico para los usuarios de la organización. Si el conector puede asociar esta dirección con un usuario de Microsoft 365, los elementos se importan al buzón de ese usuario.

2. Haga **clic en** Siguiente, revise la configuración y, a continuación, vaya a la página **Conectores** de datos para ver el progreso del proceso de importación del nuevo conector.

## <a name="step-4-monitor-the-webex-teams-connector"></a>Paso 4: Supervisar el conector de Webex Teams

Después de crear el conector de Webex Teams, puede ver el estado del conector en el Centro de cumplimiento de Microsoft 365.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com) y haga clic en **Conectores de datos** en la navegación izquierda.

2. Haga clic **en la pestaña Conectores** y, a continuación, seleccione el conector **de Webex Teams** para mostrar la página desplegable. Esta página contiene las propiedades y la información sobre el conector.

3. En **Estado del conector con origen,** haga clic en el vínculo Descargar **registro** para abrir (o guardar) el registro de estado del conector. Este registro contiene información sobre los datos que se han importado a la nube de Microsoft.

## <a name="known-issues"></a>Problemas conocidos

- En este momento, no se admite la importación de datos adjuntos o elementos de más de 10 MB. La compatibilidad con elementos más grandes estará disponible en una fecha posterior.