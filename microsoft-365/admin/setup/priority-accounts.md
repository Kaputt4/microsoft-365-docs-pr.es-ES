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
localization_priority: Normal
ms.collection:
- Adm_O365
ms.custom: AdminSurgePortfolio
description: Supervisar los mensajes de correo electrónico con errores y retrasos enviados a o desde cuentas que tienen un alto impacto empresarial.
ms.openlocfilehash: 86e01e591823c94d8279f975ed7de24cc65776dc
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286146"
---
# <a name="manage-and-monitor-priority-accounts"></a>Administrar y supervisar cuentas de prioridad

En todas Microsoft 365 organización, hay personas que son esenciales, como ejecutivos, líderes, administradores u otros usuarios que tienen acceso a información confidencial, propietaria o de alta prioridad.

Para ayudar a su organización a proteger estas cuentas, ahora puede designar usuarios específicos como cuentas de prioridad y aprovechar las características específicas de la aplicación que les proporcionan protección adicional. En el futuro, más aplicaciones y características admitirán cuentas de prioridad y, para empezar, hemos anunciado dos **funcionalidades:** protección de cuentas prioritarias y supervisión de flujo de correo **premium.**

- **Protección de** cuentas de prioridad: Microsoft Defender para Office 365 (anteriormente Office 365 Advanced Threat Protection) admite cuentas de prioridad como etiquetas que se pueden usar en filtros en alertas, informes e investigaciones. Para obtener más información, consulte [Etiquetas de usuario en Microsoft Defender para obtener Office 365](../../security/office-365-security/user-tags.md).

  Una pregunta natural es: "¿No son todos los usuarios una prioridad? ¿Por qué no designar a todos los usuarios como cuentas de prioridad?" Sí, todos los usuarios son una prioridad, pero la protección de cuentas de prioridad ofrece las siguientes ventajas adicionales:

  - **Heurística adicional:** nuestro análisis del flujo de correo en los centros de datos de Microsoft indica que los patrones de flujo de correo para los ejecutivos de la compañía son diferentes del empleado promedio. La protección de cuentas prioritarias ofrece heurísticas adicionales adaptadas específicamente a los ejecutivos de la compañía que no beneficiarían a un empleado normal.
  - **Visibilidad adicional en los informes:** en efecto, la información de todos los usuarios (o todos los usuarios afectados) ya está disponible en alertas, informes e investigaciones. La etiqueta cuentas de prioridad como filtro le permite dirigirse específicamente a sus investigaciones.

- **Premium supervisión Flow** correo electrónico: un flujo de correo correcto puede ser fundamental para el éxito empresarial y los retrasos o errores de entrega pueden tener un impacto negativo en el negocio. Puede elegir un umbral para mensajes de correo electrónico con errores o retrasos, recibir alertas cuando se supere ese umbral y ver un informe de problemas de correo electrónico para cuentas de prioridad. Para obtener más información, consulte Problemas de correo electrónico para el informe de cuentas [de prioridad en el EAC moderno](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)

Para obtener información sobre los procedimientos recomendados de seguridad para cuentas de prioridad, vea [Recomendaciones de seguridad para cuentas de prioridad.](../../security/office-365-security/security-recommendations-for-priority-accounts.md)

## <a name="before-you-begin"></a>Antes de empezar

La **característica de protección de** cuentas de prioridad que se describe en este tema solo está disponible para las organizaciones que cumplen los siguientes requisitos:

- Microsoft Defender para Office 365 plan 2, incluidos aquellos con Office 365 E3, Office 365 E5, Microsoft 365 E5 o Seguridad de Microsoft 365 E5.

La **Premium supervisión Flow correo** electrónico que se describe en este tema solo está disponible para las organizaciones que cumplen los siguientes requisitos:

- Su organización debe tener un recuento de licencias de al menos 5.000, desde uno de los siguientes productos o una combinación de los siguientes productos: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5. Por ejemplo, su organización podría tener 3000 licencias de Office 365 E3 y 2500 de Microsoft 365 E5, con un total de 5500 licencias de productos aptos.
- Su organización necesita tener al menos 50 usuarios activos de Exchange Online mensuales.

> [!NOTE]
> Puede supervisar hasta 250 cuentas de prioridad.

Al aplicar la protección de cuenta de prioridad a un buzón de correo, también debe aplicar la protección de cuenta de prioridad a los usuarios que tienen acceso al buzón (por ejemplo, el director ejecutivo y el asistente ejecutivo del CEO que administra el calendario del CEO).

### <a name="add-priority-accounts-from-the-setup-page"></a>Agregar cuentas de prioridad desde la página Configuración

Agregue cuentas de prioridad desde la **página De instalación**.

1. Vaya a la Centro de administración de Microsoft 365 en <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .

2. Vaya a **Configurar**  >  **conocimientos de** la organización y elija Ver **en** Supervisar las cuentas **más importantes.**

3. Seleccione **Introducción** o **Administrar**.

4. En la **página Agregar cuentas de** prioridad, en el campo de búsqueda, escriba el nombre o la dirección de correo electrónico de la persona que desea agregar a la lista de cuentas de prioridad. También puede establecer el umbral de correo electrónico para mensajes de correo electrónico con errores o retrasos y obtener un informe semanal de problemas para cuentas de prioridad.

5. Seleccione el usuario y elija **Guardar**.

También puede agregar cuentas de prioridad desde la página Usuarios activos.

### <a name="add-priority-accounts-from-active-users-page"></a>Agregar cuentas de prioridad desde la página Usuarios activos

Agregue cuentas de prioridad desde la página Usuarios activos.

1. Vaya al Centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.

2. Vaya a **Usuarios**  >  **Usuarios activos** y seleccione los tres puntos (más acciones) en la parte superior de la página. Seleccione **Administrar cuentas de prioridad**.

3. Seleccione **Agregar cuentas** y, en la página Agregar cuentas de prioridad, en el campo de búsqueda, escriba el nombre de la persona que desea agregar a la lista de cuentas de prioridad. 

4. Seleccione el usuario y elija **Guardar**.

## <a name="remove-a-user-from-the-priority-accounts-list"></a>Quitar un usuario de la lista de cuentas de prioridad

1. Vaya a la Centro de administración de Microsoft 365 en <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .

2. Vaya a **Configurar**  >  **conocimientos de** la organización y elija Ver **en** Supervisar las cuentas **más importantes.**

3. En la **página Supervisar la mayoría de las cuentas,** elija Cuentas de **prioridad** en Administrar **esta característica.**

4. En la **página Cuentas de** prioridad, seleccione el usuario o los usuarios que desea quitar de la lista y elija Quitar **cuentas.**

## <a name="related-topics"></a>Temas relacionados

[Uso de cuentas de prioridad en Microsoft 365](https://techcommunity.microsoft.com/t5/microsoft-365-blog/using-priority-accounts-in-microsoft-365/ba-p/1873314)
