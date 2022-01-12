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
description: Use detecciones en tiempo real o explorador para investigar y responder a las amenazas de forma eficaz.
ms.custom:
- seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 22e11be0080243325ca7048138fd1212eccc861d
ms.sourcegitcommit: c6a97f2a5b7a41b74ec84f2f62fabfd65d8fd92a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2022
ms.locfileid: "61872211"
---
# <a name="explorer-and-real-time-detections"></a>Detecciones en tiempo real y explorador

**Se aplica a**
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

En este artículo:

- [Diferencias entre detecciones en tiempo real y explorador](#differences-between-explorer-and-real-time-detections)
- [Experiencia actualizada para detecciones en tiempo real y explorador](#updated-experience-for-explorer-and-real-time-detections)
- [Permisos y licencias necesarios](#required-licenses-and-permissions)

> [!NOTE]
> Esto forma parte de una serie de **3** artículos en **Explorer (también** conocido como Explorador de amenazas), seguridad de correo electrónico y **conceptos** básicos de explorer y detecciones en tiempo real (como las diferencias entre las herramientas y los permisos necesarios para operarlas). Los otros dos artículos de esta serie son [Threat hunting in Explorer](threat-hunting-in-threat-explorer.md) y Email security with [Explorer](email-security-in-microsoft-defender.md).

En este artículo se explica la diferencia entre los informes de detecciones en tiempo real y explorer, la experiencia actualizada con explorer y las detecciones en tiempo real donde se puede alternar entre experiencias antiguas y nuevas, y las licencias y permisos necesarios.

Si su organización tiene [Microsoft Defender](defender-for-office-365.md)para Office 365 y tiene los permisos, puede usar **explorer** (también conocido como Explorador de **amenazas)** o detecciones en tiempo **real** para detectar y corregir amenazas. [](#required-licenses-and-permissions)

En el portal Microsoft 365 Defender en , vaya a Correo electrónico & colaboración y, a continuación, elija Explorador o <https://security.microsoft.com>   **Detecciones en tiempo real**.  Para ir directamente a la página, use <https://security.microsoft.com/threatexplorer> o <https://security.microsoft.com/realtimereports> .

Con estas herramientas, puede:

- Vea malware detectado por Microsoft 365 de seguridad.
- Ver la dirección URL de suplantación de identidad (phishing) y hacer clic en datos de veredicto.
- Inicie un proceso automatizado de investigación y respuesta desde una vista en el Explorador.
- Investigar correo electrónico malintencionado y mucho más.

Para obtener más información, vea [Email security with Explorer](email-security-in-microsoft-defender.md).

## <a name="differences-between-explorer-and-real-time-detections"></a>Diferencias entre detecciones en tiempo real y explorador

- *Las detecciones en* tiempo real son una herramienta de informes disponible en Defender para Office 365 Plan 1. *El Explorador de* amenazas es una herramienta de búsqueda y corrección de amenazas disponible en Defender para Office 365 Plan 2.
- El informe de detecciones en tiempo real permite ver las detecciones en tiempo real. El Explorador de amenazas también lo hace, pero proporciona detalles adicionales para un ataque determinado, como resaltar las campañas de ataque, y ofrece a los equipos de operaciones de seguridad la capacidad de corregir amenazas (incluida la activación de una investigación automatizada de investigación y [respuesta.](automated-investigation-response-office.md)
- Una *vista De todo* el correo electrónico está disponible en el Explorador de amenazas, pero no se incluye en el informe de detecciones en tiempo real.
- Las funciones de filtrado enriquecido y las acciones de corrección se incluyen en el Explorador de amenazas. Para obtener más información, vea [Microsoft Defender for Office 365 Service Description: Feature availability across Defender for Office 365 plans](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).

## <a name="updated-experience-for-explorer-and-real-time-detections"></a>Experiencia actualizada para detecciones en tiempo real y explorador

La experiencia del Explorador de amenazas y las detecciones en tiempo real se actualiza para alinearse con los estándares de accesibilidad modernos y optimizar el flujo de trabajo. Durante un breve período de tiempo, podrás alternar entre la experiencia antigua y la nueva.  

> [!NOTE]
> La toggling afecta solo a su cuenta y no afecta a nadie dentro de su espacio empresarial. 

El Explorador de amenazas y las detecciones en tiempo real se dividen en las siguientes vistas:

- *Todo el correo* electrónico: muestra todo el correo electrónico analizado por Defender para office 365 y contiene correos electrónicos buenos y malintencionados. Esta característica solo está presente en el Explorador de amenazas y no está disponible para detecciones en tiempo real. De forma predeterminada, se establece para mostrar datos durante dos días, que se pueden expandir hasta 30 días. Esta es también la vista predeterminada del Explorador de amenazas.  

- *Vista malware:* muestra los correos electrónicos en los que se identificó una amenaza de malware. Esta es la vista predeterminada para las detecciones en tiempo real y muestra los datos durante dos días (se puede expandir a 30 días).  

- *Vista De suplantación* de identidad : muestra los correos electrónicos en los que se identificó una amenaza de suplantación de identidad.

- *Vista de malware de* contenido: muestra detecciones malintencionadas identificadas en archivos compartidos OneDrive, SharePoint o Teams. 

Estos son los componentes comunes dentro de estas experiencias:

- Filtros

    - Puede usar los distintos filtros para ver los datos en función de los atributos de correo electrónico o archivo.  

    - De forma predeterminada, el filtro de tiempo se aplica a los registros y se aplica durante dos días.  

    - Si va a aplicar varios filtros, se aplican en modo "AND" y puede usar el filtro avanzado para cambiarlo al modo "OR".  

    - Puede usar comas para agregar varios valores para el mismo filtro.  

    > [!div class="mx-imgBorder"]
    > ![Filtros del explorador](../../media/explorer-new-experience-filters.png)

- Gráficos

    - Los gráficos proporcionan una vista visual y agregada de datos basada en filtros. Puede usar distintos filtros para ver los datos por diferentes dimensiones.  

    > [!NOTE]
    > Es posible que no vea ningún resultado en la vista de gráfico incluso si está viendo una entrada en la vista de lista. Esto sucede si el filtro no produce datos. Por ejemplo, si ha aplicado la familia de malware de filtro, pero los datos subyacentes no tienen ningún correo electrónico malintencionado, es posible que vea el mensaje sin datos disponibles para este escenario.  

    > [!div class="mx-imgBorder"]
    > ![Vista de gráfico del Explorador](../../media/explorer-new-experience-export-chart-data.png)

- Cuadrícula de resultados  

    - La cuadrícula de resultados muestra los resultados del correo electrónico en función de los filtros que haya aplicado.  

    - En función del conjunto de configuración del espacio empresarial, los datos se mostrarán en UTC o zona horaria local, con la información de zona horaria disponible en la primera columna.  

    - Puede navegar a la página de entidad de correo electrónico individual desde la vista de lista haciendo clic en el **icono Abrir en nueva** ventana. 

    - También puede personalizar las columnas para agregar o quitar columnas para optimizar la vista.

    > [!Note]
    > Puede alternar entre la vista *Gráfico* y la *Vista de lista* para maximizar el conjunto de resultados.  

    > [!div class="mx-imgBorder"]
    > ![Vista de cuadrícula del Explorador](../../media/explorer-new-experience-list-chart-view.png)

- Flyout detallado  

    - Puede hacer clic en hipervínculos para llegar al panel de resumen de correo electrónico (entradas de la columna Asunto), destinatario o control de IP.  

    - El panel de resumen de correo electrónico reemplaza al control remoto de correo electrónico heredado y también proporciona una ruta de acceso al panel de entidades de correo electrónico.  

    - Los elementos desplegables de entidades individuales como IP, destinatario y dirección URL reflejarían la misma información, pero se presentarían en una sola vista basada en pestañas, con la capacidad de expandir y contraer las distintas secciones en función de los requisitos.  

    - Para los elementos desplegables como  direcciones URL, puede hacer clic en Ver todo el correo electrónico o Ver todos los clics para ver el conjunto completo de correos electrónicos o clics que contienen esa dirección URL, así como exportar el conjunto de **resultados.**  

- Acciones

    - Desde el Explorador de amenazas, puedes desencadenar acciones de corrección como *Eliminar un correo electrónico.* Para obtener más información sobre la corrección, los límites de corrección y la corrección de seguimiento, vea [Remediate malicious email](remediate-malicious-email-delivered-office-365.md).  

- Export

    - Puede hacer clic en **Exportar datos del gráfico** para exportar los detalles del gráfico. Del mismo modo, haga clic **en Exportar lista de correo electrónico** para exportar detalles de correo electrónico.

    - Puede exportar hasta 200.000 registros para la lista de correo electrónico. Sin embargo, para mejorar el rendimiento del sistema y reducir el tiempo de descarga, debe usar varios filtros de correo electrónico.

    > [!div class="mx-imgBorder"]
    > ![Exportar datos del gráfico](../../media/explorer-new-experience-export-chart-data.png)

Además de estas características, también recibirá experiencias *actualizadas* como direcciones *URL* superiores, clics superiores, usuarios de destino principales y origen de correo *electrónico.* *Las direcciones URL superiores,* *los clics* principales y *los usuarios* de destino superiores se pueden filtrar aún más en función del filtro que aplique en el Explorador. 

## <a name="required-licenses-and-permissions"></a>Permisos y licencias necesarios

Debe tener [Microsoft Defender para Office 365](defender-for-office-365.md) usar cualquiera de las detecciones en tiempo real o explorer:

- El Explorador solo se incluye en Defender for Office 365 Plan 2.
- El informe de detecciones en tiempo real se incluye en Defender for Office 365 Plan 1.

Los equipos de operaciones de seguridad deben asignar licencias para todos los usuarios que deberán estar protegidos por Defender para Office 365 y tener en cuenta que las detecciones en tiempo real y explorador muestran datos de detección para usuarios con licencia.

Para ver y usar *detecciones* en tiempo real o explorador, necesita los siguientes permisos:

- En Defender para Office 365:
  - Administración de la organización
  - Administrador de seguridad (se puede asignar en el centro Azure Active Directory de administración ( <https://aad.portal.azure.com> )
  - Lector de seguridad
- En Exchange Online:
  - Administración de la organización
  - Administración de la organización de solo visualización
  - Destinatarios con permiso de vista
  - Administración de cumplimiento

Para obtener más información sobre roles y permisos, consulte los siguientes artículos:

- [Permisos en el portal de Microsoft 365 Defender](permissions-microsoft-365-security-center.md)
- [Permisos de Exchange Online](/e/exchange/permissions-exo/permissions-exo)

## <a name="more-information"></a>Más información

- [El Explorador de amenazas recopila detalles de correo electrónico en la página de entidad de correo electrónico](mdo-email-entity-page.md)
- [Buscar e investigar el correo electrónico malintencionado que se ha entregado](investigate-malicious-email-that-was-delivered.md)
- [Ver archivos malintencionados detectados en SharePoint Online, OneDrive y Microsoft Teams](mdo-for-spo-odb-and-teams.md)
- [Informe de estado de protección contra amenazas](view-email-security-reports.md#threat-protection-status-report)
- [Investigación y respuesta automatizada en la Protección contra amenazas de Microsoft](automated-investigation-response-office.md)
