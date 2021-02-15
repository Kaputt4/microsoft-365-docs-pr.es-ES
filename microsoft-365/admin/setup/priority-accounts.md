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
description: Supervisar mensajes de correo electrónico con errores y retrasos enviados a o desde cuentas que tienen un alto impacto en la empresa.
ms.openlocfilehash: bc191873b3bbdcd84122a5430adeffe2b8c29fb1
ms.sourcegitcommit: 5ce64d510b15c6e2df32b78e6086f77156731e3c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/30/2020
ms.locfileid: "49477618"
---
# <a name="manage-and-monitor-priority-accounts"></a>Administrar y supervisar cuentas de prioridad

En todas las organizaciones de Microsoft 365, hay personas que son esenciales, como ejecutivos, líderes, administradores u otros usuarios que tienen acceso a información confidencial, propietaria o de prioridad alta.

Para ayudar a su organización a proteger estas cuentas, ahora puede designar usuarios específicos como cuentas de prioridad y aprovechar las características específicas de la aplicación que les proporcionan protección adicional. En el futuro, más aplicaciones y características admitirán cuentas de prioridad y, para empezar, hemos anunciado dos **funcionalidades:** protección de cuentas de prioridad y supervisión del flujo de correo **premium.**

- **Protección** de cuentas de prioridad: Microsoft Defender para Office 365 (anteriormente Protección contra amenazas avanzada de Office 365) admite cuentas de prioridad como etiquetas que se pueden usar en filtros en alertas, informes e investigaciones. Para obtener más información, consulte [Etiquetas de usuario en Microsoft Defender para Office 365.](https://docs.microsoft.com/microsoft-365/security/office-365-security/user-tags?view=o365-worldwide)
- **Supervisión del flujo de correo premium:** un flujo de correo correcto puede ser fundamental para el éxito de la empresa y los retrasos o errores en la entrega pueden tener un impacto negativo en el negocio. Puede elegir un umbral para mensajes de correo electrónico con errores o retrasos, recibir alertas cuando se supera ese umbral y ver un informe de problemas de correo electrónico para cuentas de prioridad. Para obtener más información, consulte problemas [de correo electrónico para el informe de cuentas de prioridad en el EAC moderno.](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)

## <a name="before-you-begin"></a>Antes de empezar

La **característica de protección de** cuentas de prioridad que se describe en este tema solo está disponible para las organizaciones que cumplen los siguientes requisitos:

- Microsoft Defender para Office 365 Plan 2, incluidos aquellos con Office 365 E3, Office 365 E5, Microsoft 365 E5 o Microsoft 365 E5 Security.

La **característica de supervisión del** flujo de correo premium que se describe en este tema solo está disponible para las organizaciones que cumplen los siguientes requisitos:

- Su organización debe tener un recuento de licencias de al menos 10 000, ya sea de uno de los siguientes productos o una combinación de ellos: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5. Por ejemplo, su organización puede tener 3000 licencias de Office 365 E3 y 8500 Microsoft 365 E5, para un total de 11.500 licencias de los productos elegibles.
- Su organización necesita tener al menos 50 usuarios activos de Exchange Online mensuales.

> [!NOTE]
> Puede supervisar hasta 250 cuentas de prioridad.

### <a name="add-priority-accounts-from-the-setup-page"></a>Agregar cuentas de prioridad desde la página de instalación

Agregue cuentas de prioridad desde la **página de instalación.**

1. Vaya al Centro de administración de Microsoft 365 en <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .

2. Vaya a **Configurar**  >  **conocimientos de** la organización y elija **Ver en** Supervisar las cuentas **más importantes.**

3. Seleccione **Introducción o** **Administrar.**

4. En la **página Agregar cuentas de** prioridad, en el campo de búsqueda, escriba el nombre o la dirección de correo electrónico de la persona que desea agregar a la lista de cuentas de prioridad. También puede establecer su umbral de correo electrónico para mensajes de correo electrónico con errores o retrasos y obtener un informe semanal de problemas para cuentas de prioridad.

5. Seleccione el usuario y elija **Guardar**.

También puede agregar cuentas de prioridad desde la página Usuarios activos.

### <a name="add-priority-accounts-from-active-users-page"></a>Agregar cuentas de prioridad desde la página Usuarios activos

Agregue cuentas de prioridad desde la página Usuarios activos.

1. Vaya al Centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.

2. Vaya a **Usuarios**  >  **activos y** elija **...** en la parte superior de la página. Seleccione **Administrar cuentas de prioridad.**

3. Seleccione **Agregar cuentas y,** en la página Agregar cuentas de prioridad, en el campo de búsqueda, escriba el nombre de la persona que desea agregar a la lista de cuentas de prioridad. 

4. Seleccione el usuario y elija **Guardar**.

## <a name="remove-a-user-from-the-priority-accounts-list"></a>Quitar un usuario de la lista de cuentas de prioridad

1. Vaya al Centro de administración de Microsoft 365 en <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .

2. Vaya a **Configurar**  >  **conocimientos de** la organización y elija **Ver en** Supervisar las cuentas **más importantes.**

3. En la **página Supervisar la mayoría de las cuentas,** elija Cuentas de **prioridad** en Administrar **esta característica.**

4. En la **página Cuentas de** prioridad, seleccione el usuario o los usuarios que desea quitar de la lista y elija Quitar **cuentas.**

## <a name="related-topics"></a>Temas relacionados

[Uso de cuentas de prioridad en Microsoft 365](https://techcommunity.microsoft.com/t5/microsoft-365-blog/using-priority-accounts-in-microsoft-365/ba-p/1873314)