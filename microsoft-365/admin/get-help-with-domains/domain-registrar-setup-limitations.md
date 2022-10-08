---
title: Registradores de dominios con limitaciones de configuración
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: high
ms.collection:
- scotvorg
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
search.appverid:
- MET150
ROBOTS: NOINDEX
description: Algunos registradores de dominios ofrecen servicios limitados, lo que significa que no todas las características de Microsoft funcionarán con todos los dominios.
ms.openlocfilehash: 361faf93e2b923b0c16ce7051f43663998be4dc7
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68191197"
---
# <a name="domain-registrars-with-setup-limitations"></a>Registradores de dominios con limitaciones de configuración

[Crear registros DNS en DNSMadeEasy para Microsoft](#create-dns-records-at-dnsmadeeasy-for-microsoft)\
[Crear registros DNS en easyDNS para Microsoft](#create-dns-records-at-easydns-for-microsoft)\
[Crear registros DNS en Freenom para Microsoft](#create-dns-records-at-freenom-for-microsoft)\
[Crear registros DNS en MyDomain para Microsoft](#create-dns-records-at-mydomain-for-microsoft)\
[Crear registros DNS para Microsoft con DNS basado en Windows](#create-dns-records-for-microsoft-using-windows-based-dns)\
[Crear registros DNS cuando Google (eNom) administra su dominio](#create-dns-records-when-your-domain-is-managed-by-google-enom)\
[Crear registros DNS en 1&1 IONOS para Microsoft](#create-dns-records-at-11-ionos-for-microsoft)

Algunos registradores de dominios tienen limitaciones de servicio significativas, lo que significa que no todas las características de Microsoft funcionarán con todos los dominios. En este artículo se identifican limitaciones específicas para algunos registradores. 

## <a name="create-dns-records-at-dnsmadeeasy-for-microsoft"></a>Crear registros DNS en DNSMadeEasy para Microsoft

For DNSMadeEasy accounts, the domain you added was purchased from a separate domain registrar. DNSMadeEasy does not offer domain registration services. Your ability to log in at DNSMadeEasy and create the DNS record is sufficient proof of ownership.

## <a name="create-dns-records-at-easydns-for-microsoft"></a>Crear registros DNS en easyDNS para Microsoft

Los registros SRV no están disponibles actualmente en ningún paquete de servicio easyDNS. Es posible que tenga que actualizar a un nivel de servicio superior con easyDNS para agregar registros SRV necesarios para Teams.

## <a name="create-dns-records-at-freenom-for-microsoft"></a>Crear registros DNS en Freenom para Microsoft

The Freenom website doesn't support adding SRV records, which means that several Teams and Email features won't work. No matter which Microsoft plan you use, there are significant service limitations, and you may want to switch to a different DNS hosting provider.

## <a name="create-dns-records-at-mydomain-for-microsoft"></a>Crear registros DNS en MyDomain para Microsoft

The MyDomain website doesn't support SRV records, which means several Teams and Email features won't work. No matter which Microsoft plan you use, if you manage your DNS records at MyDomain, there are significant service limitations, and you might want to switch to a different DNS hosting provider.

## <a name="create-dns-records-for-microsoft-using-windows-based-dns"></a>Crear registros DNS para Microsoft con DNS basado en Windows

Go to the page that has the DNS records for your domain. If you're working in Windows Server 2008, go to **Start**, **Run**. If you're working in Windows Server 2012, press the **Windows key** and **r**. Type **dnsmgmnt.msc**, and then select **OK**. In DNS Manager, expand **DNS server name**,  **Forward Lookup Zones**. Select your domain. You're now ready to create the DNS records.

## <a name="create-dns-records-when-your-domain-is-managed-by-google-enom"></a>Crear registros DNS cuando Google (eNom) administra su dominio

If you purchased your domain through Google while signing up for your Google Apps for Work account, your DNS records are managed by Google but registered with eNom. You can access eNom, and create DNS, through the Google Domains page.

## <a name="create-dns-records-at-11-ionos-for-microsoft"></a>Crear registros DNS en 1&1 IONOS para Microsoft

1&1 IONOS no permite que un dominio tenga un registro MX y un registro Autodiscover CNAME de nivel superior. Esto limita las formas en que puede configurar Exchange Online para Microsoft. Hay una solución alternativa, pero le recomendamos que recurra a ella solo si ya tiene experiencia con la creación de subdominios en 1&1 IONOS.

Si a pesar de esta limitación de servicio, decide administrar sus propios registros DNS de Microsoft en 1&1 IONOS, siga los pasos de este artículo para comprobar su dominio y configurar registros DNS para correo electrónico, Skype Empresarial Online, etc.

1&1 IONOS requires a workaround so that you can use an MX record together with the CNAME records required for Microsoft email services. This workaround requires you to create a set of subdomains at 1&1 IONOS, and to assign them to CNAME records.

> [!NOTE]
> Make sure that you have at least two available subdomains before starting this procedure. We recommend this solution only if you already have experience with creating subdomains at 1&1 IONOS.

### <a name="basic-cname-records"></a>Registros CNAME básicos

1.  To get started, go to your domains page at 1&1 IONOS. You'll be prompted to log in.

1.  Seleccione **Administrar dominios**.

1.  En la página Centro de dominios, busque el dominio que desea actualizar y, a continuación, seleccione **Administrar subdominios**. Ahora creará dos subdominios y establecerá un valor de **Alias** para cada uno (esto es necesario porque 1&1 IONOS solo admite un registro CNAME de nivel superior, pero Microsoft requiere varios registros CNAME).

1.  En primer lugar, deberá crear el subdominio Autodiscover. En la sección **Información general de subdominio**, elija **Crear subdominio**.

1.  In the **Create Subdomain** box for the new subdomain, type or copy and paste only the **Create Subdomain** value from the following table. (You'll add the **Alias** value at a later step.)

    |Crear subdominio|Alias|
    |:----|:----|
    |autodescubrir|autodiscover.outlook.com|

1.  Seleccione **Crear subdominio**.

1.  En la sección **Información general de subdominio**, localice el subdominio autodescubrir que acaba de crear y, a continuación, seleccione el panel de (v) control para ese subdominio.

1.  En el área **Configuración del subdominio**, seleccione **Editar configuración DNS**.

1.  En la sección **Registros A/AAAA (direcciones IP)**, en el área **Dirección IP (registro A)**, seleccione **CNAME**.

1. En el cuadro de diálogo **Alias:**, escriba o copie y pegue solo el valor **Alias** de la tabla siguiente.

    |Crear subdominio|Alias|
    |:----|:----|
    |autodescubrir|autodiscover.outlook.com|

1. Active la casilla del aviso de declinación de responsabilidades **Soy consciente**.

1. Seleccione **Guardar**.

### <a name="additional-cname-records"></a>Registros CNAME adicionales

The additional CNAME records in the following procedure enable Skype for Business Online services. Use the same steps that you used for the two CNAME records you already created.

**Cree el tercer subdominio (Lyncdiscover)**

1.  En la sección **Información general de subdominio**, seleccione **Crear subdominio**.

1.  In the **Create Subdomain** box for the new subdomain, type or copy and paste only the **Create Subdomain** value from the following table. (You'll add the **Alias** value at a later step.)

    |Crear subdominio|Alias|
    |:----|:----|
    |lyncdiscover|webdir.online.lync.com|

1.  Seleccione **Crear subdominio**.

1.  En la página Centro de dominios, seleccione **Administrar subdominios**.

1.  In the **Subdomain Overview** section, find the lyncdiscover subdomain that you just created, and then select the Panel (v) control for that subdomain. In the **Subdomain Settings** area, select **Edit DNS Settings**.

1.  En la sección **Registros A/AAAA (direcciones IP)**, en el área **Dirección IP (registro A)**, seleccione **CNAME**.

1.  En el cuadro de diálogo **Alias:**, escriba o copie y pegue solo el valor **Alias** de la tabla siguiente.

    |Crear subdominio|Alias|
    |:----|:----|
    |lyncdiscover|webdir.online.lync.com|

1.  Active la casilla de verificación **Soy consciente** del aviso de declinación de responsabilidades y, a continuación, seleccione **Guardar**.

1.  En el cuadro de diálogo **Editar configuración DNS**, seleccione **Sí**.

**Crear el cuarto subdominio (SIP)**

1.  En la sección **Información general de subdominio**, elija **Crear subdominio**.

1.  In the **Create Subdomain** box for the new subdomain, type or copy and paste only the **Create Subdomain** value from the following table. (You'll add the **Alias** value a later step.)

    |Crear subdominio|Alias|
    |:----|:----|
    |sip|sipdir.online.lync.com|  

1.  Seleccione **Crear subdominio**.

1.  En la página Centro de dominios, seleccione **Administrar subdominios**.

1.  En la sección **Información general de subdominio**, localice el subdominio sip que acaba de crear y, a continuación, seleccione el Panel de (v) control para ese subdominio. <br/> En el área **Configuración del subdominio**, seleccione **Editar configuración DNS**.

1.  En la sección **Registros A/AAAA (direcciones IP)**, en el área **Dirección IP (registro A)**, seleccione **CNAME**.

1.  En el cuadro de diálogo **Alias:**, escriba o copie y pegue solo el valor **Alias** de la tabla siguiente.

    |Crear subdominio|Alias|
    |:----|:----|
    |sip|sipdir.online.lync.com|

1.  Active la casilla de verificación **Soy consciente** del aviso de declinación de responsabilidades y, a continuación, seleccione **Guardar**.

1.  En el cuadro de diálogo **Editar configuración DNS**, seleccione **Sí**.

### <a name="cname-records-needed-for-mdm"></a>Registros CNAME necesarios para MDM

Siga el procedimiento que usó para los otros cuatro registros CNAME, pero proporcione estos valores:

|Crear subdominio|Alias|
|:----|:----|
|enterpriseregistration|enterpriseregistration.windows.net|
|enterpriseenrollment|enterpriseenrollment-s.manage.microsoft.com|
