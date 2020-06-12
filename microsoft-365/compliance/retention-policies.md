---
title: Obtenga información sobre directivas de retención para retener o eliminar automáticamente el contenido
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Utilice una directiva de retención para decidir de forma proactiva si desea retener el contenido, eliminarlo o ambas cosas, retener y luego eliminar el contenido, aplicar una única directiva a toda la organización o a lugares o usuarios específicos, y aplicar una directiva a todo el contenido o a los contenidos que cumplan condiciones específicas.
ms.openlocfilehash: 377c5e1f21938204123de298e620a3d0d2bb9755
ms.sourcegitcommit: b03a7ad0a80f8b839f40b8d396ab3a049491a12f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/10/2020
ms.locfileid: "44695143"
---
# <a name="learn-about-retention-policies"></a>Información sobre las directivas de retención

>*[Instrucciones de licencias de Microsoft 365 para la seguridad y el cumplimiento](https://aka.ms/ComplianceSD).*

Para la mayoría de las organizaciones, el volumen y la complejidad de los datos se incrementa diariamente: correo electrónico, documentos, mensajes instantáneos y mucho más. Administrar o gobernar esta información es importante, ya que necesita:
  
- **Cumplir de forma proactiva con las normas del sector y las directivas internas** que le exigen retener contenido durante un período mínimo de tiempo. Por ejemplo, la ley Sarbanes-Oxley puede exigirle que retenga determinados tipos de contenido durante siete años. 
    
- **Reducir el riesgo en caso de litigio o una infracción de seguridad** al eliminar de forma permanente contenido antiguo que ya no es necesario mantener. 
    
- **Ayudar a su organización a compartir los conocimientos de manera eficaz y ser más ágil** al asegurarse de que los usuarios trabajan solo con contenido actualizado y relevante para ellos. 
    
Una directiva de retención puede ayudarle a lograr todos estos objetivos. Administrar el contenido suele requerir dos acciones:
  
- **Conservar** contenido para que no pueda eliminarse de forma permanente antes del fin del período de retención. 
    
- **Eliminar** contenido de forma permanente al final del período de retención. 
    
Con una directiva de retención, puede:
  
- Decidir de forma proactiva si quiere retener o eliminar el contenido, o ambas opciones: retener y, a continuación, eliminar el contenido.
    
- Aplicar una única directiva a toda la organización o a ubicaciones o usuarios específicos.
    
- Aplicar una directiva a todo el contenido o solo cuando cumpla condiciones específicas, como contener palabras clave o [tipos de información confidencial](what-the-sensitive-information-types-look-for.md).
    
Cuando el contenido está sujeto a una directiva de retención, los usuarios pueden seguir editando el contenido y trabajando con él como si no hubiera cambiado nada. El contenido se conserva en su lugar, en su ubicación original. Sin embargo, si alguien edita o elimina el contenido sujeto a la directiva de retención, se guarda una copia del contenido original en una ubicación segura, donde se conserva mientras la directiva de retención para ese contenido está vigente. Para más información, vea la sección [Cómo funciona una directiva de retención con el contenido local](#how-a-retention-policy-works-with-content-in-place) en esta página.
  
Además, algunas organizaciones deben cumplir con regulaciones como la Regla 17a-4 de la Comisión de Bolsa y Valores​​ de Estados Unidos (SEC). Este reglamento requiere que, después de que se active una directiva de retención, no se pueda desactivar o hacer menos restrictiva. Para cumplir este requisito, puede usar el **Bloqueo de conservación**. Después de que se haya bloqueado una directiva de retención, ninguna persona puede desactivarla ni hacerla menos restrictiva, ni siquiera un administrador. Para más información, vea la sección [Usar el bloqueo de conservación para cumplir con los requisitos reglamentarios](#use-preservation-lock-to-comply-with-regulatory-requirements) en esta página.

## <a name="how-a-retention-policy-works-with-content-in-place"></a>Funcionamiento de una directiva de retención local

Cuando se incluyen ubicaciones tales como un sitio o buzón en una directiva de retención, el contenido permanece en su ubicación original. Los usuarios pueden seguir trabajando con sus documentos o buzones como si nada hubiera cambiado. Sin embargo, si modifican o eliminan contenido que esté incluido en la directiva de retención, se retendrá una copia del contenido tal como era cuando se aplicó la directiva.
  
- Para sitios de SharePoint y OneDrive: la copia se conserva en la biblioteca de **Suspensión para conservación**. Tenga en cuenta que la biblioteca de Suspensión para conservación consume cuota de almacenamiento del sitio.

- Para el correo electrónico y las carpetas públicas: la copia se conserva en la carpeta **Elementos recuperables**. 

- Para el contenido de Teams: la copia se conserva en la carpeta **Elementos recuperables** de Exchange.

- Para grupos de Microsoft 365 ([anteriormente grupos de Office 365](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)): 
    - El buzón de grupo se conserva en la carpeta **Elementos recuperables** de Exchange.
    - Todo el contenido del sitio se conserva en la biblioteca de **Suspensión para conservación**.

> [!NOTE]
> La biblioteca de Suspensión para conservación consume almacenamiento que no está exento de la cuota de almacenamiento de un sitio. Es posible que necesite aumentar el almacenamiento al usar las directivas de retención para los grupos de Microsoft 365 y SharePoint.
> 
Ni estas ubicaciones seguras ni el contenido retenido son visibles para la mayoría de los usuarios. Con una directiva de retención, ni siquiera es necesario que los usuarios sepan que su contenido está sujeto a la directiva.

Para obtener información más detallada sobre cómo funcionan las directivas de retención con distintas cargas de trabajo, consulte los artículos siguientes:

- [Más información sobre las directivas de retención para SharePoint y OneDrive](retention-policies-sharepoint.md)
- [Más información sobre las directivas de retención para Microsoft Teams](retention-policies-teams.md)
- [Más información sobre las directivas de retención para Exchange](retention-policies-exchange.md)

## <a name="the-principles-of-retention-or-what-takes-precedence"></a>Los principios de retención o qué tiene precedencia

Es posible o incluso probable que el contenido tenga varias directivas de retención aplicadas, cada una con una acción (conservar, eliminar o retener y luego eliminar) y un período de retención diferentes. ¿Qué tiene prioridad? En el nivel más alto, puede estar seguro de que el contenido que se conserva por una directiva de retención no lo puede eliminar de forma permanente otra directiva de retención.
  
![Diagrama de los principios de retención](../media/1693d6ec-b340-4805-9da3-89aa41bc6afb.png)
  
Para entender cómo diferentes directivas de retención se aplican al contenido, tenga en cuenta estos principios de retención:
  
1. **La retención gana a la eliminación.** Suponga que una directiva de retención está configurada para eliminar el correo electrónico de Exchange después de tres años, pero otra directiva de retención está configurada para que se conserve el correo electrónico de Exchange durante cinco años y después se elimine. Todo el contenido que llegue a tres años de antigüedad se eliminará y quedará oculto de la vista de los usuarios, pero se mantendrá en la carpeta elementos recuperables hasta que llegue a la antigüedad de cinco años, cuando se elimine de forma permanente. 
    
2. **El período de retención más largo gana**. Si el contenido está sujeto a varias directivas de retención que retienen el contenido, se conservará hasta el final del período de retención más largo. 
    
3. **La inclusión explícita gana a la inclusión implícita**. Esto significa que: 
    
    1. Si un usuario asigna manualmente una etiqueta de retención con configuración de retención a un elemento, como un correo electrónico de Exchange o un documento de OneDrive, esa etiqueta de retención tiene prioridad sobre una directiva de retención asignada en el nivel de sitio o buzón, y una etiqueta de retención predeterminada asignada por la biblioteca de documentos. Por ejemplo, si la etiqueta de retención explícita está configurada para retener el contenido durante 10 años, pero la directiva de retención asignada al sitio está configurada para que la conservación sea de solo cinco años, la etiqueta de retención tendrá prioridad. Las etiquetas de retención de aplicación automática se consideran implícitas en lugar de explícitas, porque Microsoft 365 las aplica automáticamente.
    
    2. Si una directiva de retención incluye una ubicación específica, como el buzón de un usuario específico o una cuenta de OneDrive, esa directiva de retención tiene prioridad sobre otra directiva de retención que se aplica a los buzones de todos los usuarios o a las cuentas de OneDrive pero que no incluye específicamente el buzón de ese usuario.
    
4. **El período de eliminación más corto gana.** De forma similar, si el contenido está sujeto a varias directivas de retención que eliminan contenido sin un periodo de retención, se eliminará el contenido al final del período de retención más corto. 
    
Tenga en cuenta que los principios de retención funcionan como un flujo de desempate de arriba abajo: si las reglas aplicadas por todas las directivas de retención o etiquetas de retención son las mismas en un nivel, el flujo baja al siguiente nivel para determinar la precedencia de la regla que se aplica.
  
Por último, una directiva o etiqueta de retención no puede eliminar permanentemente ningún contenido que esté en espera para eDiscovery. Cuando se libera la retención, el contenido vuelve a ser apto para el proceso de limpieza descrito anteriormente.

## <a name="use-preservation-lock-to-comply-with-regulatory-requirements"></a>Usar el bloqueo de conservación para cumplir los requisitos normativos

Algunas organizaciones podrían tener que cumplir con las reglas que definen los organismos reguladores, como la regla 17a-4 de la SEC (Comisión de intercambio y valores), lo que requiere que, después de activar una directiva de retención, esta no se pueda desactivar ni hacer menos restrictiva. 

El bloqueo de conservación garantiza que su organización cumpla con los requisitos de las normativas, ya que bloquea una directiva de retención de forma que nadie, incluido el administrador, pueda desactivar la directiva o hacer que sea menos restrictiva.
  
Cuando una directiva de retención está bloqueada:

- Nadie puede desactivarla
- Las ubicaciones se pueden agregar pero no quitar 
- El contenido sujeto a la directiva no se puede modificar ni eliminar durante el período de retención.
- Puede ampliar un período de retención, pero no disminuirlo

En resumen, una directiva de retención bloqueada se puede incrementar o ampliar, pero no se puede reducir ni desactivar.
  
> [!IMPORTANT]
> Antes de bloquear una directiva de retención, es importante que comprenda el impacto y confirme si es necesario para que la organización cumpla con los requisitos de cumplimiento.

## <a name="releasing-a-retention-policy"></a>Publicar una directiva de retención

El uso de la directiva de retención no tiene un bloqueo de conservación, puede desactivar o eliminar una directiva de retención en cualquier momento. 

Al hacerlo, el contenido de SharePoint o de OneDrive que se retiene en la biblioteca de conservación de documentos se elimina de forma inmediata y permanente. A partir de ahora, y para evitar pérdidas accidentales de datos, existe un período de gracia de 30 días durante el cual la expiración del contenido para esa directiva no se produce en la biblioteca de conservación de documentos, de modo que puede restaurar desde allí el contenido si lo ve necesario. Además, no puede eliminar manualmente este contenido durante el período de gracia.

Puede activar la directiva de retención durante el período de gracia y no se eliminará ningún contenido para esa directiva.

Este periodo de gracia de 30 días en SharePoint y OneDrive corresponde a la retención de retraso de 30 días de Exchange. Para obtener más información, consulte [Gestionar buzón con una retención de retraso](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold).

## <a name="use-a-retention-policy-instead-of-older-features"></a>Usar una directiva de retención en lugar de características anteriores

Se puede aplicar fácilmente una sola directiva de retención a toda la organización y las ubicaciones de Microsoft 365, como Exchange Online, SharePoint Online, OneDrive y Grupos de Microsoft 365. Si necesita retener o eliminar contenido en cualquier lugar de Microsoft 365, se recomienda usar una directiva de retención y, opcionalmente, complementarla con [etiquetas de retención](labels.md).
  
Si ha usado anteriormente otras configuraciones para retener o eliminar contenido en Microsoft 365, seguirán funcionando en paralelo con las directivas de retención y las etiquetas de retención. Sin embargo, le recomendamos que, en adelante, utilice directivas de retención y etiquetas de retención. Proporcionan un mecanismo único para administrar centralmente tanto la retención como la eliminación de contenido en Microsoft 365.

Las características anteriores que puede haber usado son:
  
**Características anteriores de Exchange Online:**

- [Conservación local y Retención por juicio](https://go.microsoft.com/fwlink/?linkid=846124) (suspensión de eDiscovery) 

- [Cómo identificar el tipo de retención en un buzón de Exchange Online](identify-a-hold-on-an-exchange-online-mailbox.md)
    
- [Etiquetas de retención y directivas de retención](https://go.microsoft.com/fwlink/?linkid=846125), lo que también se conoce como [administración de registros de mensajes (MRM)](https://go.microsoft.com/fwlink/?linkid=846126) (solo eliminación)
    
Vea también [Retirada de herramientas heredadas de eDiscovery](legacy-ediscovery-retirement.md)


**Características anteriores de SharePoint y OneDrive:**

- [Agregar contenido a un caso y poner orígenes en suspensión en el Centro de eDiscovery](https://docs.microsoft.com/SharePoint/governance/add-content-to-a-case-and-place-sources-on-hold-in-the-ediscovery-center) (suspensión de eDiscovery) 
    
- [Directivas de eliminación de documentos](https://support.office.com/article/Create-a-document-deletion-policy-in-SharePoint-Server-2016-4fe26e19-4849-4eb9-a044-840ab47458ff) (solo eliminación)
    
- [Configuración de administración de registros local](https://support.office.com/article/7707a878-780c-4be6-9cb0-9718ecde050a) (retención) 
    
- [Usar las directivas de cierre y eliminación de sitio](https://support.microsoft.com/es-ES/office/use-policies-for-site-closure-and-deletion-a8280d82-27fd-48c5-9adf-8a5431208ba5) (solo eliminación) 
    
- [Directivas de administración de información](intro-to-info-mgmt-policies.md) (solo eliminación)
     
Si ha usado previamente cualquiera de las retenciones de eDiscovery con el propósito del gobierno de información, debe usar en su lugar una directiva de retención para el cumplimiento proactivo. Use eDiscovery solo para retenciones.
  
### <a name="retention-policies-and-sharepoint-content-type-policies-or-information-management-policies"></a>Directivas de retención y directivas de tipo de contenido de SharePoint o directivas de administración de información

Si ha configurado los sitios de SharePoint para directivas de tipo de contenido o directivas de administración de información para conservar el contenido de una lista o biblioteca, estas directivas se omiten cuando se aplica una directiva de retención. 
  
### <a name="preservation-policies-are-converted-to-retention-policies"></a>Las directivas de conservación se convierten en directivas de retención

Si estaba usando una directiva de conservación para retener datos en buzones, sitios de OneDrive o SharePoint, o en carpetas públicas: esa directiva se ha convertido automáticamente en una directiva de retención que usa solo la acción de retención; la directiva no eliminará el contenido. No es necesario que realice cambios para obtener el mismo resultado que su directiva de conservación configurada.

Puede encontrar estas directivas en la página de **Directivas** en la página del [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com/), o en la página **Retención** en **Control de la información** en el [Centro de seguridad &amp; cumplimiento](https://protection.office.com/). Puede editar una directiva de conservación para cambiar el periodo de retención, pero no puede realizar otros cambios, como agregar o quitar ubicaciones. 


## <a name="related-information"></a>Información relacionada

- [Obtenga información sobre las etiquetas de retención](labels.md)
- [Límites de SharePoint Online](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)
- [Límites y especificaciones para Microsoft Teams](https://docs.microsoft.com/microsoftteams/limits-specifications-teams) 
- [Cumplir con la norma SEC 17a-4](use-exchange-online-to-comply-with-sec-rule-17a-4.md)

## <a name="next-steps"></a>Siguientes pasos

Si está listo para crear directivas de retención, vea [crear y configurar directivas de retención](create-retention-policies.md).

