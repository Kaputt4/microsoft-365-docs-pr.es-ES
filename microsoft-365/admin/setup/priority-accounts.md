---
title: Administración y supervisión de cuentas de prioridad
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
description: Supervise los mensajes de correo electrónico con errores y retrasados enviados a o desde cuentas que tienen un gran impacto en el negocio.
ms.openlocfilehash: bc191873b3bbdcd84122a5430adeffe2b8c29fb1
ms.sourcegitcommit: 5ce64d510b15c6e2df32b78e6086f77156731e3c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/30/2020
ms.locfileid: "49477618"
---
# <a name="manage-and-monitor-priority-accounts"></a>Administración y supervisión de cuentas de prioridad

En cada organización de Microsoft 365, hay personas que son esenciales, como ejecutivos, líderes, administradores u otros usuarios que tienen acceso a información confidencial, de propietario o de prioridad alta.

Para ayudar a su organización a proteger estas cuentas, ahora puede designar a usuarios específicos como cuentas de prioridad y aprovechar las características específicas de la aplicación que les proporcionan una protección adicional. En el futuro, más aplicaciones y características admitirán cuentas prioritarias y, para comenzar, hemos anunciado dos funcionalidades: **protección de cuenta prioritaria** y **supervisión de flujo de correo Premium**.

- **Protección de cuenta de prioridad** : Microsoft defender para Office 365 (anteriormente, la protección contra amenazas avanzada de Office 365) admite cuentas prioritarias como etiquetas que se pueden usar en filtros de alertas, informes e investigaciones. Para obtener más información, consulte [etiquetas de usuario en Microsoft defender para Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/user-tags?view=o365-worldwide).
- La **supervisión del flujo de correo Premium** : el flujo de correo en buen estado puede ser crítico para el éxito del negocio y los retrasos o errores de la entrega pueden tener un impacto negativo en la empresa. Puede elegir un umbral para los correos electrónicos con errores o retrasados, recibir alertas cuando se supere ese umbral y ver un informe de los problemas de correo electrónico de las cuentas prioritarias. Para obtener más información, consulte [problemas de correo electrónico para el informe de cuentas prioritarias en el EAC moderno](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report).

## <a name="before-you-begin"></a>Antes de empezar

La característica de **protección de cuenta prioritaria** que se describe en este tema solo está disponible para las organizaciones que cumplan los siguientes requisitos:

- Microsoft defender para Office 365 plan 2, incluidos los que tienen Office 365 E3, Office 365 E5, Microsoft 365 E5 o Microsoft 365 E5 Security.

La característica de **supervisión del flujo de correo Premium** que se describe en este tema solo está disponible para las organizaciones que cumplan los siguientes requisitos:

- Su organización debe tener un número de licencias de al menos 10.000, de una de las dos o una combinación de los siguientes productos: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5. Por ejemplo, su organización puede tener 3000 licencias de Office 365 E3 y 8500 Microsoft 365 E5, para un total de licencias de 11.500 a partir de los productos autorizados.
- Su organización debe tener al menos 50 usuarios de Exchange Online mensuales activos.

> [!NOTE]
> Puede supervisar hasta 250 cuentas de prioridad.

### <a name="add-priority-accounts-from-the-setup-page"></a>Agregar cuentas de prioridad desde la página de configuración

Agregue cuentas de prioridad desde la **Página de configuración**.

1. Vaya al centro de administración de Microsoft 365 en <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .

2. Vaya a **configuración de**  >  los conocimientos de la **organización** y elija **Ver** en **supervisar las cuentas más importantes**.

3. Seleccione **Introducción** o **administrar**.

4. En la página **Agregar cuentas de prioridad** , en el campo de búsqueda, escriba el nombre o la dirección de correo electrónico de la persona que desea agregar a la lista de cuentas prioritarias. También puede establecer el umbral de correo electrónico para los correos electrónicos con errores o retrasados y obtener un informe semanal de los problemas de las cuentas prioritarias.

5. Seleccione el usuario y elija **Guardar**.

También puede agregar cuentas prioritarias desde la página usuarios activos.

### <a name="add-priority-accounts-from-active-users-page"></a>Agregar cuentas de prioridad de la página usuarios activos

Agregar cuentas de prioridad desde la página usuarios activos.

1. Vaya al Centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.

2. Vaya a **usuarios**  >  **activos** y elija **...** en la parte superior de la página. Seleccione **administrar cuentas de prioridad**.

3. Seleccione **Agregar cuentas** y, en el campo de búsqueda de la página **Agregar cuentas de prioridad** , escriba el nombre de la persona que desea agregar a la lista de cuentas prioritarias.

4. Seleccione el usuario y elija **Guardar**.

## <a name="remove-a-user-from-the-priority-accounts-list"></a>Quitar un usuario de la lista de cuentas prioritarias

1. Vaya al centro de administración de Microsoft 365 en <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .

2. Vaya a **configuración de**  >  los conocimientos de la **organización** y elija **Ver** en **supervisar las cuentas más importantes**.

3. En la página **supervisar la mayoría de las cuentas** , elija **cuentas prioritarias** en **administrar esta característica**.

4. En la página **cuentas prioritarias** , seleccione el usuario o los usuarios que desea quitar de la lista y elija, **quitar cuentas**.

## <a name="related-topics"></a>Temas relacionados

[Uso de cuentas prioritarias en Microsoft 365](https://techcommunity.microsoft.com/t5/microsoft-365-blog/using-priority-accounts-in-microsoft-365/ba-p/1873314)