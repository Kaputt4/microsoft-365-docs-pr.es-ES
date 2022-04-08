---
title: Agregar registros DNS para conectarse a su dominio
f1.keywords:
- CSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: high
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- MET150
description: Conecte un dominio en cualquier proveedor de host DNS a Microsoft 365 mediante la verificación de su dominio y la actualización de los registros DNS en la cuenta del registrador.
ms.custom:
- okr_smb
- AdminSurgePortfolio
- AdminTemplateSet
- business_assist
- admindeeplinkMAC
ms.openlocfilehash: 08d28a5586c92d0e439170807f750150d9fbe17c
ms.sourcegitcommit: 5c9137f98e688ab23c144e75687399e390bb2601
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/07/2022
ms.locfileid: "64704787"
---
# <a name="add-dns-records-to-connect-your-domain"></a>Agregar registros DNS para conectarse a su dominio

Si ha comprado un dominio de un proveedor de host externo, puede conectarlo a Microsoft 365 actualizando los registros DNS de la cuenta del registrador.

Tras finalizar estos pasos, el dominio seguirá registrado en el host en el que compró el dominio, pero Microsoft 365 podrá usarlo para sus direcciones de correo electrónico (como usuario@sudominio.com) y otros servicios.

Si no agrega el dominio, los integrantes de la organización usarán el dominio onmicrosoft.com para las direcciones de correo electrónico hasta que lo agregue. Es importante que agregue el dominio antes de agregar usuarios, para evitar tener que configurarlo dos veces.

[Consulte las preguntas frecuentes sobre los dominios](../setup/domains-faq.yml) si no encuentra lo que busca debajo.

