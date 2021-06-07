---
title: Determinar si la implementación centralizada de complementos funciona para su organización
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b4527d49-4073-4b43-8274-31b7a3166f92
description: Determine si el inquilino y los usuarios cumplen los requisitos, de modo que pueda usar la implementación centralizada para implementar Office complementos.
ms.openlocfilehash: 63775ed6bab2d595ae87085e1607be5818b355e2
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782494"
---
# <a name="determine-if-centralized-deployment-of-add-ins-works-for-your-organization"></a>Determinar si la implementación centralizada de complementos funciona para su organización

La implementación centralizada es la forma recomendada y más enriquecte de características para que la mayoría de los clientes implemente Office complementos para usuarios y grupos dentro de su organización. Si es administrador, use esta guía para determinar si su organización y los usuarios cumplen los requisitos para poder usar la implementación centralizada.

Implementación centralizada proporciona las siguientes ventajas:
  
- Un administrador global puede asignar un complemento directamente a un usuario, a varios usuarios a través de un grupo o a todos los usuarios de la organización.
    
- Cuando se inicia Office aplicación, el complemento se descarga automáticamente. Si el complemento admite comandos de complemento, el complemento aparecerá automáticamente en la cinta de opciones dentro de la Office aplicación.
    
- Los complementos ya no aparecen para los usuarios si el administrador desactiva o elimina el complemento, o si el usuario se quita de Azure Active Directory o de un grupo al que está asignado el complemento.

La implementación centralizada admite tres plataformas de escritorio Windows, Mac y Aplicaciones Office línea. La implementación centralizada también admite iOS y Android (solo Outlook complementos móviles).

Un complemento puede tardar hasta 24 horas en aparecer para todos los usuarios.
  
## <a name="before-you-begin"></a>Antes de empezar

