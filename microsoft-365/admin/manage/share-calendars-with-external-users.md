---
title: Compartir calendarios con usuarios externos
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: fb00dd4e-2d5f-4e8d-8ff4-94b2cf002bdd
description: Habilite el uso compartido de calendarios en el Centro de administración de Microsoft 365 para que los usuarios puedan compartir sus calendarios con cualquier persona dentro o fuera de la organización.
ms.openlocfilehash: b3ca1d4f2a6ef24a6958b4fe805ccf617c0984e7
ms.sourcegitcommit: a7c1acfb3d2cbba913e32493b16ebd8cbfeee456
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/13/2022
ms.locfileid: "66043152"
---
# <a name="share-microsoft-365-calendars-with-external-users"></a>Compartir calendarios de Microsoft 365 con usuarios externos

A veces es necesario que los usuarios programe reuniones con personas ajenas a la organización. Para simplificar el proceso de búsqueda de horas de reunión comunes, Microsoft 365 le permite poner calendarios a disposición de estas personas. Se trata de personas que necesitan ver los tiempos de disponibilidad y disponibilidad de los usuarios de su organización, pero no tienen cuentas de usuario para su organización Microsoft 365.

Puede habilitar el uso compartido de calendarios para todos los usuarios de la organización en el Centro de administración de Microsoft 365. Una vez habilitado el uso compartido, los usuarios pueden usar Outlook Web App para compartir sus calendarios con cualquier persona dentro o fuera de la organización. Los usuarios de la organización pueden ver el calendario compartido junto con su propio calendario. Las personas de fuera de la organización recibirán una dirección URL que pueden usar para ver el calendario. Los usuarios de su organización deciden cuándo compartir y cuánto compartir.

> [!NOTE]
> Si quiere compartir calendarios con una organización que usa Exchange Server 2013 (una solución local), el administrador de Exchange tendrá que configurar una relación de autenticación con la nube. Esto se conoce como federación y debe cumplir los requisitos mínimos de software. Vea [Uso compartido](/exchange/sharing-exchange-2013-help) para obtener más información.
  
## <a name="enable-calendar-sharing-using-the-microsoft-365-admin-center"></a>Habilitación del uso compartido de calendarios mediante el Centro de administración de Microsoft 365

1. Inicie sesión como **administrador global** en el centro de administración, vaya a **Configuración** \> **configuración de la organización** y, en la <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">pestaña **Servicios**</a>, seleccione **Calendario**.
  
3. En la página **Calendario**, elija si desea permitir que los usuarios compartan sus calendarios con personas ajenas a la organización que tengan Microsoft 365 o Exchange. Elija si desea permitir que los usuarios anónimos (usuarios sin credenciales) accedan a los calendarios a través de una invitación por correo electrónico.

4. Elija qué tipo de información de calendario se va a poner a disposición de los usuarios. Puede permitir toda la información o limitarla solo a tiempo o hora, asunto y ubicación.

## <a name="external-sharing-sync-interval"></a>Intervalo de sincronización de uso compartido externo

Actualmente no se admite la sincronización instantánea para compartir fuera del inquilino. Aunque puede compartir estas configuraciones, la sincronización se realizará periódicamente. Hay dos tipos de uso compartido entre inquilinos:

1. **Microsoft 365 a otro usuario Microsoft 365 (si el uso compartido externo está habilitado):** se crea un calendario totalmente compartido, pero la sincronización se realizará aproximadamente cada tres horas. La sincronización instantánea finalmente se habilitará para esta configuración.

2. **Microsoft 365 a un usuario de Outlook.com**: si el uso compartido externo está deshabilitado, el uso compartido con otro usuario Microsoft 365 también pertenece a este grupo. Se genera una dirección URL de ICS al compartir, que el destinatario puede usar para agregar a cualquier servicio de calendario. Con una suscripción de ICS, el servicio de calendario del destinatario elige cuándo sincronizar la suscripción de ICS para recibir nuevas actualizaciones. Si el destinatario es un Outlook.com o un usuario Microsoft 365, la sincronización se realizará aproximadamente cada tres horas.

## <a name="invite-people-to-access-calendars"></a>Invitar a personas a acceder a los calendarios

Una vez habilitado el uso compartido, los propietarios del calendario pueden ampliar las invitaciones a usuarios específicos.

1. Abra [Outlook en la Web](https://outlook.office365.com).

2. En la parte superior de la página, seleccione el iniciador de aplicaciones y seleccione **Calendario**. De forma predeterminada, el calendario principal se denomina "Calendario". Si ha creado otros calendarios, puede seleccionar uno de ellos para compartirlo en su lugar. No se pueden compartir calendarios propiedad de otras personas.

3. Escriba el nombre o la dirección de correo electrónico de la persona con la que desea compartir el calendario en el cuadro **Enviar una invitación para compartir en el correo electrónico** .

4. Elija la cantidad de información que desea que vea esta persona:

     - **Puede ver cuando estoy ocupado** permite que la persona vea cuando está ocupado, pero no incluye detalles como la ubicación del evento.

     - **Puede ver los títulos y las ubicaciones** que permite a la persona ver cuándo está ocupado, así como el título y la ubicación de los eventos.

     - **Puede ver todos los detalles** para que la persona vea todos los detalles de los eventos.

     - **Puede editar** para que la persona vea todos los detalles de los eventos y edite el calendario (solo disponible cuando se comparte con personas de su organización).

5. Seleccione **Compartir**. 

## <a name="related-content"></a>Contenido relacionado

[Activar o desactivar el uso compartido externo para un sitio](/sharepoint/change-external-sharing-site) (artículo)\
[Introducción a la Centro de administración de Microsoft 365](../admin-overview/admin-center-overview.md) (vídeo)\
[Administrar correo electrónico y calendarios](/admin) (página de vínculos)

