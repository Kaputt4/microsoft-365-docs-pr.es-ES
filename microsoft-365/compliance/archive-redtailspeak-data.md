---
title: Configurar un conector para archivar Redtail datos de voz en Microsoft 365
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
description: Los administradores pueden configurar un conector para importar y archivar Redtail datos de voz de Globanet a Microsoft 365. Este conector le permite archivar datos de orígenes de datos de terceros en Microsoft 365. Después de archivar estos datos, puede usar las características de cumplimiento, como directivas de retención legal, búsqueda de contenido y retención para administrar datos de terceros.
ms.openlocfilehash: ee1e5c63d8990d5847241dc0ab4a88ed19e3215f
ms.sourcegitcommit: 36d12e02f6fda199ae7f2fb72fe52d7e2b5b4efd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/31/2020
ms.locfileid: "49740297"
---
# <a name="set-up-a-connector-to-archive-redtail-speak-data"></a>Configurar un conector para archivar datos de Redtail Speak

Use un conector de Globanet en el centro de cumplimiento de Microsoft 365 para importar y archivar datos de la Redtail hable con los buzones de usuario de su organización 365 de Microsoft. Globanet proporciona un conector de [voz Redtail](https://globanet.com/redtail/) que está configurado para capturar elementos del servidor SFTP de la organización donde se reciben los elementos de Redtail. El conector convierte el contenido de Redtail hable a un formato de mensaje de correo electrónico y, a continuación, importa esos elementos al buzón del usuario en Microsoft 365.

Una vez que los datos de voz de Redtail se almacenan en buzones de usuario, puede aplicar características de cumplimiento de Microsoft 365, como retención por juicio, eDiscovery, directivas de retención y etiquetas de retención. El uso de un conector de voz de Redtail para importar y archivar datos en Microsoft 365 puede ayudar a su organización a cumplir con las directivas gubernamentales y regulatorias.

## <a name="overview-of-archiving-the-redtail-speak-data"></a>Información general sobre el archivado de los datos de Redtail Speak

La información general siguiente explica el proceso de uso de un conector para archivar los datos de Redtail Speak en Microsoft 365.

![Flujo de trabajo de archivado para Redtail datos de voz](../media/RedtailSpeakConnectorWorkflow.png)

1. Su organización trabaja con Redtail hable para configurar y configurar una puerta de enlace SMTP en la que los mensajes se reenvían desde Redtail hablan al servidor de SFTP de la organización a diario.

2. Una vez cada 24 horas, los elementos Redtail Speak se copian en el sitio Merge1 de Globanet. El conector también convierte los elementos Speak Redtail en un formato de mensaje de correo electrónico.

3. El conector para voz Redtail que ha creado en el centro de cumplimiento de Microsoft 365 se conecta al sitio de Globanet Merge1 todos los días y transfiere los mensajes a una ubicación de almacenamiento seguro de Azure en la nube de Microsoft.

4. El conector importa los elementos convertidos de Redtail de voz a los buzones de usuarios específicos mediante el valor de la propiedad *email* de la asignación automática de usuarios, como se describe en el [paso 3](#step-3-map-users-and-complete-the-connector-setup). Se crea una subcarpeta en la carpeta Bandeja de entrada denominada **Redtail Speak** en los buzones de usuario y los elementos se importan a esa carpeta. El conector determina a qué buzón se importarán los elementos mediante el valor de la propiedad *email* . Cada elemento Speak de Redtail contiene esta propiedad, que se rellena con la dirección de correo electrónico de cada participante del elemento.

## <a name="before-you-begin"></a>Antes de empezar

- Cree una cuenta de Globanet Merge1 para Microsoft Connectors. Para crear una cuenta, póngase en contacto [con el soporte técnico de Globanet](https://globanet.com/contact-us/). Debe iniciar sesión en esta cuenta cuando cree el conector en el paso 1.

- En el paso 2, debe especificar el servidor SFTP de su organización. Esto es necesario para que Globanet Merge1 pueda ponerse en contacto con él para recopilar datos Redtail leer a través de SFTP.

- El usuario que crea el conector del importador leer de Redtail en el paso 1 (y lo completa en el paso 3) debe asignarse a la función importación y exportación de buzones de correo en Exchange Online. Este rol es necesario para agregar conectores en la página conectores de datos del centro de cumplimiento de Microsoft 365. De forma predeterminada, este rol no está asignado a ningún grupo de roles en Exchange Online. Puede Agregar el rol importación y exportación de buzones al grupo de funciones de administración de la organización en Exchange Online. O bien, puede crear un grupo de roles, asignar el rol de importación y exportación de buzones de correo y, a continuación, agregar los usuarios adecuados como miembros. Para obtener más información, vea las secciones [crear grupos](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) de roles o [modificar grupos de roles](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) en el artículo sobre la administración de grupos de roles en Exchange Online.

## <a name="step-1-set-up-the-redtail-speak-connector"></a>Paso 1: configurar el conector para voz de Redtail

El primer paso consiste en tener acceso a la página **conectores de datos** en el centro de cumplimiento de Microsoft 365 y crear un conector para los datos de voz de Redtail.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com/) y haga clic en **conectores de datos** &gt; **Redtail hable**.

2. En la página Descripción del producto **Redtail Speak** , haga clic en **Agregar nuevo conector**.

3. En la página **condiciones de servicio** , haga clic en **Aceptar**.

4. Escriba un nombre único que identifique el conector y, a continuación, haga clic en **siguiente**.

5. Inicie sesión en su cuenta de Merge1 para configurar el conector.

## <a name="step-2-configure-the-redtail-speak-connector-on-the-globanet-merge1-site"></a>Paso 2: configurar el conector de voz de Redtail en el sitio de Merge1 de Globanet

El segundo paso consiste en configurar el conector de voz de Redtail en el sitio de Merge1. Para obtener información acerca de cómo configurar el conector para voz de Redtail, consulte [Merge1 guía del usuario de conectores de terceros](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Redtail%20Speak%20User%20Guide%20.pdf).

Después de hacer clic en **guardar & finalizar**, se muestra la página **asignación de usuarios** en el Asistente para conectores del centro de cumplimiento de Microsoft 365.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Paso 3: asignar usuarios y completar la configuración del conector

Para asignar usuarios y completar la configuración del conector, siga estos pasos:

1. En la página **asignar Redtail de voz a usuarios de Microsoft 365** , habilite la asignación automática de usuarios. Los elementos Redtail hablan incluyen una propiedad denominada *email*, que contiene las direcciones de correo electrónico de los usuarios de la organización. Si el conector puede asociar esta dirección con un usuario de Microsoft 365, los elementos se importan al buzón de correo del usuario.

2. Haga clic en **siguiente**, revise la configuración y vaya a la página **conectores de datos** para ver el progreso del proceso de importación del nuevo conector.

## <a name="step-4-monitor-the-redtail-speak-connector"></a>Paso 4: supervisar el conector para voz de Redtail

Después de crear el conector para voz de Redtail, puede ver el estado del conector en el centro de cumplimiento de Microsoft 365.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com/) y haga clic en **conectores de datos** en el panel de navegación izquierdo.

2. Haga clic en la pestaña **conectores** y, a continuación, seleccione el conector de **voz Redtail** para mostrar la página de flotante. Esta página muestra las propiedades y la información sobre el conector.

3. En **Estado del conector con origen**, haga clic en el vínculo **Descargar registro** para abrir (o guardar) el registro de estado del conector. Este registro contiene datos que se han importado a la nube de Microsoft.

## <a name="known-issues"></a>Problemas conocidos

- En este momento, no se admite la importación de datos adjuntos o elementos de más de 10 MB. La compatibilidad con elementos más grandes estará disponible en una fecha posterior.
