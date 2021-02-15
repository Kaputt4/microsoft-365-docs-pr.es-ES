---
title: Configurar un conector para archivar datos dinámicos en Microsoft 365
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
description: Los administradores pueden configurar un conector para importar y archivar datos dinámicos de Globanet en Microsoft 365. Este conector le permite archivar datos de orígenes de datos de terceros en Microsoft 365 para que pueda usar características de cumplimiento como suspensión legal, búsqueda de contenido y directivas de retención para administrar los datos de terceros de su organización.
ms.openlocfilehash: 23badcb2a8d2873f03b86499ccfd4c9a96b81090
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620377"
---
# <a name="set-up-a-connector-to-archive-pivot-data"></a>Configurar un conector para archivar datos dinámicos

Use un conector Globanet en el Centro de cumplimiento de Microsoft 365 para importar y archivar datos de la plataforma dinámica a los buzones de usuario de su organización de Microsoft 365. Globanet proporciona un conector dinámico que está configurado para capturar elementos del origen de datos de terceros (de forma periódica) y, [a](https://globanet.com/pivot/) continuación, importar esos elementos a Microsoft 365. Pivot es una plataforma de mensajería instantánea que permite la colaboración con participantes del mercado financiero. El conector convierte elementos como mensajes de chat, de las cuentas dinámicas de un usuario a un formato de mensaje de correo electrónico y, a continuación, importa esos elementos a los buzones de usuario de Microsoft 365.

Después de almacenar los datos dinámicos en buzones de usuario, puede aplicar características de cumplimiento de Microsoft 365, como retención por juicio, exhibición de documentos electrónicos, directivas de retención y etiquetas de retención, y cumplimiento de comunicaciones. El uso de un conector dinámico para importar y archivar datos en Microsoft 365 puede ayudar a su organización a cumplir con las directivas gubernamentales y reglamentarias.

## <a name="overview-of-archiving-pivot-data"></a>Información general sobre el archivado de datos dinámicos

En la siguiente introducción se explica el proceso de uso de un conector para archivar los datos dinámicos en Microsoft 365.

![Flujo de trabajo de archivado para datos dinámicos](../media/PivotConnectorWorkflow.png)

1. Su organización funciona con Pivot para configurar y configurar un sitio de origen dinámico.

2. Una vez cada 24 horas, los elementos dinámicos se copian en el sitio de Globanet Merge1. El conector también convierte los elementos dinámicos en un formato de mensaje de correo electrónico.

3. El conector dinámico que cree en el Centro de cumplimiento de Microsoft 365, se conecta al sitio de Globanet Merge1 todos los días y transfiere los elementos dinámicos a una ubicación segura de Azure Storage en la nube de Microsoft.

4. El conector importa los elementos dinámicos a los buzones de usuarios específicos mediante el valor de la propiedad *Email* de la asignación automática de usuarios, tal como se describe en [el paso 3.](#step-3-map-users-and-complete-the-connector-setup) Se crea una subcarpeta de la carpeta Bandeja de entrada denominada **Pivot** en los buzones de usuario y los elementos se importan a esa carpeta. El conector hace esto mediante el valor de la *propiedad Email.* Cada elemento dinámico contiene esta propiedad, que se rellena con la dirección de correo electrónico de todos los participantes del elemento.

## <a name="before-you-begin"></a>Antes de empezar

- Cree una cuenta de Globanet Merge1 para los conectores de Microsoft. Para crear esta cuenta, póngase en contacto [con el servicio de soporte al cliente de Globanet.](https://globanet.com/ms-connectors-contact/) Inicie sesión en esta cuenta cuando cree el conector en el paso 1.

- El usuario que crea el conector dinámico en el paso 1 (y lo completa en el paso 3) debe estar asignado al rol De importación y exportación de buzones en Exchange Online. Este rol es necesario para agregar conectores en la página Conectores de datos en el Centro de cumplimiento de Microsoft 365. De forma predeterminada, este rol no se asigna a un grupo de roles en Exchange Online. Puede agregar el rol De importación y exportación de buzones al grupo de roles Administración de la organización en Exchange Online. O bien, puede crear un grupo de roles, asignar el rol de importación y exportación de buzones de correo y, a continuación, agregar los usuarios adecuados como miembros. Para obtener más información, vea [](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) las secciones Crear grupos de [roles](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) o Modificar grupos de roles en el artículo "Administrar grupos de roles en Exchange Online".

## <a name="step-1-set-up-the-pivot-connector"></a>Paso 1: Configurar el conector dinámico

El primer paso es obtener acceso a la página **Conectores** de datos en el Centro de cumplimiento de Microsoft y crear un conector para datos dinámicos.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com/) y, a continuación, haga **clic en Conectores de datos**  >  **Pivot**.

2. En la página **Descripción del** producto dinámico, haga clic en **Agregar conector.**

3. En la **página Términos de** servicio, haga clic **en Aceptar.**

4. Escriba un nombre único que identifique el conector y, a continuación, haga clic en **Siguiente.**

5. Inicie sesión en su cuenta merge1 para configurar el conector.

## <a name="step-2-configure-the-pivot-connector-on-the-globanet-merge1-site"></a>Paso 2: Configurar el conector dinámico en el sitio de Globanet Merge1

El segundo paso es configurar el conector dinámico en el sitio Merge1. Para obtener información acerca de cómo configurar el conector dinámico en el sitio de Globanet Merge1, vea la Guía del usuario de Conectores [de terceros Merge1.](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Pivot%20User%20Guide%20.pdf)

Después de hacer clic en &  **finalizar,** se muestra la página Asignación de usuarios en el Asistente para conectores en el Centro de cumplimiento de Microsoft 365.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Paso 3: Asignar usuarios y completar la configuración del conector

Para asignar usuarios y completar la configuración del conector en el Centro de cumplimiento de Microsoft 356, siga estos pasos:

1. En la **página Asignar usuarios dinámicos a usuarios de Microsoft 365,** habilite la asignación automática de usuarios. Los elementos dinámicos incluyen una propiedad denominada *Correo* electrónico, que contiene direcciones de correo electrónico para los usuarios de su organización. Si el conector puede asociar esta dirección con un usuario de Microsoft 365, los elementos se importan al buzón de ese usuario.

2. Haga **clic en** Siguiente, revise  la configuración y vaya a la página Conectores de datos para ver el progreso del proceso de importación para el nuevo conector.

## <a name="step-4-monitor-the-pivot-connector"></a>Paso 4: Supervisar el conector dinámico

Después de crear el conector dinámico, puede ver el estado del conector en el Centro de cumplimiento de Microsoft 365.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com) conectores de **datos y haga clic en** conectores de datos en el panel de navegación izquierdo.

2. Haga clic **en la pestaña Conectores** y, **a** continuación, seleccione el conector dinámico para mostrar la página desplegable. Esta página contiene las propiedades y la información sobre el conector.

3. En Estado del conector  **con origen,** haga clic en el vínculo Descargar registro para abrir (o guardar) el registro de estado del conector. Este registro contiene datos que se han importado a la nube de Microsoft.

## <a name="known-issues"></a>Problemas conocidos

- En este momento, no se admite la importación de datos adjuntos o elementos de más de 10 MB. La compatibilidad con elementos más grandes estará disponible en una fecha posterior.
