---
title: Compromisos avanzados de Data Residency
description: Compromisos avanzados de Data Residency
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.service: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.date: ''
ms.reviewer: dmwmsft
ms.custom:
- it-pro
ms.collection:
- M365-subscription-management
ms.openlocfilehash: e08e2a0df9c5a6a711d565c04aeb8fe6e16b0415
ms.sourcegitcommit: 0c72639cc3dc74667a6b14343d303f318e70d457
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2022
ms.locfileid: "68806231"
---
# <a name="advanced-data-residency-commitments"></a>Compromisos avanzados de Data Residency

>[!NOTE]
>Si ha adquirido una suscripción multigeográfica, Microsoft almacenará determinados datos de clientes en reposo en más de una ubicación geográfica en función de su configuración, incluso si ha adquirido el complemento de Data Residency avanzada de Microsoft 365 ("ADR").  

Microsoft se compromete a almacenar determinados datos de clientes en reposo en la _geografía de la región local_ o en la _geografía de la región local expandida_ [aplicable para los clientes aptos](advanced-data-residency.md#eligibility) que compren ADR.  Los compromisos se especifican a continuación.  

## <a name="exchange-online"></a>Exchange Online

Los siguientes datos de cliente se almacenarán en reposo en geografía de _la región local_ o geografía _expandida de la región local_:

- Exchange Online contenido de buzón de correo (cuerpo del correo electrónico, entradas de calendario y contenido de datos adjuntos de correo electrónico almacenados en la _geografía de la región local_ o geografía de _región local expandida_ relacionada.

## <a name="sharepoint-onlineonedrive-for-business"></a>SharePoint Online/OneDrive para la Empresa

Los siguientes datos de cliente se almacenarán en reposo en geografía de _la región local_ o geografía _expandida de la región local_:

- El contenido del sitio de SharePoint Online y los archivos almacenados en ese sitio, así como los archivos cargados en OneDrive para la Empresa.

## <a name="microsoft-teams"></a>Microsoft Teams

Los siguientes datos de cliente se almacenarán en reposo en geografía de _la región local_ o geografía _expandida de la región local_:

- Mensajes de chat de Microsoft Teams (incluidos mensajes privados, mensajes de canal, mensajes de reunión e imágenes usados en chats) y, para los clientes que usan Microsoft Stream (en SharePoint), grabaciones de reuniones.

## <a name="microsoft-defender-for-office-p1"></a>Microsoft Defender para Office P1

Los siguientes datos de cliente se almacenarán en reposo en geografía de _la región local_ o geografía _expandida de la región local_:

- MDO P1 no almacena datos de clientes dentro de su servicio.
- Exchange Online Protection (EOP). Los siguientes datos de cliente se almacenarán en reposo en geografía de _la región local_ o _geografía de la región local expandida_: directivas y datos de configuración del servicio, correo electrónico y datos adjuntos en cuarentena, correo electrónico no deseado, análisis de clasificación, listas de bloques (url, inquilino, usuario), dominios de correo no deseado, informes y alertas

## <a name="office-for-the-web"></a>Office para la Web

Los siguientes datos de cliente se almacenarán en reposo en geografía de _la región local_ o geografía _expandida de la región local_:

- Office for the Web almacena los archivos en un host de almacenamiento que tiene sus promesas aplicables a geografía / de _la región local__expandida geografía local_.

## <a name="viva-connections"></a>Viva Connections

Los siguientes datos de cliente se almacenarán en geografía de _la región local_ o geografía de _la región local expandida_:

- Viva Connections Panel y fuente pueden tener contenido procedente de SharePoint Online, Exchange Online y Microsoft Teams. Todos los datos de clientes procedentes de estos servicios cubiertos por los compromisos de residencia de datos se almacenarán en geografía de _la región local_ o geografía de _la región local expandida_. Consulte las páginas de residencia de datos [de cargas de trabajo de Exchange Online](m365-dr-workload-exo.md), [SharePoint Online](m365-dr-workload-spo.md) y [Microsoft Teams](m365-dr-workload-teams.md) para obtener más información.

## <a name="viva-topics"></a>Temas Viva

Los siguientes datos de cliente se almacenarán en reposo en geografía de _la región local_ o geografía _expandida de la región local_:

- Todos los temas y fragmentos de datos de clientes detectados se almacenan en las _ubicaciones geográficas pertinentes_ en Exchange Online Sustrato (buzones de sitio o arbitraje, y Sustrato). Todos los datos de cliente de tema se particionan en función de la _geografía de la región local_ o de la _región local expandida_ , los datos proceden de dentro del inquilino.
- Los modelos de Machine Learning ("ML") se entrenan en datos web públicos y, como tal, no contienen datos de clientes del inquilino. En el futuro es posible que usemos datos de cliente para mejorar la precisión de los modelos de ML, en cuyo caso el control de datos de los modelos de ML seguirá las mismas directivas que cualquier otro contenido de cliente (incluida la residencia de datos, la retención, el control de acceso y la confidencialidad).
- El resaltado de temas se calcula dinámicamente cuando la página de SharePoint Online se representa mediante la ejecución de un modelo de lenguaje en el contenido de la página y su vinculación con el knowledge base de Temas. Los datos de Topics se obtienen del sustrato de la geografía de la _región local_ o de la _geografía de la región local expandida_.
- Los datos de configuración de administración se almacenan en geografía de _región local_ o geografía de _región local expandida_.

## <a name="purview-audit-standard"></a>Auditoría de Purview (estándar)

Los siguientes datos de cliente se almacenarán en reposo en geografía de _la región local_ o geografía _expandida de la región local_:

- Datos de configuración del servicio, actividades auditadas, registros de auditoría y permisos de consulta de registros de auditoría.

## <a name="purview-audit-premium"></a>Auditoría de Purview (Premium)

Los siguientes datos de cliente se almacenarán en reposo en geografía de _la región local_ o geografía _expandida de la región local_:

- Además de los datos del cliente almacenados como parte de Purview Audit (Standard), la configuración y los datos del cliente relacionados con eventos cruciales de alto valor.

## <a name="data-lifecycle-management---data-retention"></a>Administración del ciclo de vida de los datos: retención de datos

Los siguientes datos de cliente se almacenarán en reposo en geografía de _la región local_ o geografía _expandida de la región local_:

- Configuración de directivas de retención, definiciones de etiquetas de retención
- Datos de cliente almacenados en ubicaciones originales para los siguientes servicios:
  - Correo electrónico de Exchange
  - Sitio de SharePoint
  - Cuentas de OneDrive
  - Grupos de Microsoft 365
  - Carpetas públicas de Exchange
  - Chats y mensajes de canal de Microsoft Teams
- Datos de cliente copiados y almacenados en Exchange Online buzones ocultos
  - Mensajes de canal de Teams
  - Chats de Teams
  - Mensajes del canal privado de Teams
  - SharePoint Online, OneDrive para la Empresa, Exchange Online y Microsoft Teams siguen los compromisos de residencia de datos para esos servicios. Consulte las páginas de residencia de datos [de cargas de trabajo de Exchange Online](m365-dr-workload-exo.md), [SharePoint Online](m365-dr-workload-spo.md) y [Microsoft Teams](m365-dr-workload-teams.md) para obtener más información.
- Clasificadores de entrenamiento
- Eliminación de datos
- Asignaciones entre etiquetas de retención y directivas de prevención de pérdida de datos (DLP).

## <a name="data-lifecycle-management---records-management"></a>Administración del ciclo de vida de los datos: Administración de registros

Los siguientes datos de cliente se almacenarán en reposo en geografía de _la región local_ o geografía _expandida de la región local_:

- Definiciones de etiquetas de retención de registros, definiciones de plan de archivo, configuración de directivas de retención basadas en eventos, registros de revisión de eliminación y registros de eliminación

## <a name="information-protection---sensitivity-labels"></a>Information Protection: etiquetas de confidencialidad

Los siguientes datos de cliente se almacenarán en reposo en geografía de _la región local_ o geografía _expandida de la región local_:

- Configuración de etiquetas
- Definición de etiquetas
- Directivas de etiqueta
- Página de ayuda personalizada
- Explorador de actividad y registros de auditoría unificados de Microsoft 365
- Registros de justificación de cambio de etiqueta.

## <a name="information-protection---data-loss-prevention-dlp"></a>Information Protection: Prevención de pérdida de datos (DLP)

Los siguientes datos de cliente se almacenarán en reposo en geografía de _la región local_ o geografía _expandida de la región local_:

- Configuración del administrador DLP, directivas DLP en el Centro de cumplimiento, actividades supervisadas por DLP, historial de infracciones, Explorador de actividades y registros de auditoría unificados de Microsoft 365, almacenamiento en cuarentena, alertas DLP y panel de administración de alertas DLP.

## <a name="information-protection---office-message-encryption"></a>Information Protection: Cifrado de mensajes de Office

Los siguientes datos de cliente se almacenarán en reposo en geografía de _la región local_ o geografía _expandida de la región local_:

- Directivas de cifrado, configuración de administración y mensajes cifrados.

## <a name="insider-risk-management---information-barriers"></a>Administración de riesgos internos: barreras de información

Los siguientes datos de cliente se almacenarán en reposo en geografía de _la región local_ o geografía _expandida de la región local_:

- Configuración de directivas, indicadores de riesgo y configuración de administrador.
