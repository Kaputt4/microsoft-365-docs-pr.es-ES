---
title: Información sobre la suplantación
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Los administradores pueden aprender cómo funciona la información de suplantación. Pueden determinar rápidamente qué remitentes envían legítimamente correo electrónico a sus organizaciones desde dominios que no pasan comprobaciones de autenticación por correo electrónico (SPF, DKIM o DMARC).
ms.custom:
- seo-marvel-apr2020
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: 34cb0cfe920751c40685d2df51b7f61f5ba02dbb
ms.sourcegitcommit: 2b89bcff547e00be3d38dc8d1e6cbcf8f41eba42
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2022
ms.locfileid: "67596839"
---
# <a name="impersonation-insight-in-defender-for-office-365"></a>Información de suplantación en Defender para Office 365

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a**
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

La suplantación es donde el remitente de un mensaje de correo electrónico es muy similar a una dirección de correo electrónico del remitente real o esperada. Los atacantes suelen suplantar las direcciones de correo electrónico del remitente en phishing u otros tipos de ataques en un esfuerzo por ganar la confianza del destinatario. Básicamente hay dos tipos de suplantación:

- **Suplantación de dominio**: en lugar de lila@contoso.com, se lila@ćóntoso.com la dirección de correo electrónico del remitente suplantado.
- **Suplantación de usuario**: en lugar de michelle@contoso.com, se rnichell@contoso.com la dirección de correo electrónico del remitente suplantado.

La suplantación de dominio es diferente de [la suplantación de dominio](anti-spoofing-protection.md), ya que el dominio suplantado suele ser un dominio real registrado. Los mensajes de los remitentes del dominio suplantado pueden y suelen pasar comprobaciones de autenticación de correo electrónico normales que, de lo contrario, identificarían intentos de suplantación (SPF, DKIM y DMARC).

La protección contra suplantación forma parte de la configuración de la directiva contra suplantación de identidad exclusiva de Microsoft Defender para Office 365. Para obtener más información sobre esta configuración, consulte [Configuración de suplantación en directivas contra suplantación de identidad en Microsoft Defender para Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).

Puede usar la información de suplantación en el portal de Microsoft 365 Defender para identificar rápidamente los mensajes de remitentes suplantados o dominios de remitente que ha configurado para la protección de suplantación.

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Abra el portal de Microsoft 365 Defender en <https://security.microsoft.com>. Para ir directamente a la página **Anti-phishing** , use <https://security.microsoft.com/antiphishing>. Para ir directamente a la página **Información de suplantación** , use <https://security.microsoft.com/impersonationinsight>.

- Debe tener permisos asignados en el portal de Microsoft 365 Defender para poder realizar los procedimientos de este artículo:
  - **Administración de organizaciones**
  - **Administrador de seguridad**
  - **Lector de seguridad**
  - **Lector global**

  Para obtener más información, consulte [Permisos en el portal de Microsoft 365 Defender](permissions-microsoft-365-security-center.md).

  **Nota**: La adición de usuarios al rol de Azure Active Directory correspondiente en la Centro de administración de Microsoft 365 proporciona a los usuarios los permisos necesarios en el portal de Microsoft 365 Defender _y_ permisos para otras características de Microsoft 365. Para más información, consulte[Sobre los roles de administrador](../../admin/add-users/about-admin-roles.md).

- Puede habilitar y configurar la protección contra suplantación en las directivas contra suplantación de identidad en Microsoft Defender para Office 365. La protección contra suplantación no está habilitada de forma predeterminada. Para obtener más información, vea [Configurar directivas contra suplantación de identidad (antiphishing) en Microsoft Defender para Office 365](configure-mdo-anti-phishing-policies.md).

## <a name="open-the-impersonation-insight-in-the-microsoft-365-defender-portal"></a>Abra la información de suplantación en el portal de Microsoft 365 Defender

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a Email & Directivas de **colaboración** \> **& Directivas** de **amenazas** \> de reglas \> **Anti-phishing** en la sección **Directivas**. Para ir directamente a la página **Anti-phishing** , use <https://security.microsoft.com/antiphishing>.

