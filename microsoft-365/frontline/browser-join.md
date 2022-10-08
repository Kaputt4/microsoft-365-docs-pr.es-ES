---
title: Administrar la experiencia de unión para las citas virtuales de Teams en los exploradores
author: lanachin
ms.author: v-lanachin
manager: samanro
audience: ITPro
ms.topic: article
ms.service: microsoft-365-frontline
search.appverid: ''
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
- Microsoft Cloud for Retail
f1.keywords:
- NOCSH
ms.localizationpriority: high
ms.collection:
- microsoftcloud-healthcare
- microsoftcloud-retail
- m365solution-healthcare
- m365solution-scenario
- m365-frontline
- highpri
ms.reviewer: hafarmer
description: Obtenga más información sobre la experiencia de unión para las citas virtuales de Teams en los exploradores.
appliesto:
- Microsoft Teams
- Microsoft 365 for frontline workers
ms.openlocfilehash: d9a64032610a3ef49b8d8bc5367901be80c7702a
ms.sourcegitcommit: 674dfa2cb2f20546d2f7822e09bacf0e12e2718b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68038849"
---
# <a name="manage-the-join-experience-for-teams-virtual-appointments-on-browsers"></a>Administrar la experiencia de unión para las citas virtuales de Teams en los exploradores

Microsoft Teams facilita a los usuarios unirse a citas virtuales sin tener que descargar Teams. Para una experiencia más fluida, los asistentes pueden unirse a citas como visitas sanitarias y consultas financieras desde un explorador móvil o de escritorio. Los asistentes no necesitan instalar la aplicación Teams en su dispositivo.

Al unirse al explorador, cuando un asistente se une a una cita, no se le pide que descargue Teams. En su lugar, Teams se abre en un explorador, donde el asistente puede seleccionar **Unirse ahora** para unirse. Con esta característica, tenga en cuenta que si Teams ya está instalado en el dispositivo, Teams se abrirá en un explorador y no en la aplicación.

Actualmente, la unión al explorador está disponible para las citas que se programan a través de:

- [La aplicación Bookings](https://support.microsoft.com/office/what-is-bookings-42d4e852-8e99-4d8f-9b70-d7fc93973cb5)
- Conector de la historia clínica electrónica (HCE) para Microsoft Teams:

  - Integración con [Cerner EHR](ehr-admin-cerner.md)
  - Integración con [Epic EHR](ehr-admin-epic.md)

## <a name="set-up-browser-join"></a>Configurar la unión al explorador

### <a name="appointments-scheduled-through-the-bookings-app"></a>Citas programadas a través de la aplicación Bookings

Los programadores de su organización pueden activar esta característica para tipos de citas específicos y para citas individuales en la aplicación Bookings.

Después de activar esta característica, el correo electrónico de confirmación o el texto SMS que se envía a los asistentes contendrá un vínculo para unirse a la reunión que abre Teams en un explorador móvil o de escritorio. Para obtener una lista de los exploradores compatibles, consulte [Exploradores compatibles](#supported-browsers).

#### <a name="turn-on-browser-join-for-an-appointment-type"></a>Activar la unión al explorador para un tipo de cita

En Bookings, vaya a **Configuración** > **Tipos de cita**, seleccione un [tipo de cita](https://support.microsoft.com/office/create-an-appointment-type-810eac77-6a65-4dc8-964d-c00eadf43887) y, a continuación, active **Permitir que los asistentes se unan desde un explorador**. Al hacerlo, se habilita la unión al explorador para todas las citas de este tipo.

:::image type="content" source="media/browser-join-bookings-appointment-type.png" alt-text="Captura de pantalla de la opción Permitir que los asistentes se unan desde un explorador para tipos de citas en la aplicación Bookings":::

#### <a name="turn-on-browser-join-for-an-individual-appointment"></a>Activar la unión al explorador para una cita individual

En Bookings, seleccione **Nueva reserva** y, a continuación, active **Permitir que los asistentes se unan desde un explorador**.

:::image type="content" source="media/browser-join-bookings-form.png" alt-text="Captura de pantalla de la opción Permitir que los asistentes se unan desde un explorador en el nuevo formulario de reserva de la aplicación Bookings":::

### <a name="appointments-scheduled-through-the-teams-ehr-connector"></a>Citas programadas a través del conector HCE de Teams

Usted o su personal no necesitan ninguna configuración.

**Integración con Cerner EHR**: el conector EHR de Teams admite que los pacientes se unan a citas virtuales a través de un vínculo en el mensaje de texto SMS. En el momento de la cita, los pacientes pueden unirse pulsando el vínculo en el mensaje de texto SMS y Teams se abre en un explorador.

**Integración con Epic EHR**: el conector EHR de Teams admite que los pacientes se unan a citas virtuales a través de MyChart web y móvil. En el momento de la cita, los pacientes pueden iniciar la cita desde MyChart mediante el botón **Iniciar visita virtual** y Teams se abre en un explorador.

## <a name="supported-browsers"></a>Exploradores compatibles

Estos son los exploradores que se admiten actualmente. Se admite la versión más reciente más dos versiones anteriores, a menos que se indique lo contrario.

|Plataforma  |Chrome |Safari |Edge (Chromium)|
|---------|:---|:---|:---:|
|Android   | &#x2714; &sup1;      |         |         |
|iOS    |         | &#x2714; &sup1; &sup2; |         |
|macOS     | &#x2714; | &#x2714;|         |
|Windows    | &#x2714; |   | &#x2714; |
|Ubuntu/Linux     | &#x2714;         |     |         |

&sup1; No se admite la pantalla compartida saliente en iOS o Android.

&sup2; Las aplicaciones de iOS en Safari no pueden seleccionar dispositivos de micrófono y altavoz. Por ejemplo, dispositivos Bluetooth. Se trata de una limitación del sistema operativo, que controla la selección de dispositivos predeterminada.

## <a name="things-to-consider"></a>Consideraciones que se deben tener en cuenta

El miembro del personal que realiza la cita puede compartir su pantalla desde su cliente de escritorio, móvil o web de Teams con un asistente que se una desde un explorador móvil o de escritorio. Sin embargo, los asistentes no pueden compartir su pantalla desde un explorador móvil o de escritorio.

## <a name="related-articles"></a>Artículos relacionados

- [Citas virtuales con Teams y la aplicación Bookings](bookings-virtual-visits.md)
- [Crear un tipo de cita de Bookings](https://support.microsoft.com/office/create-an-appointment-type-810eac77-6a65-4dc8-964d-c00eadf43887)
- [Unirse a una cita de Bookings como asistente](https://support.microsoft.com/office/join-a-bookings-appointment-as-an-attendee-95cea12d-2220-421f-a663-6efb20913c7f)
- [Citas virtuales con Teams: integración en Cerner EHR](ehr-admin-cerner.md)
- [Citas virtuales con Teams: integración en Epic EHR](ehr-admin-epic.md)
