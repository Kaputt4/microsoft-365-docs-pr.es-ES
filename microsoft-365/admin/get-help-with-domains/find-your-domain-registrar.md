---
title: Buscar su registrador de dominios
f1.keywords:
- CSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: high
ms.collection:
- Tier2
- scotvorg
- highpri
- M365-subscription-management
- Adm_O365
- Adm_O365_Setup
ms.custom:
- VSBFY23
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: b5b633ba-1e56-4a98-8ff5-2acaac63a5c8
description: Aprenda a encontrar su registrador de dominios y su proveedor de host DNS con la búsqueda InterNIC.
ms.openlocfilehash: 2cc67c4f351e86952f198e7b65dc70918f6525b3
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "68729795"
---
# <a name="find-your-domain-registrar"></a>Buscar su registrador de dominios

 **[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.yml)** si no encuentra lo que busca.

## <a name="domain-registrar"></a>Registrador de dominios

### <a name="find-your-domain-name-registrar"></a>Buscar el registrador de nombre de dominio

> [!NOTE]
> Solo los dominios que terminen en *.COM*, *.NET* y *.EDU* funcionarán con esta herramienta.

1. On the [InterNIC search page](https://go.microsoft.com/fwlink/p/?LinkId=402770), in the **Whois Search** box, type your domain. For example,  *contoso.com.*

2. Seleccione la opción **Dominio** y, a continuación, seleccione **Enviar**.

3. On the **Whois Search Results** page, locate the **Registrar** entry. This entry lists the organization that provides registrar service for your domain.

## <a name="dns-hosting-provider"></a>Proveedor de host DNS

### <a name="find-your-dns-hosting-provider"></a>Buscar su proveedor de host DNS

> [!NOTE]
> Solo los dominios que terminen en *.COM*, *.NET* y *.EDU* funcionarán con esta herramienta.

1. On the [InterNIC search page](https://go.microsoft.com/fwlink/p/?LinkId=402770), in the **Whois Search** box, type your domain. For example, contoso.com.

2. Seleccione la opción **Dominio** y, a continuación, seleccione **Enviar**.

3. En la página **Whois Search Results** (Resultados de la búsqueda de Whois), busque la primera entrada de **Name Server** (Servidor DNS).

4. Copy the name server (NS) information that appears after the colon (:), and then paste it into the **Search** box at the top of the page. Select **Nameserver**, and then select **Submit**.

5. On the **Whois Search Results** page, locate the **Registrar** entry. This entry lists your DNS hosting provider, the DNS provider who owns the name server for your domain.

---

