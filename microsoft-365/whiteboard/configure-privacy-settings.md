---
title: Configuración de la privacidad en La pizarra de Microsoft
ms.author: chucked
author: chuckedmonson
manager: alexfaulkner
ms.reviewer: ''
audience: admin
ms.topic: article
ms.custom: ''
ms.prod: microsoft-365-enterprise
search.appverid: MET150
ms.collection: ''
ms.localizationpriority: medium
description: Obtenga información sobre el cumplimiento y cómo configurar las opciones de privacidad en La pizarra de Microsoft.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: a2708d3eda92f3d29ea9ad6ee15e518d32d93a22
ms.sourcegitcommit: 49c275f78664740988bbc4ca4b14d3ad758e1468
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/19/2022
ms.locfileid: "66882792"
---
# <a name="configure-privacy-settings-in-microsoft-whiteboard"></a>Configuración de la privacidad en La pizarra de Microsoft

>[!NOTE]
> Si usted o sus usuarios quieren obtener más información sobre la configuración de privacidad predeterminada, las experiencias conectadas opcionales y cómo se recopilan los datos de diagnóstico, conéctelos a [la privacidad y el cumplimiento de la Pizarra de Microsoft](https://support.microsoft.com/office/privacy-and-compliance-ed9f0de9-71be-44c2-837d-e0f448660be1).

Si es el administrador de La pizarra de Microsoft para su organización, puede controlar lo siguiente:

- Qué nivel de datos de diagnóstico se recopilan y envían a Microsoft sobre el software cliente de Whiteboard que se ejecuta en el dispositivo del usuario.

- Si las experiencias conectadas opcionales en Whiteboard están disponibles para los usuarios.

Para configurar el nivel de datos de diagnóstico, inicie sesión en la [Centro de administración de Microsoft 365](/microsoft-365/admin/admin-overview/admin-center-overview?view=o365-worldwide) con su cuenta de administrador. En la página principal del centro de administración, vaya a **Mostrar toda la configuración de > > configuración de la organización > Pizarra**.

Para configurar la disponibilidad de experiencias conectadas opcionales, use el [servicio de directivas](/deployoffice/admincenter/overview-office-cloud-policy-service) en la nube de Office en el [centro de administración de Aplicaciones Microsoft 365](https://config.office.com). Inicie sesión con su cuenta de administrador y vaya a **Personalización > Administración de directivas**. La directiva que desea configurar se denomina: **Permitir el uso de experiencias conectadas opcionales adicionales en Office**.

## <a name="diagnostic-data-setting-for-your-organization"></a>Configuración de datos de diagnóstico para su organización

Puede elegir el nivel de datos de diagnóstico que se recopilan y envían a Microsoft sobre el software cliente de Whiteboard que se ejecuta en los dispositivos de su organización. Los datos de diagnóstico opcionales se enviarán a Microsoft, a menos que cambie la configuración en el Centro de administración de Microsoft 365. Si elige enviarnos sus datos de diagnóstico opcionales, también se incluyen los datos de diagnósticos necesarios.

Además de **Obligatorio** u **Opcional**, también hay una opción de **Ninguno**. Si elige esa opción, no se enviará a Microsoft ningún dato de diagnóstico sobre el software cliente whiteboard que se ejecuta en el dispositivo del usuario. Sin embargo, esta opción limita significativamente la capacidad de Microsoft para detectar, diagnosticar y corregir problemas que los usuarios pueden encontrar al usar Whiteboard.

Los usuarios no podrán cambiar el nivel de datos de diagnóstico de sus dispositivos si han iniciado sesión en Whiteboard con sus credenciales organizativas (a veces denominadas cuentas profesionales o educativas). Pero si han iniciado sesión en Whiteboard con una cuenta microsoft, como una dirección de correo electrónico de outlook.com personal, pueden cambiar el nivel de datos de diagnóstico en sus dispositivos si van a **Configuración > Privacidad y seguridad**.

## <a name="optional-connected-experiences-setting-for-your-organization"></a>Configuración de experiencias conectadas opcionales para su organización

Puede elegir si desea que las experiencias conectadas opcionales de Whiteboard estén disponibles para los usuarios. Estas experiencias conectadas estarán disponibles para los usuarios a menos que cambie la configuración en el Centro de administración de Microsoft 365. 

Estas experiencias conectadas son diferentes porque no están cubiertas por el contrato comercial de su organización con Microsoft. Las experiencias conectadas opcionales ofrecidas por Microsoft directamente a los usuarios se rigen por el [Contrato de servicios de Microsoft](https://www.microsoft.com/servicesagreement) en lugar de los [Términos de servicios en línea](https://www.microsoft.com/licensing/product-licensing/products).

Incluso si decide que estas experiencias conectadas opcionales estén disponibles para los usuarios, los usuarios tienen la opción de desactivarlas como un grupo; para ello, vaya a **Configuración > Privacidad y seguridad**. Los usuarios solo tienen esta opción si han iniciado sesión en Whiteboard con sus credenciales organizativas (a veces denominadas cuentas profesionales o educativas), no si han iniciado sesión con una cuenta de Microsoft, como una dirección de correo electrónico de outlook.com personal.

## <a name="required-diagnostic-data-events-collected-by-whiteboard"></a>Eventos de datos de diagnóstico necesarios recopilados por Whiteboard

A continuación se muestran los eventos de datos de diagnóstico necesarios recopilados por Whiteboard, incluida una lista de campos de datos en cada evento.

**Intentional.CanvasObject.Ink.DrawFirstStroke**

La tinta recopilada por primera vez se agrega a un panel en Microsoft Whiteboard. Esta información es fundamental para detectar errores asociados con la adición de lápiz a un panel. Microsoft usa estos datos para diagnosticar el problema con el fin de garantizar que Microsoft Whiteboard se ejecuta según lo previsto.

- **Acción** : tipo de trazo de lápiz
- **Origen** : método de entrada para el trazo de lápiz

**Intentional.SurfSide.ActivationProtocol.LoadFromUri**

Se recopila cada vez que se inicia Microsoft Whiteboard mediante una llamada desde otra aplicación o proceso. Esta información es fundamental para detectar si Whiteboard no se inicia cuando otra aplicación o proceso lo invoca correctamente. Microsoft usa estos datos para diagnosticar el problema con el fin de garantizar que Microsoft Whiteboard se ejecuta según lo previsto.

- **ApplicationExecutionState** : estado de ejecución de la aplicación cuando se produce el protocolo de activación
- **IsSignedIn** : el usuario es el estado de autenticación.
- **Tipo** : aplicación o proceso que inicia Whiteboard

**Intentional.Whiteboard.Init.DisplayWhiteboard**

Se recopila la primera vez que microsoft Whiteboard se muestra realmente en un cliente por sesión. Esta información es fundamental para detectar problemas de inicio. Microsoft usa estos datos para diagnosticar el problema con el fin de garantizar que Microsoft Whiteboard se ejecuta según lo previsto.

- **IsPrelaunched** : estado de inicio previo
- **IsProtocolActivation** : tipo de inicio de aplicación

**Intentional.Whiteboard.Init.StartApp**

Se recopila cada vez que Microsoft Whiteboard se inicia después de que el estado anterior finalice sin bloquearse. Esta información es fundamental para detectar problemas de bloqueo. Microsoft usa estos datos para diagnosticar el problema con el fin de garantizar que Microsoft Whiteboard se ejecuta según lo previsto.

- **Primer inicio** : primera vez que se inició la aplicación en el cliente

**Intentional.Whiteboard.KeyCategory.UseCategory**

Se recopila cada vez que se usa una característica por primera vez (y solo la primera vez) por usuario, sesión o pizarra en La pizarra de Microsoft. Esta información es fundamental para asegurarse de que se usan las categorías clave. Microsoft usa estos datos para diagnosticar el problema con el fin de garantizar que Microsoft Whiteboard se ejecuta según lo previsto.

- **CategoryName** : nombre de la categoría de clave

**Intentional.Whiteboard.KeyFeature.UseFeature**

Se recopila cada vez que se usa una característica por primera vez (y solo la primera vez) por usuario, sesión o pizarra en La pizarra de Microsoft. Esta información es fundamental para asegurarse de que se llama a las características y se usan. Microsoft usa estos datos para diagnosticar el problema con el fin de garantizar que Microsoft Whiteboard se ejecuta según lo previsto.

- **FeatureName** : nombre de la característica de clave

**Intentional.Whiteboard.SafeBoot.StartApp**

Se recopila cada vez que Microsoft Whiteboard se inicia después de que el estado anterior terminara en un bloqueo. Esta información es fundamental para detectar problemas de bloqueo. Microsoft usa estos datos para diagnosticar el problema con el fin de garantizar que Microsoft Whiteboard se ejecuta según lo previsto.

- **Primer inicio** : primera vez que se inició la aplicación en el cliente

**Intentional.Whiteboard.Scrub.LoadSettings**

Se recopila cada vez que se inicia Microsoft Whiteboard. Esta información es fundamental para detectar errores asociados a la configuración configurada por el usuario. Microsoft usa estos datos para diagnosticar el problema con el fin de garantizar que Microsoft Whiteboard se ejecuta según lo previsto.

- **ActivePen** : estado del modo de lápiz
- **CollectFullTelemetryWithoutSignIn** : recopilación de telemetría completa sin habilitación de inicio de sesión
- **DefaultWhiteboardBackgroundColor** : color de fondo del panel predeterminado
- **DefaultWhiteboardBackgroundPattern** : patrón de fondo de placa predeterminado
- **FlightStatus** : estado del vuelo
- **InkToShape** : habilitación de la entrada de lápiz a la forma
- **InkToTable** : habilitación de entrada de lápiz a tabla
- **SignInEnabled** : habilitación del inicio de sesión de usuario
- **SharingWithoutSignInEnabled** : habilitación del panel de uso compartido
- **ToolbarLocation** : ubicación predeterminada de la barra de herramientas en pantalla
- **TeamSettingsSource** : habilitación de la configuración de Teams
