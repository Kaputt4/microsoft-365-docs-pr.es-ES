---
title: Cambiar los servidores de nombres para configurar Microsoft 365 con cualquier registrador de dominios
f1.keywords:
- CSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- VSBFY23
- okr_smb
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
- GEU150
- GEA150
ms.assetid: a8b487a9-2a45-4581-9dc4-5d28a47010a2
description: Obtenga información sobre cómo agregar y configurar el dominio en Microsoft 365 para que sus servicios, como el correo electrónico y Skype Empresarial Online, usen su propio nombre de dominio.
ms.openlocfilehash: e33bfad12c3785e95ca328c4f0e82ab640d549d0
ms.sourcegitcommit: 2f6a7410e9919f753a759c1ada441141e18f06fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2022
ms.locfileid: "67085957"
---
# <a name="change-nameservers-to-set-up-microsoft-365-with-any-domain-registrar"></a>Cambiar los servidores de nombres para configurar Microsoft 365 con cualquier registrador de dominios

 **[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.yml)** si no encuentra lo que busca.

Siga estas instrucciones para agregar y configurar el dominio en Microsoft 365 para que sus servicios, como el correo electrónico y Teams, usen su propio nombre de dominio. Para ello, comprobará el dominio y, a continuación, cambiará los servidores de nombres del dominio a Microsoft 365 para que pueda configurar los registros DNS correctos. Siga estos pasos si las siguientes instrucciones describen su situación:

- Tiene su propio dominio y quiere configurarlo para que funcione con Microsoft 365.

- Quiere que Microsoft 365 administre los registros DNS automáticamente. (Si lo prefiere, puede [administrar sus propios registros DNS](../setup/add-domain.md)).

## <a name="add-a-txt-or-mx-record-for-verification"></a>Agregar un registro TXT o MX para su verificación

> [!NOTE]
> Sólo debe crear uno de los dos registros. TXT es el tipo de registro preferido, pero algunos proveedores de host DNS no lo admiten. De ser así, puede crear un registro MX.

Antes de utilizar el dominio con Microsoft 365, tenemos que asegurarnos de que sea el propietario. Si puede iniciar sesión en la cuenta en el registrador de dominio y crear el registro DNS, Microsoft 365 sabrá que es el propietario del dominio.

> [!NOTE]
> Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea.

### <a name="find-the-area-on-your-dns-hosting-providers-website-where-you-can-create-a-new-record"></a>Busque el área en el sitio web del proveedor de hospedaje DNS donde puede crear un nuevo registro.

1. Inicie sesión en el sitio web del proveedor de host DNS.

2. Elija su dominio.

3. Busque la página donde puede modificar los registros DNS para su dominio.

### <a name="create-the-record"></a>Creación del registro

En función de si se está creando un registro TXT o un registro MX, siga uno de los procedimientos siguientes:

**Si crea un registro TXT, utilice estos valores:**

<br>

****

|Tipo de registro|Alias o nombre de host|Valor|TTL|
|---|---|---|---|
|TXT|Realice una de las siguientes acciones: escriba **@**, deje el campo vacío o escriba el nombre de dominio.    <p> **Nota**: Los distintos hosts DNS tienen requisitos diferentes para este campo.|MS=ms *XXXXXXXX* <p> **Nota:** esto es un ejemplo. Use su valor **Dirección de destino** específico aquí, de la tabla de Microsoft 365. [¿Cómo puedo encontrar esto?](../get-help-with-domains/information-for-dns-records.md)|Configure este valor como **1 hora** o el equivalente en minutos ( **60** ), segundos ( **3600** ), etc.|
|||||

**Si crea un registro MX, utilice estos valores:**

<br>

****

