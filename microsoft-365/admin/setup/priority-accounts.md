---
title: Administrar y supervisar cuentas de prioridad
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- admindeeplinkMAC
description: Supervise los mensajes enviados por correo electrónico con errores y retrasados enviados a o desde cuentas que tienen un alto impacto empresarial.
ms.openlocfilehash: edf2c2b1994e1647c4df9b639386cc43dc312c80
ms.sourcegitcommit: da6b3cb3b2ccfcdcd5091efce8290b6c486547db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/18/2022
ms.locfileid: "65465874"
---
# <a name="manage-and-monitor-priority-accounts-in-microsoft-365"></a>Administración y supervisión de cuentas de prioridad en Microsoft 365

En cada Microsoft 365 organización, hay personas que son esenciales, como ejecutivos, líderes, administradores u otros usuarios que tienen acceso a información confidencial, propietaria o de alta prioridad.

Para ayudar a su organización a proteger estas cuentas, ahora puede designar usuarios específicos como cuentas prioritarias y aprovechar las características específicas de la aplicación que les proporcionan protección adicional. En el futuro, más aplicaciones y características admitirán cuentas prioritarias y, para empezar, hemos anunciado dos funcionalidades: **protección de cuenta prioritaria** y **supervisión del flujo de correo premium**.

- **Protección de cuentas prioritarias**: Microsoft Defender para Office 365 (anteriormente Office 365 Advanced Threat Protection) admite cuentas de prioridad como etiquetas que se pueden usar en filtros en alertas, informes e investigaciones. Para obtener más información, consulte [Etiquetas de usuario en Microsoft Defender para Office 365](../../security/office-365-security/user-tags.md).

  Una pregunta natural es: "¿No son prioridad todos los usuarios? ¿Por qué no designar a todos los usuarios como cuentas prioritarias?" Sí, todos los usuarios son una prioridad, pero la protección de la cuenta de prioridad ofrece las siguientes ventajas adicionales:

  - **Heurística adicional**: nuestro análisis del flujo de correo en los centros de datos de Microsoft indica que los patrones de flujo de correo para los ejecutivos de la empresa son diferentes del promedio de empleados. La protección de cuentas prioritaria ofrece heurística adicional que se adapta específicamente a los ejecutivos de la empresa que no beneficiarían a un empleado normal.
  - **Visibilidad adicional en los informes**: de hecho, la información de todos los usuarios (o todos los usuarios afectados) ya está disponible en alertas, informes e investigaciones. La etiqueta de cuentas de prioridad como filtro le permite dirigirse específicamente a las investigaciones.

- **Premium Supervisión de correo Flow**: el flujo de correo correcto puede ser fundamental para el éxito empresarial, y los retrasos o errores de entrega pueden tener un impacto negativo en la empresa. Puede elegir un umbral para los correos electrónicos con errores o retrasados, recibir alertas cuando se supere ese umbral y ver un informe de problemas de correo electrónico para las cuentas de prioridad. Para obtener más información, consulte El [informe problemas de correo electrónico para cuentas de prioridad en el EAC moderno](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)

Para conocer los procedimientos recomendados de seguridad para las cuentas de prioridad, consulte [Recomendaciones de seguridad para cuentas de prioridad](../../security/office-365-security/security-recommendations-for-priority-accounts.md).

## <a name="before-you-begin"></a>Antes de empezar

La característica **de protección de cuentas de prioridad** que se describe en este tema solo está disponible para las organizaciones que cumplen los siguientes requisitos:

- Microsoft Defender para Office 365 Plan 2, incluidos los que tienen Office 365 E3, Office 365 E5, Microsoft 365 E5 o Seguridad de Microsoft 365 E5.

La característica **de supervisión Flow de correo Premium** que se describe en este tema solo está disponible para las organizaciones que cumplen los siguientes requisitos:

- Su organización debe tener un recuento de licencias de al menos 5 000, de uno de los productos siguientes, o una combinación de los siguientes: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5. Por ejemplo, su organización podría tener 3000 licencias de Office 365 E3 y 2500 de Microsoft 365 E5, con un total de 5500 licencias de productos aptos.
- Su organización debe tener al menos 50 usuarios activos mensuales para una o varias cargas de trabajo principales: Teams, One Drive para la Empresa, SharePoint Online, Exchange Online y aplicaciones Office.

> [!NOTE]
> Puede supervisar hasta 250 cuentas de prioridad.

Al aplicar la protección de la cuenta de prioridad a un buzón de correo, también debe aplicar la protección de cuenta de prioridad a los usuarios que tienen acceso al buzón (por ejemplo, el ceo y el asistente ejecutivo del ceo que administra el calendario del ceo).

### <a name="add-priority-accounts-from-the-setup-page"></a>Agregar cuentas de prioridad desde la página Configuración

Agregue cuentas de prioridad desde la **página Configuración**.

1. Vaya a la Centro de administración de Microsoft 365 en <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.

2. Vaya a **SetupOrganizational knowledge** (**Información** >  organizativa) y elija **View (Ver**) en **Monitor your most important accounts (Supervisar las cuentas más importantes**).

3. Seleccione **Introducción** o **Administrar**.

4. En la página **Agregar cuentas de prioridad** , en el campo de búsqueda, escriba el nombre o la dirección de correo electrónico de la persona que desea agregar a la lista de cuentas de prioridad. También puede establecer el umbral de correo electrónico para los correos electrónicos con errores o retrasados y obtener un informe semanal de los problemas de las cuentas de prioridad.

5. Seleccione el usuario y elija **Guardar**.

También puede agregar cuentas de prioridad desde la página Usuarios activos.

### <a name="add-priority-accounts-from-active-users-page"></a>Agregar cuentas de prioridad desde la página Usuarios activos

Agregue cuentas de prioridad desde la página Usuarios activos.

1. Vaya al Centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.

2. Vaya a **UsuariosUsuarios** >  **activos** y seleccione los tres puntos (más acciones) en la parte superior de la página. Seleccione **Administrar cuentas de prioridad**.

3. Seleccione **Agregar cuentas** y, en la página **Agregar cuentas de prioridad** , en el campo de búsqueda, escriba el nombre de la persona que desea agregar a la lista de cuentas de prioridad.

4. Seleccione el usuario y elija **Guardar**.

## <a name="remove-a-user-from-the-priority-accounts-list"></a>Eliminación de un usuario de la lista de cuentas de prioridad

1. Vaya a la Centro de administración de Microsoft 365 en <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.

2. Vaya a **SetupOrganizational knowledge** (**Información** >  organizativa) y elija **View (Ver**) en **Monitor your most important accounts (Supervisar las cuentas más importantes**).

3. En la página **Supervisión de la mayoría de las cuentas** , elija **Cuentas prioritarias** en **Administrar esta característica**.

4. En la página **Cuentas de prioridad** , seleccione el usuario o los usuarios que desea quitar de la lista y elija **Quitar cuentas**.

## <a name="related-topics"></a>Temas relacionados

[Uso de Cuentas prioritarias en Microsoft 365](https://techcommunity.microsoft.com/t5/microsoft-365-blog/using-priority-accounts-in-microsoft-365/ba-p/1873314)