> [!TIP]
> Si necesita ayuda con los pasos descritos en este tema, considere la posibilidad de [trabajar con un especialista de Microsoft Small Business](https://go.microsoft.com/fwlink/?linkid=2186871). Con Business Assist, usted y sus empleados obtienen acceso de forma ininterrumpida a especialistas de pequeñas empresas a medida que hace crecer su negocio, desde la incorporación hasta el uso diario.

## <a name="step-1-add-a-txt-or-mx-record-to-verify-you-own-the-domain"></a>Paso 1: Agregar un registro TXT o MX para comprobar que es el propietario del dominio

### <a name="recommended-verify-with-a-txt-record"></a>Se recomienda: comprobarlo con un registro TXT

En primer lugar, tiene que demostrar que es el propietario del dominio que quiere agregar a Microsoft 365.

1. Inicie sesión en el Centro de administración de Microsoft 365 y seleccione **Mostrar todo** > **Configuración** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">**Dominios**</a>.
2. En una nueva pestaña o ventana del explorador, inicie sesión en su proveedor de host DNS y, después, busque el lugar donde administra la configuración de DNS (por ejemplo, Configuración del archivo de zona, Administrar dominios, Administrador de dominios, Administrador de DNS).
3. Vaya a la página del administrador de DNS de su proveedor y agregue a su dominio el registro TXT indicado en el centro de administración.

   Agregar este registro no afectará a su correo electrónico existente ni a otros servicios. Podrá quitarlo de forma segura una vez que su dominio se haya conectado a Microsoft 365.

   Ejemplo:

   - Nombre TXT: `@`
   - Valor TXT: MS=ms######## (ID único del centro de administración)
   - TTL: `3600` (o el proveedor predeterminado)

4. Guarde el registro, vuelva al centro de administración y, a continuación, seleccione **Comprobar**. Por lo general, los cambios de registro tardan alrededor de 15 minutos en efectuarse, pero a veces puede tardar más. Espere unos momentos y pruebe varias veces hasta detectar el cambio.

Cuando Microsoft encuentre el registro TXT correcto, se comprobará su dominio.

### <a name="verify-with-an-mx-record"></a>Comprobarlo con un registro MX

Si su registrador no permite agregar registros TXT, puede agregar un registro MX para comprobarlo.

1. Inicie sesión en el Centro de administración de Microsoft 365 y seleccione **Mostrar todo** > **Configuración** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">**Dominios**</a>.
2. En una nueva pestaña o ventana del explorador, inicie sesión en su proveedor de host DNS y, después, busque el lugar donde administra la configuración de DNS (por ejemplo, Configuración del archivo de zona, Administrar dominios, Administrador de dominios, Administrador de DNS).
3. Vaya a la página del administrador de DNS de su proveedor y agregue a su dominio el registro MX indicado en el centro de administración.

La **prioridad** de este registro MX debe ser la máxima de todos los registros MX existentes para el dominio. De lo contrario, puede interferir con el envío y la recepción de correo electrónico. Debe eliminar estos registros tan pronto como se haya completado la comprobación del dominio.

Asegúrese de configurar los campos con los siguientes valores:

- Tipo de registro: `MX`
- Prioridad: establecer en cualquier valor grande que aún no se haya usado.
- Nombre de host: `@`
- Dirección de destino: copie el valor del centro de administración y péguelo aquí.
- TTL: `3600` (o el proveedor predeterminado)

Cuando Microsoft encuentre el registro MX correcto, se comprobará su dominio.

## <a name="step-2-add-dns-records-to-connect-microsoft-services"></a>Paso 2: Agregar registros DNS para conectarse a los servicios de Microsoft

En una nueva pestaña o ventana del explorador, inicie sesión en su proveedor de host DNS y busque el lugar donde administra la configuración de DNS (por ejemplo, Configuración del archivo de zona, Administrar dominios, Administrador de dominios, Administrador de DNS).

Agregará varios tipos de registros DNS en función de los servicios que quiera habilitar.

### <a name="add-an-mx-record-for-email-outlook-exchange-online"></a>Agregar un registro MX para el correo electrónico (Outlook, Exchange Online)

**Antes de empezar:** si los usuarios ya tienen correo electrónico en su dominio (por ejemplo, usuario@sudominio.com), cree sus cuentas en el centro de administración antes de configurar los registros MX. De esta forma, seguirán recibiendo correo electrónico. Cuando actualice el registro MX de su dominio, todo el correo electrónico nuevo de cualquiera que use su dominio pasará a Microsoft 365. Cualquier correo electrónico ya existente permanecerá en el host de correo electrónico actual, a menos que decida [migrar el correo electrónico y los contactos a Microsoft 365.](../setup/migrate-email-and-contacts-admin.md)

Obtendrá la información del registro MX del asistente de configuración del dominio del centro de administración.

En el sitio web del proveedor de host, agregue un nuevo registro MX. Asegúrese de configurar los campos con los siguientes valores:

- Tipo de registro: `MX`
- Prioridad: defina la prioridad con el valor más alto posible, que suele ser `0`.
- Nombre de host: `@`
- Dirección de destino: copie el valor del centro de administración y péguelo aquí.
- TTL: `3600`

> [!NOTE]
> Exchange Online solo admite valores TTL de menos de 6 horas (21 600 segundos).

Guarde el registro y, a continuación, quite cualquier otro registro MX.

### <a name="add-cname-records-to-connect-other-services-teams-exchange-online-aad-mdm"></a>Agregar registros CNAME para conectarse a otros servicios (Teams, Exchange Online, AAD, MDM)

Obtendrá la información de los registros CNAME del asistente de configuración del dominio del centro de administración.

En el sitio web de su proveedor de host, agregue los registros CNAME para cada servicio al que quiera conectarse.
Asegúrese de configurar los campos con los siguientes valores para cada uno:

- Tipo de registro: `CNAME (Alias)`
- Host: pegue aquí los valores que copie del centro de administración.
- Dirección de destino: copie el valor del centro de administración y péguelo aquí.
- TTL: `3600` (o el proveedor predeterminado)

### <a name="add-or-edit-an-spf-txt-record-to-help-prevent-email-spam-outlook-exchange-online"></a>Agregar un registro TXT para SPF para ayudar a prevenir correo electrónico no deseado (Outlook, Exchange Online)

**Antes de empezar:** si ya tiene un registro de SPF para su dominio, no cree uno nuevo para Microsoft 365. En vez de eso, agregue los valores necesarios de Microsoft 365 para el registro actual en el sitio web de su proveedor de host, de modo que solo tenga un *único* registro de SPF que incluya ambos conjuntos de valores.

En el sitio web de su proveedor de host, edite el registro SPF existente o cree un nuevo registro SPF.
Asegúrese de configurar los campos con los siguientes valores:

- Tipo de registro: `TXT (Text)`
- Host: `@`
- Valor TXT: `v=spf1 include:spf.protection.outlook.com -all`
- TTL: `3600` (o el proveedor predeterminado)

Guarde el registro.

Para validar el registro de SPF, use una de estas[herramientas de validación de SPF](/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain).

SPF está diseñado para ayudar a evitar la suplantación de identidad, pero hay técnicas de suplantación de identidad contra las que SPF no puede proteger. Para protegerse de estos, una vez que haya configurado el SPF, también debe configurar DKIM y DMARC para Microsoft 365.

Para comenzar, consulte [Usar DKIM para validar el correo electrónico saliente enviado desde su dominio en Microsoft 365](../../security/office-365-security/use-dkim-to-validate-outbound-email.md) y[Usar DMARC para validar el correo electrónico en Microsoft 365](../../security/office-365-security/use-dmarc-to-validate-email.md).

### <a name="add-srv-records-for-communications-services-teams-skype-for-business"></a>Agregar registros SRV para servicios de comunicaciones (Teams, Skype Empresarial)

En el sitio web de su proveedor de host, agregue los registros SRV para cada servicio al que quiera conectarse.
Asegúrese de configurar los campos con los siguientes valores para cada uno:

- Tipo de registro: `SRV (Service)`
- Nombre: `@`
- Destino: copie el valor del centro de administración y péguelo aquí.
- Protocolo: copie el valor del centro de administración y péguelo aquí.
- Servicio: copie el valor del centro de administración y péguelo aquí.
- Prioridad: `100`
- Peso: `1`
- Puerto: copie el valor del centro de administración y péguelo aquí.
- TTL: `3600` (o el proveedor predeterminado)

Guarde el registro.

#### <a name="srv-record-field-restrictions-and-workarounds"></a>Restricciones y soluciones alternativas para campos de registros SRV

Algunos proveedores de host imponen restricciones en los valores de los campos de los registros SRV. Estas son algunas soluciones alternativas habituales para estas restricciones.

##### <a name="name"></a>Nombre

Si el proveedor de host no permite configurar este campo en **@**, déjelo en blanco. Use esta estrategia *solo* cuando el proveedor de host tiene campos separados para los valores de servicio y protocolo. De lo contrario, consulte las notas de servicio y protocolo a continuación.

##### <a name="service-and-protocol"></a>Servicio y protocolo

Si el proveedor de host no ofrece estos campos para los registros SRV, debe especificar los valores de **Servicio** y **Protocolo** en el campo de **Nombre** del registro. (Nota: dependiendo de su proveedor de host, el campo de **Nombre** puede llamarse de otra forma, como: **Host**, **Nombre de host** o **Subdominio**). Para agregar estos valores, cree una sola cadena, separando los valores con un punto.

Ejemplo: `_sip._tls`

##### <a name="priority-weight-and-port"></a>Prioridad, peso y puerto

Si el proveedor de host no ofrece estos campos para los registros SRV, debe especificarlos en el campo **Destino** del registro. (Nota: en función de su proveedor de host, el campo **Destino** puede llamarse de otra forma, como: **Contenido**, **Dirección IP** o **Host de destino**).

Para agregar estos valores, cree una sola cadena, con separación de los valores con espacios y *que terminen con un punto* (comuníquese con su proveedor si no está seguro). Los valores deben incluirse en este orden: Prioridad, Peso, Puerto, Destino.

- Ejemplo 1: `100 1 443 sipdir.online.lync.com.`
- Ejemplo 2: `100 1 443 sipdir.online.lync.com`

## <a name="related-content"></a>Contenido relacionado

[Cambiar los servidores DNS para configurar Microsoft 365 con cualquier registrador de dominios](change-nameservers-at-any-domain-registrar.md) (artículo)\
[Buscar y corregir problemas después de agregar el dominio o los registros DNS](find-and-fix-issues.md) (artículo)\
[Administrar dominios](/admin) (página de vínculo)