|Tipo de registro|Alias o nombre de host|Valor|Prioridad|TTL|
|---|---|---|---|---|
|MX|Escriba **@** o el nombre del dominio. |MS=ms *XXXXXXXX* **Nota:** Este es un ejemplo. Use su valor **Dirección de destino** específico aquí, de la tabla de Microsoft 365. [¿Cómo puedo encontrar esto?](../get-help-with-domains/information-for-dns-records.md)|Para **Prioridad**, para evitar conflictos con el registro MX usado para el flujo de correo, use una prioridad más baja que la prioridad de cualquier registro MX existente. Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](../setup/domains-faq.yml)|Configure este valor como **1 hora** o el equivalente en minutos ( **60** ), segundos ( **3600** ), etc.|
||||||

### <a name="save-the-record"></a>Guardar el registro

Ahora que ha agregado el registro en el sitio de su registrador de dominios, volverá a Microsoft 365 y solicitará que busque el registro.

Cuando Microsoft 365 encuentre el registro TXT correcto, se comprobará su dominio.

1. En el centro de administración, diríjase a la página **configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a>.

2. En la página **Dominios**, elija el dominio que está verificando.

3. En la página de **Configuración**, elija **Iniciar configuración**.

4. En la página **verificar dominio**, seleccione **verificar**.

> [!NOTE]
> Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).

## <a name="change-your-domains-nameserver-ns-records"></a>Cambiar los registros del servidor de nombres (o NS) de su dominio

Cuando llegue al último paso del Asistente para la configuración de dominios en Microsoft 365, le queda una tarea. Para configurar el dominio con servicios de Microsoft 365, como el correo electrónico, cambie los registros de servidor de nombres (o NS) del dominio en el registrador de dominios para que apunten a los servidores de nombres principales y secundarios de Microsoft 365. A continuación, dado que Microsoft 365 hospeda el DNS, los registros DNS necesarios para los servicios se configuran automáticamente. Puede actualizar los registros NS usted mismo siguiendo los pasos que su registrador de dominios debe proporcionar en el apartado de ayuda de su sitio web. Si no está familiarizado con DNS, pónganse en contacto con el registrador del dominio.

::: moniker range="o365-worldwide"

Para cambiar los servidores DNS en el sitio web del registrador de dominios usted mismo, haga lo siguiente:

1. Busque el área en el sitio web del registrador de dominios, donde puede cambiar los servidores de nombres de su dominio o un área donde pueda usar servidores de nombres personalizados.

2. Cree registros nameserver o edite los registros nameserver existentes para que coincidan con los valores siguientes:

    - Nombreservidor de nombres: ns1.bdm.microsoftonline.com
    - Segundo servidor de nombres: ns2.bdm.microsoftonline.com
    - Tercer servidor de nombres: ns3.bdm.microsoftonline.com
    - Cuarto servidor de nombres: ns4.bdm.microsoftonline.com

   > [!TIP]
   > Es mejor agregar los cuatro registros, pero si el registrador solo admite dos, agregue **ns1.bdm.microsoftonline.com** y **ns2.bdm.microsoftonline.com**.

3. Guarde los cambios.

> [!CAUTION]
> Al cambiar los registros NS del dominio para que apunten a los servidores de nombres de Microsoft 365, se verán afectados todos los servicios que están asociados actualmente al dominio. Si ha omitido algún paso del asistente, como añadir direcciones de correo electrónico, o si utiliza el dominio para blogs, cestas de compra u otros servicios, se necesitan realizar más pasos. De lo contrario, este cambio podría traducirse en una interrupción del servicio, como por ejemplo que no se pueda acceder al correo electrónico o a su sitio web.

::: moniker-end

::: moniker range="o365-21vianet"

1. En el sitio web del registrador de dominios, busque el área donde poder modificar los servidores DNS del dominio.

2. Cree dos registros de servidor DNS o modifique los existentes para que coincidan con los valores siguientes:

   - Nombreservidor de nombres: ns1.dns.partner.microsoftonline.cn
   - Segundo servidor de nombres: ns2.dns.partner.microsoftonline.cn

   > [!TIP]
   > Debe usar al menos dos registros nameserver. Si aparece algún otro servidor de nombres, puede eliminarlos o cambiarlos a **ns3.dns.partner.microsoftonline.cn** y **ns4.dns.partner.microsoftonline.cn**.