La implementación centralizada de complementos requiere que los usuarios usen SKU de Microsoft 365 Enterprise: E3/E5/F3 o SKU empresariales: Business Basic, Business Standard, Business Premium (y han iniciado sesión en Office con su identificador de organización) y tienen buzones de Exchange Online y Exchange Online activos. El directorio de suscripción debe estar en o federado para Azure Active Directory.
Puede ver requisitos específicos para Office y Exchange a continuación, o usar el Control de compatibilidad de implementación [centralizada](#centralized-deployment-compatibility-checker).

La implementación centralizada no es compatible con lo siguiente:
  
- Complementos que tengan como objetivo Word, Excel o PowerPoint en Office 2013 
- Un servicio de directorio local
- Implementación de complementos en un buzón Exchange local
- Implementación de complemento a SharePoint  
- Teams aplicaciones
- Implementación de complementos de modelo de objetos componentes (COM) o Visual Studio Tools para Office (VSTO).
- Implementaciones de Microsoft 365 que no incluyen Exchange Online como SKU: Aplicaciones Microsoft 365 para empresas y Aplicaciones Microsoft 365 para Enterprise.

### <a name="office-requirements"></a>Office Requisitos

- Para word, Excel y PowerPoint complementos, los usuarios deben usar una de las siguientes opciones:
  - En un dispositivo Windows, versión 1704 o posterior de Microsoft 365 Enterprise SKU: E3/E5/F3 o SKU empresariales: Business Basic, Business Standard, Business Premium.
  - En mac, versión 15.34 o posterior.

- Por Outlook, los usuarios deben usar una de las siguientes opciones: 
  - Versión 1701 o posterior de Microsoft 365 Enterprise SKU: E3/E5/F3 o SKU empresariales: Business Basic, Business Standard, Business Premium.
  - Versión 1808 o posterior de Office Profesional Plus 2019 o Office Standard 2019.
  - Versión 16.0.4494.1000 o posterior de Office Profesional Plus 2016 (MSI) o Office Standard 2016 (MSI)\*
  - Versión 15.0.4937.1000 o posterior de Office Profesional Plus 2013 (MSI) o Office Standard 2013 (MSI)\*
  - Versión 16.0.9318.1000 o posterior de Office 2016 para Mac 
- Versión 2.75.0 o posterior de Outlook móvil para iOS 
- Versión 2.2.145 o posterior de Outlook móvil para Android 
    
    *Las versiones MSI de Outlook muestran complementos instalados por el administrador en la cinta de opciones Outlook, no en la sección "Mis complementos".

### <a name="exchange-online-requirements"></a>Exchange Online requisitos

Microsoft Exchange los manifiestos del complemento en el inquilino de la organización. El administrador que implementa complementos y los usuarios que reciben esos complementos deben estar en una versión de Exchange Online que admita la autenticación de OAuth.
  
Póngase en contacto con el administrador de Exchange de su organización para averiguar qué configuración está en uso. La conectividad de OAuth por usuario puede comprobarse usando el cmdlet de PowerShell [Test-OAuthConnectivity](/powershell/module/exchange/test-oauthconnectivity). 


### <a name="centralized-deployment-compatibility-checker"></a>Comprobación de compatibilidad de implementación centralizada

Con el control de compatibilidad de implementación centralizada, puede comprobar si los usuarios del espacio empresarial están configurados para usar la implementación centralizada para Word, Excel y PowerPoint. El Comprobador de compatibilidad no es necesario para la compatibilidad con Outlook. Descargue el [control de compatibilidad](https://aka.ms/officeaddindeploymentorgcompatibilitychecker).
  
#### <a name="run-the-compatibility-checker"></a>Ejecutar el control de compatibilidad
  
1. Inicie una ventana PowerShell.exe con privilegios elevados.
    
2. Ejecute el siguiente comando:

   ```powershell
   Import-Module O365CompatibilityChecker
   ```
    
3. Ejecute el **comando Invoke-CompatabilityCheck:**

   ```powershell
   Invoke-CompatibilityCheck
   ```
   Este comando le solicita  *_TenantDomain_* (por ejemplo, *TailspinToysIncorporated.onmicrosoft. </span> com*) y  *_las credenciales de TenantAdmin_* (use sus credenciales de administrador global) y, a continuación, solicite el consentimiento.
    
   > [!NOTE]
   > Según el número de usuarios de su espacio empresarial, el comprobador puede tardar minutos u horas en realizar la comprobación. 
  
Cuando la herramienta completa el proceso, genera un archivo de salida en formato delimitado por comas (.csv). El archivo se guarda en **C:\windows\system32** de forma predeterminada. El archivo de salida contiene la información siguiente:
  
- Nombre de usuario
    
- Id. de usuario (dirección de correo electrónico del usuario)
    
- Preparado para la Implementación centralizada: si los elementos restantes son ciertos
    
- Office plan: el plan de Office para el que tienen licencia
    
- Office activado: si Office está activado
    
- Buzón compatible: si están en un buzón habilitado para OAuth

> [!NOTE]
> La autenticación multifactor no se admite al usar el módulo PowerShell de implementación central. El módulo solo funciona con autenticación básica.
  
## <a name="user-and-group-assignments"></a>Asignaciones de usuario y de grupo

La característica Implementación centralizada actualmente admite la mayoría de los grupos admitidos por Azure Active Directory, incluidos Microsoft 365, listas de distribución y grupos de seguridad.
  
> [!NOTE]
> Los grupos de seguridad no habilitados para correo no son compatibles en estos momentos. 
  
La implementación centralizada admite asignaciones a usuarios individuales, grupos y todos los usuarios del espacio empresarial. La implementación centralizada es compatible con usuarios en grupos de nivel superior o grupos sin grupo primario, pero no con usuarios en grupos anidados o grupos que forman parte de otros primarios.
   
Eche un vistazo al siguiente ejemplo, en el que Sandra, Sheila y el grupo del departamento de ventas están asignados a un complemento. Como el departamento de ventas de la Costa Occidental es un grupo anidado, Bert y Fred no están asignados a un complemento.
  
![Diagrama del departamento de ventas](../../media/683094bb-1160-4cce-810d-26ef7264c592.png)

   
### <a name="find-out-if-a-group-contains-nested-groups"></a>Averiguar si un grupo contiene grupos anidados

La forma más sencilla de detectar si un grupo contiene grupos anidados es ver la tarjeta de contacto del grupo en Outlook. Si escribe el nombre del grupo en el campo **Para** de un correo electrónico y, a continuación, selecciona el nombre del grupo cuando se resuelve, se mostrará si contiene usuarios o grupos anidados. En el ejemplo siguiente, la pestaña **Miembros** de la tarjeta de contacto de Outlook del grupo de pruebas no muestra usuarios, solo dos subgrupos. 
  
![Ficha Miembros de Outlook de contacto](../../media/d9db88c4-d752-426c-a480-b11a5b3adcd6.png)
  
Puede realizar la consulta opuesta para comprobar si un grupo es miembro de cualquier otro. En el ejemplo siguiente, puede ver en la pestaña **Miembros** de la tarjeta de contacto de Outlook que el Subgrupo 1 es miembro del grupo de pruebas. 
  
![Ficha Pertenencia de la Outlook de contacto](../../media/a9f9b6ab-9c19-4822-9e3d-414ca068c42f.png)
  
De forma alternativa, puede usar la API de Graph Azure Active Directory para ejecutar consultas para encontrar una lista de grupos dentro de un grupo. Para obtener más información, vea [Operaciones en grupos | Referencia de API de Graph](/previous-versions/azure/ad/graph/api/groups-operations).
  
### <a name="contacting-microsoft-for-support"></a>Ponerse en contacto con Microsoft para obtener soporte técnico

Si usted o sus usuarios tienen problemas para cargar el complemento mientras usan aplicaciones de Office para la web (Word, Excel, etc.), que se implementaron de forma centralizada, es posible que deba ponerse en contacto con el soporte técnico de Microsoft[(](../../business-video/get-help-support.md)obtenga información sobre cómo ). Proporcione la siguiente información sobre su entorno Microsoft 365 en el vale de soporte técnico.
  
|**Plataforma**|**Información de depuración**|
|:-----|:-----|
|Office  <br/> | Registros Charles/Fiddler  <br/>  Id. del espacio empresarial ( [más información](/onedrive/find-your-office-365-tenant-id))      <br/>  CorrelationID. Vea el origen de una de las páginas de office y busque el valor de Id. de correlación y envíelo para admitir:  <br/>`<input name=" **wdCorrelationId**" type="hidden" value=" **{BC17079E-505F-3000-C177-26A8E27EB623}**">`  <br/>  `<input name="user_id" type="hidden" value="1003bffd96933623"></form>`  <br/> |
|Clientes enriquecidos (Windows y Mac)  <br/> | Registros Charles/Fiddler  <br/>  Generar números de la aplicación cliente (preferiblemente como una captura de pantalla de **Archivo/Cuenta**)  <br/> |

## <a name="related-content"></a>Contenido relacionado

[Implementar complementos en el Centro](../manage/manage-deployment-of-add-ins.md) de administración (artículo)\
[Administrar complementos en el Centro de administración](manage-addins-in-the-admin-center.md) (artículo)\
[Preguntas más frecuentes sobre implementación](../manage/centralized-deployment-faq.md) centralizada (artículo)\
[Actualizar su Microsoft 365 usuarios empresariales al último Office cliente](../setup/upgrade-users-to-latest-office-client.md) (artículo)
 