---
title: Conectar los registros DNS en IONOS de 1&1 a Microsoft 365
f1.keywords:
- CSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5762c3ca-1de2-4999-bfe5-4c5e25a8957e
description: Obtenga información sobre cómo comprobar el dominio y configurar registros DNS para correo electrónico, Skype Empresarial En línea y otros servicios en 1&1 IONOS para Microsoft.
ms.openlocfilehash: 8afdfed0998a262b1df4c95a63e9086e4f71e5b6
ms.sourcegitcommit: ac0ae5c2888e2b323e36bad041a4abef196c9c96
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/12/2022
ms.locfileid: "64780685"
---
# <a name="connect-your-dns-records-at-ionos-by-11-to-microsoft-365"></a>Conectar los registros DNS en IONOS de 1&1 a Microsoft 365

 **[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.yml)** si no encuentra lo que busca.

Si IONOS de 1&1 es el proveedor de hospedaje dns, siga los pasos de este artículo para comprobar el dominio y configurar registros DNS para correo electrónico, Skype Empresarial En línea, etc.

## <a name="before-you-begin"></a>Antes de empezar

Tiene dos opciones para configurar registros DNS para el dominio:

- [**Use Dominio Conectar**](#use-domain-connect-to-verify-and-set-up-your-domain) Si no ha configurado el dominio con otro proveedor de servicios de correo electrónico, use los pasos de Conectar dominio para comprobar y configurar automáticamente el nuevo dominio para usarlo con Microsoft 365.

    OR

- [**Siga los pasos manuales.**](#create-dns-records-with-manual-setup) Compruebe el dominio siguiendo los pasos manuales que se indican a continuación y elija cuándo y qué registros se van a agregar al registrador de dominios. Esto le permite configurar nuevos registros MX (correo), por ejemplo, a su conveniencia.

## <a name="use-domain-connect-to-verify-and-set-up-your-domain"></a>Uso de Conectar de dominio para comprobar y configurar el dominio

Siga estos pasos para comprobar y configurar automáticamente el dominio IONOS by 1&1 con Microsoft 365:

1. En el Centro de administración de Microsoft 365, seleccione **Configuración** >  <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">**Dominios**</a> y seleccione el dominio que desea configurar.

    :::image type="content" source="../../media/dns-IONOS/IONOS-DomainConnects-1.png" alt-text="Seleccione el dominio en Microsoft 365.":::

1. Seleccione los tres puntos (más acciones) > elija **Iniciar configuración**.

    :::image type="content" source="../../media/dns-IONOS/IONOS-DomainConnects-2.png" alt-text="Seleccione Iniciar configuración.":::

1. En ¿Cómo desea conectar el dominio? página, seleccione **Continuar**.

1. En la página Agregar registros DNS, seleccione **Agregar registros DNS**.

1. En la página de inicio de sesión de IONOS by 1&1, inicie sesión en su cuenta y seleccione **Conectar** y **Permitir**.

    :::image type="content" source="../../media/dns-IONOS/IONOS-DomainConnects-3.png" alt-text="Seleccione Conectar y, a continuación, Permitir.":::

    Esto completa la configuración del dominio para Microsoft 365.

## <a name="create-dns-records-with-manual-setup"></a>Creación de registros DNS con configuración manual

Después de agregar estos registros a IONOS por 1&1, el dominio se configurará para trabajar con servicios Microsoft.

> [!CAUTION]
> Tenga en cuenta que IONOS de 1&1 no permite que un dominio tenga un registro MX y un registro CNAME de detección automática de nivel superior. Esto limita las formas en que puede configurar Exchange Online para Microsoft. Hay una solución alternativa, pero se recomienda emplearla **solo** si ya tiene experiencia con la creación de subdominios en IONOS por 1&1.
> Si a pesar de esta [limitación de servicio](../setup/domains-faq.yml) decide administrar sus propios registros DNS de Microsoft en IONOS por 1&1, siga los pasos de este artículo para comprobar su dominio y configurar registros DNS para correo electrónico, Skype Empresarial En línea, etc.

> [!NOTE]
> Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, vea [Encontrar y solucionar problemas después de agregar el dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).

### <a name="add-a-txt-record-for-verification"></a>Agregar un registro TXT para verificación

Antes de utilizar el dominio con Microsoft, tenemos que asegurarnos de que sea el propietario. Si puede iniciar sesión en la cuenta en el registrador de dominio y crear el registro DNS, Microsoft sabrá que es el propietario del dominio.

> [!NOTE]
> Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea.

1. Para empezar, vaya a la página dominios en IONOS 1&1 mediante [este vínculo](https://my.1and1.com/). You'll be prompted to log in.

1. Seleccione **Menú** y, a continuación, **dominios y SSL**.

   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-1.png" alt-text="Seleccione Dominios y SSL.":::

1. En **Acciones** para el dominio que desea actualizar, seleccione el control de engranaje y, a continuación **, dns.**

   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-2.png" alt-text="Seleccione DNS en la lista desplegable.":::

1. Seleccione **Agregar registro**.

    :::image type="content" source="../../media/dns-IONOS/IONOS-domains-3.png" alt-text="Seleccione Agregar registro.":::

1. Seleccione la sección **TXT** .

    :::image type="content" source="../../media/dns-IONOS/IONOS-domains-4.png" alt-text="Seleccione la sección TXT.":::

1. En la página Agregar un registro DNS, en los cuadros del nuevo registro, escriba o copie y pegue los valores de la tabla siguiente.

    |Nombre de host|Valor|TTL|
    |---|---|---|
    |(Deje este campo en blanco)|MS=ms *XXXXXXXX*  <br/> NOTA: Este es un ejemplo. Utilice aquí su valor de **Dirección de destino**, desde la tabla. [¿Cómo puedo encontrar esto?](../get-help-with-domains/information-for-dns-records.md)|1 hora|

1. Seleccione **Guardar**.

    :::image type="content" source="../../media/dns-IONOS/IONOS-domains-5.png" alt-text="Seleccione Guardar.":::

    Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.

Ahora que ha agregado el registro en el sitio de su registrador de dominios, volverá a Microsoft 365 y solicitará que busque el registro. Cuando Microsoft encuentre el registro TXT correcto, se comprobará su dominio.

Para comprobar el registro en Microsoft 365:

1. En el centro de administración, vaya a dominios **de Configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">**.**</a>

1. En la página Dominios, seleccione el dominio que está comprobando y seleccione **Iniciar configuración**.

    :::image type="content" source="../../media/dns-IONOS/IONOS-DomainConnects-2.png" alt-text="Seleccione Iniciar configuración.":::

1. Seleccione **Continuar**.

1. En la página **verificar dominio**, seleccione **verificar**.

> [!NOTE]
> Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).

### <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Agregar un registro MX para que el correo electrónico del dominio vaya a Microsoft

> [!NOTE]
> Si se ha registrado con 1und1.de, [inicie sesión aquí](https://go.microsoft.com/fwlink/?linkid=859152).

1. Para empezar, vaya a la página dominios en IONOS 1&1 mediante [este vínculo](https://my.1and1.com/). You'll be prompted to log in.

1. Seleccione **Menú** y, a continuación, **dominios y SSL**.

   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-1.png" alt-text="Seleccione Dominios y SSL.":::

1. En **Acciones** para el dominio que desea actualizar, seleccione el control de engranaje y, a continuación **, dns.**

   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-2.png" alt-text="Seleccione DNS en la lista desplegable.":::

1. Seleccione **Agregar registro**.

    :::image type="content" source="../../media/dns-IONOS/IONOS-domains-3.png" alt-text="Seleccione Agregar registro.":::

1. Seleccione la sección **MX** .

    :::image type="content" source="../../media/dns-IONOS/IONOS-domains-MX.png" alt-text="Seleccione la sección MX.":::

1. En la página Agregar un registro DNS, en los cuadros del nuevo registro, escriba o copie y pegue los valores de la tabla siguiente.

    |Nombre de host|Points to |Prioridad|TTL|
    |---|---|---|---|
    |@|*\<domain-key\>*.mail.protection.outlook.com  <br/>  NOTA: Obtenga su \<domain-key\> de su cuenta Microsoft. [¿Cómo puedo encontrarla?](../get-help-with-domains/information-for-dns-records.md)|10  <br/> Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](../setup/domains-faq.yml)|1 hora|

1. Seleccione **Guardar**.

    :::image type="content" source="../../media/dns-IONOS/IONOS-domains-MX-Save.png" alt-text="Seleccione Guardar.":::

1. Si ya aparece algún registro MX, elimínelos seleccionando la papelera **Eliminar registro** en la página **Agregar registro** .

    :::image type="content" source="../../media/dns-IONOS/IONOS-domains-Delete.png" alt-text="Seleccione Eliminar registro.":::

### <a name="add-the-cname-record-required-for-microsoft"></a>Agregar el registro CNAME necesario para Microsoft

> [!NOTE]
> Si se ha registrado con 1und1.de, [inicie sesión aquí](https://go.microsoft.com/fwlink/?linkid=859152).

1. Para empezar, vaya a la página dominios en IONOS 1&1 mediante [este vínculo](https://my.1and1.com/). You'll be prompted to log in.

1. Seleccione **Menú** y, a continuación, **dominios y SSL**.

   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-1.png" alt-text="Seleccione Dominios y SSL.":::

1. En **Acciones** para el dominio que desea actualizar, seleccione el control de engranaje y, a continuación **, dns.**

   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-2.png" alt-text="Seleccione DNS en la lista desplegable.":::

   Ahora podrá crear dos subdominios y establecer un valor **Alias** para cada uno.

   (Esto es necesario porque 1&1 IONOS solo admite un registro CNAME de nivel superior, pero Microsoft requiere varios registros CNAME).

   En primer lugar, deberá crear el subdominio Autodiscover.

1. Seleccione **Subdominios**.

   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-Subdomains.png" alt-text="Seleccione Subdominio.":::

1. Seleccione **Agregar subdominio**.

   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-add-subdomains.png" alt-text="Seleccione Agregar subdominios.":::

1. En el cuadro **Agregar subdominio** para el nuevo subdominio, escriba o copie y pegue solo el valor **Agregar subdominio** de la tabla siguiente. (Agregará el valor **Alias** en un paso posterior).

    |Agregar subdominio|Alias|
    |---|---|
    |autodescubrir|autodiscover.outlook.com|

1. En **Acciones** para el subdominio de **detección automática** que acaba de crear, seleccione el control de engranaje y, a continuación, seleccione **DNS** en la lista desplegable.

1. Seleccione **Agregar registro** y, a continuación, seleccione la sección **CNAME** .

1. En el cuadro de diálogo **Alias:**, escriba o copie y pegue solo el valor **Alias** de la tabla siguiente.

    |Agregar subdominio|Alias|
    |---|---|
    |autodescubrir|autodiscover.outlook.com|

1. Seleccione **Guardar**.

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Agregar un registro TXT para SPF para ayudar a prevenir el spam de correo electrónico

> [!IMPORTANT]
> No puede tener más de un registro TXT para el SPF de un dominio. Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado. Si ya tiene un registro de SPF para su dominio, no cree uno nuevo para Microsoft. En su lugar, agregue los valores de Microsoft necesarios al registro actual para que tenga un  *único*  registro SPF que incluya ambos conjuntos de valores. ¿Necesita ejemplos? Consulte los [Registros externos del sistema de nombres de dominio para Microsoft](../../enterprise/external-domain-name-system-records.md). Para validar el registro SPF, puede usar una de estas [herramientas de validación de SPF](../setup/domains-faq.yml).

> [!NOTE]
> Si se ha registrado con 1und1.de, [inicie sesión aquí](https://go.microsoft.com/fwlink/?linkid=859152).

1. Para empezar, vaya a la página dominios en IONOS 1&1 mediante [este vínculo](https://my.1and1.com/). You'll be prompted to log in.

1. Seleccione **Menú** y, a continuación, **dominios y SSL**.

   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-1.png" alt-text="Seleccione Dominios y SSL.":::

1. En **Acciones** para el dominio que desea actualizar, seleccione el control de engranaje y, a continuación **, dns.**

   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-2.png" alt-text="Seleccione DNS en la lista desplegable.":::

1. Seleccione **Agregar registro**.

    :::image type="content" source="../../media/dns-IONOS/IONOS-domains-3.png" alt-text="Seleccione Agregar registro.":::

1. Seleccione la sección **SPF (TXT).**

    :::image type="content" source="../../media/dns-IONOS/IONOS-domains-SPFTXT.png" alt-text="Seleccione la sección SPF (TXT).":::

1. En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la tabla siguiente.

    |Tipo|Nombre de host|Valor|TTL|
    |---|---|---|---|
    |SPF (TXT)|(Deje este campo en blanco).|v=spf1 include:spf.protection.outlook.com -all  <br/> **Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.|1 hora|

1. Seleccione **Guardar**.

   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-SPFTXT-Save.png" alt-text="Seleccione Guardar.":::

## <a name="advanced-option-skype-for-business"></a>Opción avanzada: Skype Empresarial

Solo seleccione esta opción si su organización usa Skype Empresarial para servicios de comunicación en línea, como chat, llamadas de conferencia y videollamadas, además de Microsoft Teams. Skype necesita 4 registros: 2 registros SRV para la comunicación de usuario a usuario y 2 registros CNAME para iniciar sesión y conectar usuarios al servicio.

### <a name="add-two-additional-cname-records"></a>Agregar dos registros CNAME adicionales

1. Para empezar, vaya a la página dominios en IONOS 1&1 mediante [este vínculo](https://my.1and1.com/). You'll be prompted to log in.

1. Seleccione **Menú** y, a continuación, **dominios y SSL**.

   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-1.png" alt-text="Seleccione Dominios y SSL.":::

1. En **Acciones** para el dominio que desea actualizar, seleccione el control de engranaje y, a continuación **, dns.**

   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-2.png" alt-text="Seleccione DNS en la lista desplegable.":::

   Ahora podrá crear dos subdominios y establecer un valor **Alias** para cada uno.

   (Esto es necesario porque 1&1 IONOS solo admite un registro CNAME de nivel superior, pero Microsoft requiere varios registros CNAME).

   En primer lugar, creará el subdominio lyncdiscover.

1. Seleccione **Subdominios**.

   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-Subdomains.png" alt-text="Seleccione Subdominio.":::

1. Seleccione **Agregar subdominio**.

   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-add-subdomains.png" alt-text="Seleccione Agregar subdominios.":::

1. En el cuadro **Agregar subdominio** para el nuevo subdominio, escriba o copie y pegue solo el valor **Agregar subdominio** de la tabla siguiente. (Agregará el valor **Alias** en un paso posterior).

    |Agregar subdominio|Alias|
    |---|---|
    |lyncdiscover   |webdir.online.lync.com  |

1. En **Acciones** para el subdominio **lyncdiscover** que acaba de crear, seleccione el control de engranaje y, a continuación, seleccione **DNS** en la lista desplegable.

1. Seleccione **Agregar registro** y, a continuación, seleccione la sección **CNAME** .

1. En el cuadro de diálogo **Alias:**, escriba o copie y pegue solo el valor **Alias** de la tabla siguiente.

    |Crear subdominio|Alias|
    |---|---|
    |lyncdiscover|webdir.online.lync.com|

1. Crear otro subdominio (SIP): seleccione **Agregar subdominio**.

1. En el cuadro **Agregar subdominio** para el nuevo subdominio, escriba o copie y pegue solo el valor **Agregar subdominio** de la tabla siguiente. (Agregará el valor **Alias** en un paso posterior).

    |Agregar subdominio|Alias|
    |---|---|
    |sip|sipdir.online.lync.com|

1. En **Acciones** para el subdominio que acaba de crear, seleccione el control de engranaje y, a continuación, seleccione **DNS** en la lista desplegable.

1. Seleccione **Agregar registro**.

    :::image type="content" source="../../media/dns-IONOS/IONOS-domains-3.png" alt-text="Seleccione Agregar registro.":::

1. Seleccione la sección **CNAME** .

1. en el cuadro **Alias:** , escriba o copie y pegue solo el valor **Alias** de la tabla siguiente.

    |Crear subdominio|Alias|
    |---|---|
    |sip|sipdir.online.lync.com|

1. Active la casilla de verificación **Soy consciente** del aviso de declinación de responsabilidades y, a continuación, seleccione **Guardar**.

## <a name="add-the-two-srv-records-required-for-microsoft"></a>Agregar los dos registros SRV necesarios para Microsoft

> [!NOTE]
> Si se ha registrado con 1und1.de, [inicie sesión aquí](https://go.microsoft.com/fwlink/?linkid=859152).

1. Para empezar, vaya a la página dominios en IONOS 1&1 mediante [este vínculo](https://my.1and1.com/). You'll be prompted to log in.

1. Seleccione **Menú** y, a continuación, **dominios y SSL**.

   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-1.png" alt-text="Seleccione Dominios y SSL.":::

1. En **Acciones** para el dominio que desea actualizar, seleccione el control de engranaje y, a continuación **, dns.**

   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-2.png" alt-text="Seleccione DNS en la lista desplegable.":::

1. Seleccione **Agregar registro**.

    :::image type="content" source="../../media/dns-IONOS/IONOS-domains-3.png" alt-text="Seleccione Agregar registro.":::

1. Seleccione la sección **SRV** .

    :::image type="content" source="../../media/dns-IONOS/IONOS-domains-SRV.png" alt-text="Seleccione la sección SRV.":::

1. En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la tabla siguiente.

    |Tipo|Servicio|Protocolo|Nombre de host|Points to |Prioridad|Peso|Puerto|TTL|
    |---|---|---|---|---|---|---|---|---|
    |SRV|_sip|_tls|(Deje este campo en blanco).|sipdir.online.lync.com|100|1|443|1 hora|
    |SRV|_sipfederationtls|tcp|(Deje este campo en blanco).|sipfed.online.lync.com|100|1|5061|1 hora|

1. Seleccione **Guardar**.

    :::image type="content" source="../../media/dns-IONOS/IONOS-domains-SRV-Save.png" alt-text="Seleccione Guardar.":::

1. Agregue el otro registro SRV.

> [!NOTE]
> Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, vea [Encontrar y solucionar problemas después de agregar el dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).

## <a name="advanced-option-intune-and-mobile-device-management-for-microsoft-365"></a>Opción avanzada: Intune y mobile Administración de dispositivos para Microsoft 365

Este servicio le ayuda a proteger y administrar de forma remota los dispositivos móviles que se conectan a su dominio. Mobile Administración de dispositivos necesita 2 registros CNAME para que los usuarios puedan inscribir dispositivos en el servicio.

### <a name="add-the-two-required-cname-records"></a>Agregar los dos registros CNAME necesarios

> [!IMPORTANT]
> Siga el procedimiento de subdominio que usó para los demás registros CNAME y proporcione los valores de la tabla siguiente.

1. Para empezar, vaya a la página dominios en IONOS 1&1 mediante [este vínculo](https://my.1and1.com/). You'll be prompted to log in.

1. Seleccione **Menú** y, a continuación, **dominios y SSL**.

   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-1.png" alt-text="Seleccione Dominios y SSL.":::

1. En **Acciones** para el dominio que desea actualizar, seleccione el control de engranaje y, a continuación **, dns.**

   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-2.png" alt-text="Seleccione DNS en la lista desplegable.":::

   Ahora podrá crear dos subdominios y establecer un valor **Alias** para cada uno.

   (Esto es necesario porque 1&1 IONOS solo admite un registro CNAME de nivel superior, pero Microsoft requiere varios registros CNAME).

   En primer lugar, creará el subdominio lyncdiscover.

1. Seleccione **Subdominios**.

   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-Subdomains.png" alt-text="Seleccione Subdominio.":::

1. Seleccione **Agregar subdominio**.

   :::image type="content" source="../../media/dns-IONOS/IONOS-domains-add-subdomains.png" alt-text="Seleccione Agregar subdominios.":::

1. En el cuadro **Agregar subdominio** para el nuevo subdominio, escriba o copie y pegue solo el valor **Agregar subdominio** de la tabla siguiente. (Agregará el valor **Alias** en un paso posterior).

    |Agregar subdominio|Alias|
    |---|---|
    |enterpriseregistration|enterpriseregistration.windows.net|

1. En **Acciones** para el subdominio **enterpriseregistration** que acaba de crear, seleccione el control de engranaje y, a continuación, seleccione **DNS** en la lista desplegable.

1. Seleccione **Agregar registro** y, a continuación, seleccione la sección **CNAME** .

1. En el cuadro de diálogo **Alias:**, escriba o copie y pegue solo el valor **Alias** de la tabla siguiente.

    |Agregar subdominio|Alias|
    |---|---|
    |enterpriseregistration|enterpriseregistration.windows.net|

1. Crear otro subdominio: seleccione **Agregar subdominio**.

1. En el cuadro **Agregar subdominio** para el nuevo subdominio, escriba o copie y pegue solo el valor **Agregar subdominio** de la tabla siguiente. (Agregará el valor **Alias** en un paso posterior).

    |Agregar subdominio|Alias|
    |---|---|
    |enterpriseenrollment|enterpriseenrollment-s.manage.microsoft.com|

1. En **Acciones** para el subdominio **de inscripción empresarial** que acaba de crear, seleccione el control de engranaje y, a continuación, seleccione **DNS** en la lista desplegable.

1. Seleccione **Agregar registro**.

    :::image type="content" source="../../media/dns-IONOS/IONOS-domains-3.png" alt-text="Seleccione Agregar registro.":::

1. Seleccione la sección **CNAME** .

1. en el cuadro **Alias:** , escriba o copie y pegue solo el valor **Alias** de la tabla siguiente.

    |Crear subdominio|Alias|
    |---|---|
    |enterpriseenrollment|enterpriseenrollment-s.manage.microsoft.com|

1. Active la casilla de verificación **Soy consciente** del aviso de declinación de responsabilidades y, a continuación, seleccione **Guardar**.
