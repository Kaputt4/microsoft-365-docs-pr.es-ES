---
title: 'Citas virtuales con Teams: integración en Cerner EHR'
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: ITPro
ms.topic: conceptual
ms.service: microsoft-365-frontline
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
ms.localizationpriority: high
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
- m365solution-healthcare
- m365solution-scenario
- m365-frontline
appliesto:
- Microsoft Teams
- Microsoft 365 for frontline workers
ms.reviewer: ansantam
description: Obtenga información sobre cómo integrar el conector EHR de Teams que permita a los proveedores de atención sanitaria de su organización realizar citas virtuales con pacientes u otros proveedores en Teams directamente desde el sistema CERNER EHR.
ms.openlocfilehash: eeb851e0f040d714dd55c5d1b262507a6b5eaf83
ms.sourcegitcommit: 5e5c2c1f7c321b5eb1c5b932c03bdd510005de13
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/15/2022
ms.locfileid: "66822597"
---
# <a name="virtual-appointments-with-teams---integration-into-cerner-ehr"></a>Citas virtuales con Teams: integración en Cerner EHR

El conector de la historia clínica electrónica (HCE) de Microsoft Teams hace que sea fácil para los médicos lanzar una cita virtual con el paciente o consultar con otro proveedor en Microsoft Teams directamente desde el sistema CERNER EHR. Integrado en la nube de Microsoft 365, Teams hace posible una colaboración y una comunicación sencillas y seguras con herramientas de chat, vídeo, voz y atención sanitaria en un único centro que admite el cumplimiento de la HIPAA, la certificación HITECH, etc.

La plataforma de comunicación y colaboración de Teams facilita a los médicos el desorden de los sistemas fragmentados para que puedan centrarse en proporcionar la mejor atención posible. Con el conector EHR de Teams, puede:

- Realice citas virtuales de Teams desde el sistema HCE Cerner con un flujo de trabajo clínico integrado.
- Permitir que los pacientes se unan a citas virtuales de Teams desde notificaciones por correo electrónico o SMS.
- Vea informes de datos de consumo e información personalizable de calidad de llamadas para citas conectadas a EHR.

Este artículo describe cómo instalar y configurar el conector EHR de Teams para integrarlo con la plataforma de Cerner. También proporciona información general sobre la experiencia de citas virtuales de Teams desde el sistema EHR de Cerner.

## <a name="before-you-begin"></a>Antes de empezar

> [!NOTE]
> Asegúrese de hablar con su representante de Cerner y revise la guía de integración de Cerner antes de habilitar la integración.

### <a name="prerequisites"></a>Requisitos previos

Antes de integrar el conector HCE de Teams en su organización sanitaria, debe tener lo siguiente:

- Una suscripción activa para Microsoft en la nube para la atención sanitaria o una suscripción a la oferta independiente del conector EHR de Microsoft Teams.
- Los usuarios tienen un Microsoft 365 adecuado o una licencia de Office 365 que incluye reuniones de Teams.
- Teams se adopta y usa en su organización de atención sanitaria.
- Los sistemas cumplen todos los [requisitos de software y explorador](/microsoftteams/hardware-requirements-for-the-teams-app) para Teams.
- Versión de Cerner de noviembre de 2018 o posterior

## <a name="set-up-the-teams-ehr-connector"></a>Configuración del conector HCE de Teams

Para la configuración del conector, debe realizar las siguientes acciones:

- [Inicio del portal de configuración del conector EHR](#launch-the-ehr-connector-configuration-portal)
- [Escribir información de configuración](#enter-configuration-information)
- [Habilitar notificaciones SMS (opcional)](#enable-sms-notifications-optional)
- [Revisar y finalizar la configuración](ehr-admin-cerner.md#review-and-finish-the-configuration)

> [!IMPORTANT]
> El administrador global de Microsoft 365 de la organización debe completar estos pasos.  

### <a name="launch-the-ehr-connector-configuration-portal"></a>Inicio del portal de configuración del conector EHR

Para empezar, el administrador de Microsoft 365 inicia el [portal de configuración del conector EHR](https://ehrconnector.teams.microsoft.com) e inicia sesión con sus credenciales de Microsoft.

El administrador de Microsoft 365 puede configurar un solo departamento o varios departamentos para probar la integración. Configure la dirección URL de prueba y producción en el portal de configuración. Asegúrese de probar la integración desde el entorno de prueba de Cerner antes de pasar a producción.

### <a name="enter-configuration-information"></a>Escribir información de configuración

A continuación, para configurar la integración, el administrador de Microsoft 365 debe añadir una URL base de recursos de interoperabilidad sanitaria rápida (FHIR) de Cerner y especificar el entorno. Configure tantas URLs base de FHIR como sea necesario, según las necesidades de su organización y los entornos que desee probar.

:::image type="content" source="media/ehr-admin-cerner-configuration.png" alt-text="Recorte de pantalla de la página Información de configuración del portal de configuración del conector EHR de Teams." lightbox="media/ehr-admin-cerner-configuration.png":::

- La dirección URL base de FHIR es una dirección estática que corresponde al punto de conexión de la API de FHIR del servidor. Un ejemplo de URL es `https://lamnahealthcare.com/fhir/auth/connect-ocurprd-oauth/api/FHDST`.

- Puede configurar la integración para entornos de prueba y producción. Para la configuración inicial, le recomendamos que configure el conector desde un entorno de prueba antes de pasar a producción.

Una vez validada la dirección URL base de FHIR y seleccionado el entorno, elija **Listo**. A continuación, agregue más direcciones URL base de FHIR para otros entornos, según sea necesario.

Seleccione **Siguiente** para ir al paso siguiente.

### <a name="enable-sms-notifications-optional"></a>Habilitar notificaciones sms (opcional)

Complete este paso si su organización quiere que Microsoft administre las notificaciones por SMS para los pacientes. Al habilitar las notificaciones por SMS, los pacientes recibirán mensajes de confirmación y recordatorio para las citas programadas.

Para habilitar las notificaciones por SMS, el administrador de Microsoft 365 hace lo siguiente:

1. En la página notificaciones de SMS, seleccione ambas casillas de consentimiento para:

    - Permitir que Microsoft envíe notificaciones por SMS a los pacientes en nombre de su organización.
    - Confirme que se asegurará de que los asistentes hayan dado su consentimiento para enviar y recibir mensajes SMS.

    :::image type="content" source="media/ehr-admin-cerner-sms-notifications.png" alt-text="Recorte de pantalla de la página de notificaciones por SMS, en la que se muestran las casillas de consentimiento y la opción para generar un número de teléfono." lightbox="media/ehr-admin-cerner-sms-notifications.png":::

1. En **Su número de teléfono**, seleccione **Generar un nuevo número de teléfono** para generar un número de teléfono para su organización. Al hacerlo, se inicia el proceso para solicitar y generar un nuevo número de teléfono. Este proceso puede tardar hasta 2 minutos en completarse.

    Una vez generado el número de teléfono, se muestra en la pantalla. Este número se usará para enviar confirmaciones por SMS y recordatorios a los pacientes. El número se ha aprovisionado, pero aún no está vinculado a la dirección URL base de FHIR. Lo podrá hacer en el paso siguiente.

    :::image type="content" source="media/ehr-admin-cerner-phone-number.png" alt-text="Recorte de pantalla que muestra un ejemplo del número de teléfono generado." lightbox="media/ehr-admin-cerner-phone-number.png":::

    Elija **Listo** y a continuación seleccione **Siguiente**.

1. Para vincular el número de teléfono a una dirección URL base de FHIR, en **Número de teléfono** en la sección **Configuración de SMS**, seleccione el número. Haga esto para cada dirección URL base de FHIR para la que quiera habilitar las notificaciones SMS.

    :::image type="content" source="media/ehr-admin-cerner-link-phone-number.png" alt-text="Recorte de pantalla que muestra cómo vincular un número de teléfono a una dirección URL base de FHIR." lightbox="media/ehr-admin-cerner-link-phone-number.png":::

    Si es la primera vez que configura el conector, verá la dirección URL base de FHIR que se escribió en el paso anterior. El mismo número de teléfono se puede vincular a varias direcciones URL base de FHIR, lo que significa que los pacientes recibirán notificaciones por SMS del mismo número de teléfono para diferentes organizaciones o departamentos.

     Seleccione **Siguiente**.

### <a name="review-and-finish-the-configuration"></a>Revisar y finalizar la configuración

Se le presentarán los registros de integración para el lanzamiento de pacientes y proveedores. Estos registros son necesarios para completar la configuración de citas virtuales en Cerner. Para obtener más información, consulte la guía de integración de teleasistencia sanitaria de Cerner-Microsoft Teams.

> [!NOTE]
> En cualquier momento, el administrador de Microsoft 365 puede iniciar sesión en el portal de configuración para ver los registros de integración y cambiar la configuración, si es necesario.

## <a name="launch-teams-virtual-appointments"></a>Iniciar citas virtuales de Teams

Después de completar los pasos del conector EHR y los pasos de configuración de Cerner, su organización está lista para admitir citas en vídeo con Teams.

### <a name="virtual-appointments-prerequisites"></a>Requisitos previos de citas virtuales

- Los sistemas deben cumplir todos los requisitos de [software y explorador](/microsoftteams/hardware-requirements-for-the-teams-app) para Teams.
- Ha completado la configuración de integración entre la organización Cerner y la organización Microsoft 365.

### <a name="provider-experience"></a>Experiencia del proveedor

Los proveedores de atención sanitaria de su organización pueden unirse a citas mediante Teams desde el portal de PowerChart. El proveedor debe ir al panel de pacientes donde está disponible la opción Teams.

Desde allí, el proveedor puede ver la información de la cita, unirse a citas y enviar el vínculo de la reunión. Después del inicio de sesión único, el proveedor se dirige directamente a la cita virtual en Teams.

Características principales de la experiencia del proveedor:

- Los proveedores pueden unirse a citas mediante exploradores compatibles o la aplicación Teams.
- Los proveedores pueden usar todas las características de reunión de Teams compatibles, incluido el uso compartido de pantalla, el fondo personalizado y la grabación.
- Los proveedores pueden ver las actualizaciones en tiempo real de los pacientes que se han conectado a una cita para una determinada cita en PowerChart.
- La información del proveedor no es visible para los pacientes durante la cita.

> [!NOTE]
> El proveedor de atención sanitaria debe descargar, copiar y anotar toda la información especificada en el chat de la reunión necesaria para fines de retención o continuidad de los registros médicos. El chat no constituye un registro médico legal ni un conjunto de registros designado. Los mensajes del chat se almacenan en función de la configuración creada por el administrador de Microsoft Teams.

### <a name="patient-experience"></a>Experiencia del paciente

El conector admite que los pacientes se unan a citas a través de un vínculo en el mensaje de texto SMS. En el momento de la cita, los pacientes pueden iniciar una cita pulsando el vínculo en el mensaje de texto SMS.

Características clave de la experiencia del paciente

- Los pacientes pueden unirse a citas desde [exploradores web modernos en equipos de escritorio y móviles sin tener que instalar la aplicación Teams](browser-join.md).
- Los pacientes pueden unirse a citas con un solo clic y no se requiere ninguna otra cuenta o inicio de sesión.
- No es necesario que los pacientes creen una cuenta de Microsoft ni que inicien sesión para iniciar una visita.
- Los pacientes se colocan en una sala de espera hasta que el proveedor se une y los admite.
- Los pacientes pueden probar el vídeo y el micrófono en la sala de espera antes de unirse a la cita.

## <a name="get-insight-into-virtual-appointments-usage"></a>Obtener información sobre el uso de citas virtuales

El [ Informe de uso de visitas virtuales](virtual-visits-usage-report.md) en el centro de administración de Microsoft Teams proporciona a los administradores información general sobre la actividad de citas virtuales de Teams en su organización. El informe muestra análisis detallados de citas virtuales, incluidas las reuniones integradas en EHR de Teams realizadas desde el sistema EHR.

Puede consultar métricas clave como el tiempo de espera en la sala de espera y la duración de las citas. Use esta información para conocer las tendencias de uso y así poder optimizar las citas virtuales para obtener mejores resultados empresariales.

## <a name="privacy-and-location-of-data"></a>Privacidad y ubicación de los datos

La integración de Teams en sistemas EHR optimiza la cantidad de datos que se usan y almacenan durante los flujos de integración y citas virtuales. La solución sigue los principios generales de privacidad y administración de datos de Teams, y las directrices estipuladas en Privacidad de Teams.

El conector HCE de Teams no almacena ni transfiere ningún dato personal identificable ni ningún registro de salud de pacientes o proveedores sanitarios del sistema EHR. Los únicos datos que almacena el conector EHR son el identificador único del usuario de EHR, que es usado durante la configuración de la reunión de Teams.

El identificador único del usuario de EHR se almacena en una de las tres regiones geográficas descritas en [Donde se almacenan los datos de sus clientes de Microsoft 365](/microsoft-365/enterprise/o365-data-locations). Todos los chats, grabaciones y otros datos compartidos en Teams por los participantes de la reunión se almacenan según las directivas de almacenamiento existentes. Para obtener más información sobre la ubicación de los datos en Teams, consulte [Localización de datos en Teams](/microsoftteams/location-of-data-in-teams).

## <a name="related-articles"></a>Artículos relacionados

- [Informe de uso de consultas virtuales de Teams](virtual-visits-usage-report.md)
- [Informe de citas virtuales del conector HCE de Teams](ehr-connector-report.md)
- [Introducción a Teams para organizaciones sanitarias](teams-in-hc.md)