3. Guarde los cambios.

> [!CAUTION]
> Al cambiar los registros NS del dominio para que apunten al Office 365 operado por 21Servidores de nombres deVianet, se verán afectados todos los servicios que están asociados actualmente al dominio. Si ha omitido algún paso del asistente, como añadir direcciones de correo electrónico, o si utiliza el dominio para blogs, cestas de compra u otros servicios, se necesitan realizar más pasos. De lo contrario, este cambio podría traducirse en una interrupción del servicio, como por ejemplo que no se pueda acceder al correo electrónico o a su sitio web.

::: moniker-end

Por ejemplo, aquí se indican algunos pasos adicionales que podrían ser necesarios para el hospedaje de correo electrónico y sitios web:

- Mueva todas las direcciones de correo electrónico que usan su dominio a Microsoft 365 antes de cambiar los registros de NS.

- ¿Desea agregar un dominio que se usa actualmente con una dirección de sitio web, como `https://www.fourthcoffee.com`? Puede seguir estos pasos mientras agrega el dominio para mantener su sitio web hospedado donde se hospeda el sitio ahora, de modo que las personas puedan seguir llegando al sitio web después de cambiar los registros NS del dominio para que apunten a Microsoft 365.

1. En el centro de administración, diríjase a la página **configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a>.

2. En la página **Dominios**, seleccione un dominio.

3. En la página de detalles del dominio, seleccione la pestaña **Registros DNS** .

4. Seleccione **Agregar registro**.

5. En el panel **Agregar un registro DNS personalizado**, en la lista desplegable **Tipo**, seleccione **A (Dirección).**

6. En el cuadro **Nombre de host o Alias** , escriba **@**.

7. En el cuadro **Dirección IP** , escriba la dirección IP estática del sitio web donde se hospeda actualmente. Por ejemplo, 172.16.140.1.

   > [!IMPORTANT]
   > Debe ser una dirección IP _estática_ para el sitio web, no una dirección IP _dinámica_ . Para asegurarse de que puede obtener una dirección IP estática para su sitio web público, consulte el sitio que hospeda el sitio web.

8. Si desea cambiar la configuración de TTL para el registro, seleccione una nueva longitud de tiempo en la lista desplegable **TTL** . De lo contrario, continúe con el paso 9.

9. Seleccione **Guardar**.

Además, puede crear un registro CNAME para ayudar a los clientes a encontrar su sitio web.

1. Seleccione **Agregar registro**.
2. En el panel **Agregar un registro DNS personalizado** , en la lista desplegable **Tipo** , seleccione **CNAME (Alias).**.
3. En el cuadro **Nombre de host o Alias** , escriba **www**.
4. En el cuadro **Puntos a dirección** , escriba el nombre de dominio completo (FQDN) del sitio web. Por ejemplo, **contoso.5om**.
5. Si desea cambiar la configuración de TTL para el registro, seleccione una nueva longitud de tiempo en la lista desplegable **TTL** . De lo contrario, continúe con el paso 6.
6. Seleccione **Guardar**.

Una vez actualizados los registros nameserver para que apunten a Microsoft, se completa la configuración del dominio. Email se enruta a Microsoft y el tráfico a la dirección del sitio web continúa a su host del sitio web actual."

> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. A continuación, el correo electrónico de Microsoft y otros servicios estarán configurados para que funcionen con su dominio.

## <a name="related-content"></a>Contenido relacionado

[Agregar registros DNS para conectar el dominio](create-dns-records-at-any-dns-hosting-provider.md) (artículo)\
[Buscar y corregir problemas después de agregar el dominio o los registros DNS](find-and-fix-issues.md) (artículo)\
[Administrar dominios](/admin) (página de vínculo)