2. En la página **Anti-phishing** , la información de suplantación tiene el siguiente aspecto:

   :::image type="content" source="../../media/m365-sc-impersonation-insight.png" alt-text="Información de suplantación en la página Directiva contra suplantación de identidad en el portal de Microsoft 365 Defender." lightbox="../../media/m365-sc-impersonation-insight.png":::

   La información tiene dos modos:

    - **Modo de información**: si la protección contra suplantación está habilitada y configurada en cualquier directiva contra suplantación de identidad (phishing), la información muestra el número de mensajes detectados de dominios suplantados y usuarios suplantados (remitentes) durante los últimos siete días. Este es el total de todos los remitentes suplantados detectados de todas las directivas anti-phishing.
    - **Qué ocurre si el modo**: si la protección contra suplantación no está habilitada y configurada en ninguna directiva anti-phishing activa, la información muestra cuántos mensajes *habrían* sido detectados por nuestras funcionalidades de protección contra suplantación en los últimos siete días.

Para ver información sobre las detecciones de suplantación, haga clic en **Ver suplantaciones** en la información de suplantación.

## <a name="view-information-about-messages-from-senders-in-impersonated-domains"></a>Visualización de información sobre mensajes de remitentes en dominios suplantados

En la página **Información de suplantación** que aparece después de hacer clic en **Ver suplantaciones** en la información de suplantación, compruebe que la pestaña **Dominios** está seleccionada. La pestaña **Dominios** contiene la siguiente información:

- **Dominio del remitente**: dominio que suplanta, que es el dominio que se usó para enviar el mensaje de correo electrónico.
- **Recuento** de mensajes: el número de mensajes que han suplantado el dominio del remitente en los últimos 7 días.
- **Tipo de suplantación**: este valor muestra la ubicación detectada de la suplantación (por ejemplo, **Dominio en la dirección**).
- **Dominios suplantados**: el dominio suplantado, que debe ser muy similar al dominio configurado para la protección de suplantación en la directiva contra suplantación de identidad.
- **Tipo de dominio**: este valor es **Dominio de empresa** para dominios internos o **Dominio personalizado** para dominios personalizados.
- **Directiva**: la directiva contra suplantación de identidad que detectó el dominio suplantado.
- **Permitido suplantar**: uno de los siguientes valores:
  - **Sí**: el dominio se configuró como dominio de confianza (una excepción para la protección contra suplantación) en la directiva contra suplantación de identidad. Se detectaron mensajes de remitentes en el dominio suplantado, pero permitidos.
  - **No**: el dominio se configuró para la protección de suplantación en la directiva contra suplantación de identidad. Los mensajes de los remitentes del dominio suplantado se detectaron y actuaron en función de la acción de los dominios suplantados en la directiva contra suplantación de identidad.

Puede hacer clic en los encabezados de columna seleccionados para ordenar los resultados.

Para filtrar los resultados, puede usar el ![icono Buscar.](../../media/m365-cc-sc-search-icon.png) **Cuadro de búsqueda** para escribir una lista de valores separados por comas para filtrar los resultados.

### <a name="view-details-about-messages-from-senders-in-impersonated-domains"></a>Ver detalles sobre los mensajes de remitentes en dominios suplantados

En la pestaña **Dominios** de la página **Información de suplantación** , seleccione una de las detecciones de suplantación disponibles. El control flotante de detalles que aparece contiene la siguiente información y características:

- **Directiva de suplantación de selección que se va a modificar**: seleccione la directiva anti-phishing afectada que desea modificar. Solo están disponibles las directivas en las que se define el dominio suplantado en la directiva. Consulte la página anterior para ver qué directiva era realmente responsable de detectar el dominio suplantado (probablemente en función del destinatario y la prioridad de la directiva).
- **Agregar a la lista de suplantación permitida**: use este botón de alternancia para agregar o quitar el remitente de los **dominios y remitentes de confianza** (excepciones de suplantación) de la directiva de suplantación que seleccionó:
  - Si el valor **Permitido suplantar** para esta entrada era **No**, el botón de alternancia está desactivado. Para excluir a todos los remitentes de este dominio de la evaluación por protección de suplantación, deslice el botón de alternancia a activado: ![Activar.](../../media/scc-toggle-on.png) El dominio se agrega a la lista **Dominios de confianza** en la configuración de protección contra suplantación de la directiva contra suplantación de identidad.
  - Si el valor **Permitido suplantar** para esta entrada era **Sí**, el botón de alternancia está activado. Para devolver todos los remitentes de este dominio a la evaluación mediante protección de suplantación, deslice el botón de alternancia a desactivado: ![Desactivar.](../../media/scc-toggle-off.png) El dominio se quita de la lista **Dominios de confianza** en la configuración de protección contra suplantación de la directiva contra suplantación de identidad.
