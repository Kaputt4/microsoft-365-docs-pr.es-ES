---
title: Buscar y corregir problemas después de agregar el dominio o los registros DNS
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- Tier2
- scotvorg
- highpri
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- VSBFY23
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 40398b0b-bdd0-4afd-ab5e-b5ae6b7990bf
description: Aprenda a rastrear los problemas que se producen al configurar un dominio personalizado asegurándose de que los registros DNS están configurados correctamente.
ms.openlocfilehash: 3dc9bafdfe2a1d9b07145cfa4f92bec7c76ec049
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "68728629"
---
# <a name="find-and-fix-issues-after-adding-your-domain-or-dns-records"></a>Buscar y corregir problemas después de agregar el dominio o los registros DNS

 **[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.yml)** si no encuentra lo que busca. 
  
La configuración del dominio para que funcione con Microsoft 365 puede ser un desafío. El sistema DNS puede ser un poco enrevesado y la configuración DNS de su dominio afecta a importantes actividades empresariales, como el correo electrónico.

> [!NOTE]
> Puede comprobar si hay problemas con el dominio comprobando su estado. Vaya a **Dominios** **de instalación** >  y vea las notificaciones en la columna **Estado**. Si ve un problema, seleccione los tres puntos (más acciones) y, a continuación, elija **Comprobar estado**. El panel que se abre describirá los problemas que se produzcan con el dominio.
  
## <a name="whats-going-on"></a>¿Qué sucede?

- [¿No se puede comprobar el dominio?](#cant-verify-your-domain)
    
- [¿Outlook no funciona?](#outlook-isnt-working)
    
- [El correo electrónico de todos se cambió a Microsoft 365 y solo quería que cambiara su correo electrónico.](#everyones-email-got-switched-to-microsoft-365-and-you-only-wanted-your-email-to-switch)

- [¿No se puede confirmar el estado de la cuenta educativa o sin fines de lucro?](#cant-confirm-non-profit-or-school-account-status)

- [¿Los servicios no funcionan con su dominio?](#services-not-working-with-your-domain)
    
- [¿El acceso a su sitio web no funciona?](#accessing-your-website-isnt-working)

## <a name="cant-verify-your-domain"></a>¿No puede comprobar su dominio?

Hay algunas razones comunes por las que la comprobación del dominio puede no funcionar según lo esperado:
  
1. **The verification record value isn't quite correct.** Doublecheck that you've copied and pasted the exact value into the TXT verification record at your DNS host. One common issue is not including the "MS=" part of the record. We need that too! 
    
2. **No se ha guardado el registro.** En algunos hosts DNS, tiene que llevar a cabo un paso adicional para guardar el archivo de zona (donde se almacena el registro DNS), de modo que se actualice a través de Internet. Asegúrese de que ha guardado los cambios para que Microsoft 365 pueda ver y comprobar el registro. 
    
3. **El registro no se ha actualizado a través de Internet.** Normalmente solo tarda unos minutos en poder ver el nuevo registro, pero en ocasiones puede tardar hasta unas horas. 
    
## <a name="outlook-isnt-working"></a>¿Outlook no funciona?

Si ha configurado correctamente el registro MX y otros registros DNS de su dominio pero el correo electrónico no funciona, podemos ayudarle a [solucionar los problemas relacionados con Outlook](/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues).
  
## <a name="everyones-email-got-switched-to-microsoft-365-and-you-only-wanted-your-email-to-switch"></a>El correo electrónico de todos se cambió a Microsoft 365 y solo quería que cambiara su correo electrónico.
<a name="BKMK_EmailSwitched"> </a>

Al agregar el dominio a Microsoft 365, normalmente el registro MX del dominio se actualiza (por usted o Microsoft 365) para que apunte a Microsoft 365 y todo el correo electrónico enviado a ese dominio comenzará a llegar a Microsoft 365. Asegúrese de que ha creado buzones en Microsoft 365 para todos los usuarios que tengan correo electrónico en su dominio ANTES de cambiar el registro MX.
  
¿Qué ocurre si no desea mover el correo electrónico de todos los usuarios de su dominio a Microsoft 365? En su lugar, puede realizar pasos para [probar Microsoft 365 con solo algunas direcciones de correo electrónico](../setup/domains-faq.yml).
  
## <a name="cant-confirm-non-profit-or-school-account-status"></a>¿No se puede confirmar el estado de la cuenta educativa o sin fines de lucro?
<a name="BKMK_validateAcct"> </a>

Hay un par de escenarios en los que solo tiene que comprobar el dominio de su organización y no configurar ningún servicio. Por ejemplo, para demostrar a Microsoft 365 que su organización cumple los requisitos para una suscripción educativa.
  
Consulte las instrucciones de [Comprobación del dominio de Microsoft 365 para demostrar la propiedad, el estado de la organización sin ánimo de lucro o el estado educativo, o para activar Yammer](../setup/domains-faq.yml) para asegurarse de que ha completado todos los pasos necesarios. Es un poco diferente para cada situación. 
  
## <a name="services-not-working-with-your-domain"></a>¿Los servicios no funcionan con su dominio?

Podemos ayudarle a localizar los problemas de configuración DNS de su dominio. El solucionador de problemas de dominios de Microsoft 365 le mostrará los registros que necesiten corregirse y exactamente en qué deben establecerse los registros. 

> [!TIP]
> ¿Ha configurado DNS correctamente pero el correo electrónico no funciona en la versión de escritorio de Outlook? Consulte los [diferentes escenarios de flujo de correo que puede tener con Microsoft 365](/exchange/mail-flow-best-practices/mail-flow-best-practices) para asegurarse de que tiene las cosas configuradas correctamente para su empresa. O bien, obtenga más ayuda para solucionar problemas con el correo electrónico aquí: [Solucionar problemas de Outlook](/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues). 
  
## <a name="accessing-your-website-isnt-working"></a>¿El acceso a su sitio web no funciona?

Si ha corregido cualquier problema de DNS y sigue teniendo dificultades, pruebe los siguientes procedimientos.
  
- Personas no puede acceder a su sitio web en *contoso.com*: [Seguimiento de problemas del sitio web](../setup/add-domain.md)
    
- No puede actualizar el registro A o CNAME para que apunte a su sitio web: [Actualizar registros DNS personalizados en Microsoft 365](../setup/add-domain.md)

## <a name="related-content"></a>Contenido relacionado

[Solución de problemas: Auditar datos sobre el cambio de dominio comprobado](/azure/active-directory/reports-monitoring/troubleshoot-audit-data-verified-domain) (artículo)\
[Preguntas más frecuentes sobre dominios](../setup/domains-faq.yml) (artículo)

