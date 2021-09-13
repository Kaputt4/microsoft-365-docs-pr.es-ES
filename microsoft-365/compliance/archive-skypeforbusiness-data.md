---
title: Configurar un conector para archivar Skype Empresarial datos en Microsoft 365
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
description: Obtenga información sobre cómo configurar y usar un conector en el Centro de cumplimiento de Microsoft 365 importar y archivar datos de Skype Empresarial a Microsoft 365.
ms.openlocfilehash: 3f772bfa7b59eac7292cd869aee2688ac1a132b6
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2021
ms.locfileid: "59184294"
---
# <a name="set-up-a-connector-to-archive-skype-for-business-data"></a>Configurar un conector para archivar Skype Empresarial datos

Use un conector Veritas en el Centro de cumplimiento de Microsoft 365 para importar y archivar datos de la plataforma Skype Empresarial a los buzones de usuario de la Microsoft 365 organización. Veritas proporciona un [conector Skype Empresarial](https://www.veritas.com/en/au/insights/merge1/skype-for-business) que está configurado para capturar elementos del origen de datos de terceros (de forma regular) e importar esos elementos a Microsoft 365. El conector convierte el contenido, como mensajes entre usuarios, chats persistentes y mensajes de conferencia de Skype Empresarial a un formato de mensaje de correo electrónico y, a continuación, importa esos elementos al buzón del usuario en Microsoft 365.

Después Skype Empresarial datos se almacenan en buzones de usuario, puede aplicar Microsoft 365 de cumplimiento como retención por juicio, exhibición de documentos electrónicos, directivas de retención y etiquetas de retención. El uso de un Skype Empresarial para importar y archivar datos en Microsoft 365 puede ayudar a su organización a cumplir con las directivas gubernamentales y reglamentarias.

## <a name="overview-of-archiving-skype-for-business-data"></a>Información general sobre el archivado Skype Empresarial datos

En la siguiente introducción se explica el proceso de uso de un conector para archivar los Skype Empresarial en Microsoft 365.

![Flujo de trabajo de archivado Skype Empresarial datos.](../media/SkypeforBusinessConnectorWorkflow.png)

1. Su organización trabaja con Skype Empresarial configurar y configurar un Skype Empresarial web.

2. Una vez cada 24 horas, los Skype Empresarial se copian en el sitio Veritas Merge1. El conector también convierte Skype Empresarial elementos a un formato de mensaje de correo electrónico.

3. El Skype Empresarial que crea en el Centro de cumplimiento de Microsoft 365, se conecta al sitio Veritas Merge1 todos los días y transfiere el contenido de Skype Empresarial a una ubicación de Azure Storage segura en la nube de Microsoft.

4. El conector importa los elementos convertidos a los buzones de usuarios específicos mediante el valor de la propiedad *Email* de la asignación automática de usuarios, tal como se describe en [el paso 3](#step-3-map-users-and-complete-the-connector-setup). Se crea una subcarpeta en la carpeta Bandeja de entrada denominada **Skype Empresarial** en los buzones de usuario y los elementos se importan a esa carpeta. El conector hace esto mediante el valor de la *propiedad Email.* Cada Skype Empresarial contiene esta propiedad, que se rellena con la dirección de correo electrónico de cada participante del elemento.

## <a name="before-you-set-up-a-connector"></a>Antes de configurar un conector

- Crear una cuenta Merge1 para conectores de Microsoft. Para ello, póngase en contacto [con el Servicio de soporte al cliente de Veritas](https://www.veritas.com/form/requestacall/ms-connectors-contact.html). Debe iniciar sesión en esta cuenta al crear el conector en el paso 1.

- El usuario que crea el conector Skype Empresarial en el paso 1 (y lo completa en el paso 3) debe estar asignado al rol De exportación de importación de buzones en Exchange Online. Este rol es necesario para agregar conectores en la **página Conectores de datos** de la Centro de cumplimiento de Microsoft 365. De forma predeterminada, este rol no se asigna a ningún grupo de roles en Exchange Online. Puede agregar el rol Exportación de importación de buzones al grupo de roles Administración de la organización en Exchange Online. O bien, puede crear un grupo de roles, asignar el rol Importación de buzones de correo Exportar y, a continuación, agregar los usuarios adecuados como miembros. Para obtener más información, vea [](/Exchange/permissions-exo/role-groups#modify-role-groups) las secciones [Crear](/Exchange/permissions-exo/role-groups#create-role-groups) grupos de roles o Modificar grupos de roles en el artículo "Administrar grupos de roles en Exchange Online".

## <a name="step-1-set-up-the-skype-for-business-connector"></a>Paso 1: Configurar el conector Skype Empresarial de datos

El primer paso es obtener acceso a la página **Conectores** de datos de la Centro de cumplimiento de Microsoft 365 y crear un conector para Skype Empresarial datos.

1. Vaya a <https://compliance.microsoft.com> y haga clic en **Conectores de** datos  >  **Skype Empresarial**.

2. En la **página Skype Empresarial** descripción del producto, haga clic en **Agregar conector**.

3. En la **página Términos de** servicio, haga clic **en Aceptar**.

4. Escriba un nombre único que identifique el conector y, a continuación, haga clic en **Siguiente**.

5. Inicie sesión en su cuenta merge1 para configurar el conector.

## <a name="step-2-configure-the-skype-for-business-on-the-veritas-merge1-site"></a>Paso 2: Configurar el Skype Empresarial en el sitio de Veritas Merge1

El segundo paso es configurar el conector Skype Empresarial en el sitio de Veritas Merge1. Para obtener información sobre cómo configurar el conector Skype Empresarial, vea [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Skype%20for%20Business%20%20User%20Guide.pdf).

Después de hacer clic en Guardar  & **finalizar**, se muestra la página Asignación de usuario en el asistente para conector en Centro de cumplimiento de Microsoft 365.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Paso 3: Asignar usuarios y completar la configuración del conector

Para asignar usuarios y completar la configuración del conector en el Centro de cumplimiento de Microsoft 365, siga estos pasos:

1. En la **página Asignar Skype Empresarial usuarios a Microsoft 365 usuarios,** habilite la asignación automática de usuarios. Los Skype Empresarial incluyen una propiedad denominada *Email*, que contiene direcciones de correo electrónico para los usuarios de la organización. Si el conector puede asociar esta dirección a un Microsoft 365, los elementos se importan al buzón de ese usuario.

2. Haga **clic en** Siguiente, revise la configuración y, a continuación, vaya a la página **Conectores** de datos para ver el progreso del proceso de importación del nuevo conector.

## <a name="step-4-monitor-the-skype-for-business-connector"></a>Paso 4: Supervisar el Skype Empresarial conector

Después de crear el Skype Empresarial, puede ver el estado del conector en el Centro de cumplimiento de Microsoft 365.

1. Vaya a <https://compliance.microsoft.com/> y haga clic en **Conectores de datos** en la navegación izquierda.

2. Haga clic **en la pestaña Conectores** y, a continuación, seleccione el conector **Skype Empresarial** para mostrar la página desplegable, que contiene las propiedades e información sobre el conector.

3. En **Estado del conector con origen,** haga clic en el vínculo Descargar **registro** para abrir (o guardar) el registro de estado del conector. Este registro contiene datos que se han importado a la nube de Microsoft.

## <a name="known-issues"></a>Problemas conocidos

- En este momento, no se admite la importación de datos adjuntos o elementos de más de 10 MB. La compatibilidad con elementos más grandes estará disponible en una fecha posterior.