- Por qué lo capturamos.
- Lo que tienes que hacer.
- Un resumen de dominio que enumera el dominio suplantado.
- WhoIs datos sobre el remitente.
- Vínculo para abrir [el Explorador de amenazas](threat-explorer.md) para ver detalles adicionales sobre el remitente.
- Mensajes similares del mismo remitente que se entregaron a su organización.

## <a name="view-information-about-messages-from-impersonated-senders"></a>Visualización de información sobre mensajes de remitentes suplantados

En la página **Información de suplantación** que aparece después de hacer clic en **Ver suplantaciones** en la información de suplantación, haga clic en la pestaña **Usuarios** . La pestaña **Usuarios** contiene la siguiente información:

- **Remitente**: dirección de correo electrónico del remitente que suplanta que envió el mensaje de correo electrónico.
- **Recuento** de mensajes: el número de mensajes del remitente que suplanta en los últimos 7 días.
- **Tipo de suplantación**: este valor es **Usuario en nombre para mostrar**.
- **Usuarios suplantados**: la dirección de correo electrónico del remitente suplantado, que debe ser muy parecida al usuario configurado para la protección de suplantación en la directiva contra suplantación de identidad.
- **Tipo de usuario**: este valor muestra el tipo de protección aplicado (por ejemplo, **Usuario protegido** o **Inteligencia de buzones**).
- **Directiva**: la directiva contra suplantación de identidad que detectó al remitente suplantado.
- **Permitido suplantar**: uno de los siguientes valores:
  - **Sí**: el remitente se configuró como usuario de confianza (una excepción para la protección contra suplantación) en la directiva contra suplantación de identidad. Se detectaron mensajes del remitente suplantado, pero permitidos.
  - **No**: el remitente se configuró para la protección de suplantación en la directiva anti phishing. Los mensajes del remitente suplantado se detectaron y actuaron en función de la acción de los usuarios suplantados en la directiva anti-phishing.

Puede hacer clic en los encabezados de columna seleccionados para ordenar los resultados.

Para filtrar los resultados, puede usar el cuadro **Filtrar remitente** para escribir una lista separada por comas de valores para filtrar los resultados.

### <a name="view-details-about-messages-from-impersonated-senders"></a>Ver detalles sobre los mensajes de remitentes suplantados

En la pestaña **Usuarios** de la página **Información de suplantación** , seleccione una de las detecciones de suplantación disponibles. El control flotante de detalles que aparece contiene la siguiente información y características:

- **Directiva de suplantación de selección que se va a modificar**: seleccione la directiva anti-phishing afectada que desea modificar. Solo están disponibles las directivas en las que el remitente suplantado está definido en la directiva. Consulte la página anterior para ver qué directiva era realmente responsable de detectar al remitente suplantado (probablemente en función del destinatario y de la prioridad de la directiva).
- **Agregar a la lista de suplantación permitida**: use este botón de alternancia para agregar o quitar el remitente de los **dominios y remitentes de confianza** (excepciones de suplantación) de la directiva de suplantación que seleccionó:
  - Si el valor **Permitido suplantar** para esta entrada era **No**, el botón de alternancia está desactivado. Para excluir al remitente de la evaluación por protección de suplantación, deslice el botón de alternancia a activado: ![Activar.](../../media/scc-toggle-on.png) El remitente se agrega a la lista **Usuarios de confianza** en la configuración de protección contra suplantación de la directiva anti phishing.
  - Si el valor **Permitido suplantar** para esta entrada era **Sí**, el botón de alternancia está activado. Para devolver el remitente a la evaluación mediante la protección de suplantación, deslice el botón de alternancia a desactivado: ![Desactivar.](../../media/scc-toggle-off.png) El remitente se quita de la lista **Usuarios de confianza** en la configuración de protección contra suplantación de la directiva contra suplantación de identidad.
- Por qué lo capturamos.
- Lo que tienes que hacer.
- Resumen del remitente que muestra el remitente suplantado.
- WhoIs datos sobre el remitente.
- Vínculo para abrir [el Explorador de amenazas](threat-explorer.md) para ver detalles adicionales sobre el remitente.
- Mensajes similares del mismo remitente que se entregaron a su organización.
