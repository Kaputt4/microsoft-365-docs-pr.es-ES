---
title: Conceptos básicos del Explorador de amenazas y detecciones en tiempo real en Microsoft Defender para Office 365
f1.keywords:
- NOCSH
ms.author: dansimp
author: MSFTTracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 05/05/2021
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Use el Explorador o las detecciones en tiempo real para investigar y responder a las amenazas de forma eficaz.
ms.custom:
- seo-marvel-apr2020
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: 3c431b60abfe728cfb823ea45719d922ef0b1c93
ms.sourcegitcommit: 2b89bcff547e00be3d38dc8d1e6cbcf8f41eba42
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2022
ms.locfileid: "67596795"
---
# <a name="explorer-and-real-time-detections"></a>Detecciones en tiempo real y explorador

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a**
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

En este artículo:

- [Diferencias entre el Explorador y las detecciones en tiempo real](#differences-between-explorer-and-real-time-detections)
- [Experiencia actualizada para el Explorador y las detecciones en tiempo real](#updated-experience-for-explorer-and-real-time-detections)
- [Permisos y licencias necesarios](#required-licenses-and-permissions)

> [!NOTE]
> Esto forma parte de una **serie de 3 artículos** sobre **el Explorador (también conocido como Explorador de amenazas),** la **seguridad del correo electrónico** **y los conceptos básicos de detecciones en tiempo real y explorador** (como las diferencias entre las herramientas y los permisos necesarios para operarlas). Los otros dos artículos de esta serie son [Búsqueda de amenazas en el Explorador](threat-hunting-in-threat-explorer.md) y [Email seguridad con el Explorador](email-security-in-microsoft-defender.md).

En este artículo se explica la diferencia entre los informes de detecciones del Explorador y en tiempo real, la experiencia actualizada con el Explorador y las detecciones en tiempo real, donde puede alternar entre experiencias antiguas y nuevas, y las licencias y permisos necesarios.

Si su organización tiene [Microsoft Defender para Office 365](defender-for-office-365.md) y tiene los [permisos](#required-licenses-and-permissions), puede usar **explorador** (también conocido como **Explorador de amenazas**) o **detecciones en tiempo real** para detectar y corregir amenazas.

En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a **Email & colaboración** y, a continuación, elija **Explorador** _o_ **Detecciones en tiempo real**. Para ir directamente a la página, use <https://security.microsoft.com/threatexplorer> o <https://security.microsoft.com/realtimereports>.

Con estas herramientas, puede:

- Vea malware detectado por las características de seguridad de Microsoft 365.
- Vea la dirección URL de phishing y haga clic en datos de veredicto.
- Inicie un proceso de investigación y respuesta automatizado desde una vista en el Explorador.
- Investigue el correo electrónico malintencionado y mucho más.

Para obtener más información, vea [Email seguridad con el Explorador](email-security-in-microsoft-defender.md).

## <a name="differences-between-explorer-and-real-time-detections"></a>Diferencias entre el Explorador y las detecciones en tiempo real

- *Detecciones en tiempo real* es una herramienta de generación de informes disponible en Defender para Office 365 Plan 1. *El Explorador de amenazas* es una herramienta de búsqueda y corrección de amenazas disponible en Defender para Office 365 Plan 2.
- El informe de detecciones en tiempo real permite ver las detecciones en tiempo real. El Explorador de amenazas también lo hace, pero proporciona detalles adicionales para un ataque determinado, como resaltar las campañas de ataque, y proporciona a los equipos de operaciones de seguridad la capacidad de corregir amenazas (incluida la activación de una [investigación automatizada y una investigación de respuesta](automated-investigation-response-office.md)).
- Una vista *De todo el correo electrónico* está disponible en el Explorador de amenazas, pero no se incluye en el informe de detecciones en tiempo real.
- Las funcionalidades de filtrado enriquecidas y las acciones de corrección se incluyen en el Explorador de amenazas. Para obtener más información, consulte [Microsoft Defender para Office 365 Descripción del servicio: disponibilidad de características en los planes de Defender para Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).

## <a name="updated-experience-for-explorer-and-real-time-detections"></a>Experiencia actualizada para el Explorador y las detecciones en tiempo real

La experiencia del Explorador de amenazas y las detecciones en tiempo real se actualiza para alinearse con los estándares de accesibilidad modernos y optimizar el flujo de trabajo. Durante un breve tiempo, podrá alternar entre la experiencia anterior y la nueva.  

> [!NOTE]
> La alternancia afecta solo a su cuenta y no afecta a nadie más dentro de su inquilino. 

El Explorador de amenazas y las detecciones en tiempo real se dividen en las siguientes vistas:

- *Todo el correo electrónico*: muestra todo el correo electrónico analizado por Defender para office 365 y contiene correos electrónicos buenos y malintencionados. Esta característica solo está presente en el Explorador de amenazas y no está disponible para las detecciones en tiempo real. De forma predeterminada, se establece para mostrar los datos durante dos días, que se pueden expandir hasta 30 días. Esta es también la vista predeterminada del Explorador de amenazas.  

- *Vista de malware*: muestra los correos electrónicos en los que se identificó una amenaza de malware. Esta es la vista predeterminada para las detecciones en tiempo real y muestra los datos durante dos días (se pueden expandir a 30 días).  

- *Vista phish*: muestra los correos electrónicos en los que se identificó una amenaza de phish.

- *Vista de malware de contenido*: muestra las detecciones malintencionadas identificadas en los archivos compartidos a través de OneDrive, SharePoint o Teams. 

Estos son los componentes comunes dentro de estas experiencias:

- Filtros

    - Puede usar los distintos filtros para ver los datos en función de los atributos de correo electrónico o archivo.  

    - De forma predeterminada, el filtro de tiempo se aplica a los registros y se aplica durante dos días.  

    - Si aplica varios filtros, se aplican en modo "AND" y puede usar el filtro avanzado para cambiarlo al modo "OR".  

    - Puede usar comas para agregar varios valores para el mismo filtro.  

    > [!div class="mx-imgBorder"]
    > ![Filtros del Explorador](../../media/explorer-new-experience-filters.png)

- Gráficos

    - Los gráficos proporcionan una vista visual y agregada de datos basada en filtros. Puede usar filtros diferentes para ver los datos por dimensiones diferentes.  

    > [!NOTE]
    > Es posible que no vea ningún resultado en la vista de gráfico incluso si ve una entrada en la vista de lista. Esto sucede si el filtro no genera datos. Por ejemplo, si ha aplicado la familia de malware de filtro, pero los datos subyacentes no tienen ningún correo electrónico malintencionado, es posible que vea el mensaje sin datos disponibles para este escenario.  

    > [!div class="mx-imgBorder"]
    > ![Vista de gráfico del Explorador](../../media/explorer-new-experience-export-chart-data.png)

- Cuadrícula de resultados  

    - La cuadrícula de resultados muestra los resultados del correo electrónico en función de los filtros que ha aplicado.  

    - En función de la configuración establecida en el inquilino, los datos se mostrarán en utc o zona horaria local, con la información de zona horaria disponible en la primera columna.  

    - Puede navegar a la página de entidad de correo electrónico individual desde la vista de lista haciendo clic en el icono **Abrir en nueva ventana** . 

    - También puede personalizar las columnas para agregar o quitar columnas para optimizar la vista.

    > [!Note]
    > Puede alternar entre la *vista gráfico* y la *vista de lista* para maximizar el conjunto de resultados.  

    > [!div class="mx-imgBorder"]
    > ![Vista de cuadrícula del Explorador](../../media/explorer-new-experience-list-chart-view.png)

- Control flotante detallado  

    - Puede hacer clic en hipervínculos para llegar al panel de resumen de correo electrónico (entradas en la columna Asunto), destinatario o control flotante IP.  

    - El panel de resumen de correo electrónico reemplaza el control flotante de correo electrónico heredado y también proporciona una ruta de acceso para acceder al panel de entidades de correo electrónico.  

    - Los controles flotantes de entidades individuales, como IP, destinatario y dirección URL, reflejarían la misma información, pero se presentarían en una sola vista basada en pestañas, con la capacidad de expandir y contraer las distintas secciones según los requisitos.  

    - Para controles flotantes como direcciones URL, puede hacer clic en **Ver todos los Email** o **Ver todos los clics** para ver el conjunto completo de correos electrónicos o clics que contienen esa dirección URL, así como exportar el conjunto de resultados.  

- Acciones

    - Desde el Explorador de amenazas, puede desencadenar acciones de corrección como *Eliminar un correo electrónico*. Para obtener más información sobre la corrección, los límites de corrección y el seguimiento de la corrección, consulte [Corrección del correo electrónico malintencionado](remediate-malicious-email-delivered-office-365.md).  

- Export

    - Puede hacer clic en **Exportar datos del gráfico** para exportar los detalles del gráfico. Del mismo modo, haga clic en **Exportar lista de correo electrónico** para exportar los detalles del correo electrónico.

    - Puede exportar hasta 200 000 registros para la lista de correo electrónico. Sin embargo, para mejorar el rendimiento del sistema y reducir el tiempo de descarga, debe usar varios filtros de correo electrónico.

    > [!div class="mx-imgBorder"]
    > ![Exportación de datos de gráficos](../../media/explorer-new-experience-export-chart-data.png)

Además de estas características, también obtendrá experiencias actualizadas como *direcciones URL principales*, *clics superiores*, *usuarios de destino superior* y *Email origen*. *Las direcciones URL principales*, *los clics superiores* y *los usuarios de destino superior* se pueden filtrar aún más según el filtro que aplique en el Explorador. 

## <a name="required-licenses-and-permissions"></a>Permisos y licencias necesarios

Debe tener [Microsoft Defender para Office 365](defender-for-office-365.md) para usar detecciones del Explorador o en tiempo real:

- Explorer solo se incluye en Defender para Office 365 Plan 2.
- El informe de detecciones en tiempo real se incluye en Defender para Office 365 plan 1.

Los equipos de operaciones de seguridad deben asignar licencias para todos los usuarios que deben estar protegidos por Defender para Office 365 y tener en cuenta que las detecciones del Explorador y en tiempo real muestran datos de detección para los usuarios con licencia.

Para ver y usar el Explorador *o* las detecciones en tiempo real, necesita los permisos siguientes:

- En Defender para Office 365:
  - Administración de la organización
  - Administrador de seguridad (esto se puede asignar en el Centro de administración de Azure Active Directory (<https://aad.portal.azure.com>)
  - Lector de seguridad
- En Exchange Online:
  - Administración de la organización
  - Administración de la organización de solo visualización
  - Destinatarios con permiso de vista
  - Administración de cumplimiento

Para obtener más información sobre los roles y permisos, consulte los artículos siguientes:

- [Permisos en el portal de Microsoft 365 Defender](permissions-microsoft-365-security-center.md)
- [Permisos de Exchange Online](/exchange/permissions-exo/permissions-exo)

## <a name="more-information"></a>Más información

- [Explorador de amenazas recopila detalles de correo electrónico en la página de entidad de correo electrónico](mdo-email-entity-page.md)
- [Buscar e investigar el correo electrónico malintencionado que se ha entregado](investigate-malicious-email-that-was-delivered.md)
- [Visualización de archivos malintencionados detectados en SharePoint Online, OneDrive y Microsoft Teams](mdo-for-spo-odb-and-teams.md)
- [Informe de estado de protección contra amenazas](view-email-security-reports.md#threat-protection-status-report)
- [Investigación y respuesta automatizada en la Protección contra amenazas de Microsoft](automated-investigation-response-office.md)
