---
title: Determinar si la implementación centralizada de complementos funciona para su organización
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
description: Determine si el inquilino y los usuarios cumplen los requisitos, de modo que pueda usar la implementación centralizada para implementar complementos de Office.
ms.openlocfilehash: 04c5f9090ca788f00f2d17d3af59e8022195e9be
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519370"
---
# <a name="determine-if-centralized-deployment-of-add-ins-works-for-your-organization"></a>Determinar si la implementación centralizada de complementos funciona para su organización

La implementación centralizada es la forma recomendada y con más características para la mayoría de los clientes de implementar complementos de Office para usuarios y grupos de su organización. Si es administrador, use esta guía para determinar si su organización y los usuarios cumplen los requisitos para poder usar la implementación centralizada.

Implementación centralizada proporciona las siguientes ventajas:
  
- Un administrador global puede asignar un complemento directamente a un usuario, a varios usuarios a través de un grupo o a todos los usuarios de la organización.
    
- Cuando se inicia la aplicación de Office correspondiente, el complemento se descarga automáticamente. Si el complemento admite comandos de complemento, el complemento aparece automáticamente en la cinta de opciones dentro de la aplicación de Office.
    
- Los complementos ya no aparecen para los usuarios si el administrador desactiva o elimina el complemento, o si el usuario se quita de Azure Active Directory o de un grupo al que está asignado el complemento.

La implementación centralizada admite tres plataformas de escritorio, aplicaciones de Windows, Mac y Office en línea. La implementación centralizada también admite iOS y Android (solo complementos de Outlook Mobile).

Un complemento puede tardar hasta 24 horas en mostrarse para el cliente de todos los usuarios.
  
## <a name="requirements"></a>Requirements

La implementación centralizada de complementos requiere que los usuarios usen SKU de Microsoft 365 Enterprise: E3/E5/F3 o SKU empresariales: Business Basic, Business Standard, Business Premium (y que se haya iniciado sesión en Office con su identificador de organización) y que tengan buzones de Exchange Online y Exchange Online activos. El directorio de suscripción debe estar en Azure Active Directory o federado.
Puede ver los requisitos específicos de Office y Exchange a continuación, o usar el Herramienta de comprobación de compatibilidad [de implementación centralizada.](#centralized-deployment-compatibility-checker)

La implementación centralizada no es compatible con lo siguiente:
  
- Complementos que tengan como objetivo Word, Excel o PowerPoint en Office 2013 
- Un servicio de directorio local
- Implementación de complementos en un buzón local de Exchange
- Implementación de complemento a SharePoint  
- Aplicaciones de Teams
- Implementación de complementos del modelo de objetos componentes (COM) o Visual Studio Tools for Office (VSTO).
- Implementaciones de Microsoft 365 que no incluyen Exchange Online, como SKU: Aplicaciones de Microsoft 365 para empresas y Aplicaciones de Microsoft 365 para empresas.

### <a name="office-requirements"></a>Requisitos de Office

- Para los complementos de Word, Excel y PowerPoint, los usuarios deben usar una de las siguientes opciones:
  - En un dispositivo Windows, versión 1704 o posterior de las SKU de Microsoft 365 Enterprise: E3/E5/F3 o SKU de empresa: Business Basic, Business Standard, Empresa Premium.
  - En mac, versión 15.34 o posterior.

- Para Outlook, los usuarios deben usar una de las siguientes opciones: 
  - Versión 1701 o posterior de las SKU de Microsoft 365 Enterprise: E3/E5/F3 o SKU empresariales: Business Basic, Business Standard, Empresa Premium.
  - Versión 1808 o posterior de Office Professional Plus 2019 u Office Standard 2019.
  - Versión 16.0.4494.1000 o posterior de Office Professional Plus 2016 (MSI) u Office Standard 2016 (MSI)\*
  - Versión 15.0.4937.1000 o posterior de Office Professional Plus 2013 (MSI) u Office Standard 2013 (MSI)\*
  - Versión 16.0.9318.1000 o posterior de Office 2016 para Mac 
- Versión 2.75.0 o posterior de Outlook Mobile para iOS 
- Versión 2.2.145 o posterior de Outlook Mobile para Android 
    
    *Las versiones MSI de Outlook muestran complementos instalados por el administrador en la cinta de Outlook adecuada, no en la sección "Mis complementos".

### <a name="exchange-online-requirements"></a>Requisitos de Exchange Online

Microsoft Exchange almacena los manifiestos del complemento en el inquilino de su organización. El administrador que implementa complementos y los usuarios que reciben esos complementos deben estar en una versión de Exchange Online que admita la autenticación de OAuth.
  
Póngase en contacto con el administrador de Exchange de su organización para averiguar qué configuración está en uso. La conectividad de OAuth por usuario puede comprobarse usando el cmdlet de PowerShell [Test-OAuthConnectivity](https://go.microsoft.com/fwlink/p/?linkid=846351). 


### <a name="centralized-deployment-compatibility-checker"></a>Comprobación de compatibilidad de implementación centralizada

Con el Checker de compatibilidad de implementación centralizada, puede comprobar si los usuarios de su espacio empresarial están configurados para usar la implementación centralizada para Word, Excel y PowerPoint. El Comprobador de compatibilidad no es necesario para la compatibilidad con Outlook. Descargue el Comprobador de compatibilidad [aquí](https://aka.ms/officeaddindeploymentorgcompatibilitychecker).
  
#### <a name="run-the-compatibility-checker"></a>Ejecutar el checker de compatibilidad
  
1. Inicie una ventana de PowerShell.exe elevada.
    
2. Ejecute el siguiente comando:

   ```powershell
   Import-Module O365CompatibilityChecker
   ```
    
3. Ejecute el **comando Invoke-CompatabilityCheck:**

   ```powershell
   Invoke-CompatibilityCheck
   ```
   Este comando le solicita  *_TenantDomain_* (por ejemplo, *TailspinToysIncorporated.onmicrosoft. </span> com)* y  *_las credenciales de TenantAdmin_* (use sus credenciales de administrador global) y, a continuación, solicita su consentimiento.
    
   > [!NOTE]
   > Según el número de usuarios de su espacio empresarial, el comprobador puede tardar minutos u horas en realizar la comprobación. 
  
Cuando la herramienta completa el proceso, genera un archivo de salida en formato delimitado por comas (.csv). El archivo se guarda en **C:\windows\system32** de forma predeterminada. El archivo de salida contiene la información siguiente:
  
- Nombre de usuario
    
- Id. de usuario (dirección de correo electrónico del usuario)
    
- Preparado para la Implementación centralizada: si los elementos restantes son ciertos
    
- Plan de Office: el plan de Office para el que tienen licencia
    
- Office activado: si Office está activado
    
- Buzón compatible: si están en un buzón habilitado para OAuth

> [!NOTE]
> No se admite la autenticación multifactor al usar el módulo de PowerShell de implementación central.
  
## <a name="user-and-group-assignments"></a>Asignaciones de usuario y de grupo

La característica implementación centralizada admite actualmente la mayoría de los grupos admitidos por Azure Active Directory, incluidos los grupos de Microsoft 365, las listas de distribución y los grupos de seguridad.
  
> [!NOTE]
> Los grupos de seguridad no habilitados para correo no son compatibles en estos momentos. 
  
La implementación centralizada admite asignaciones a usuarios individuales, grupos y todos los usuarios del espacio empresarial. La implementación centralizada es compatible con usuarios en grupos de nivel superior o grupos sin grupo primario, pero no con usuarios en grupos anidados o grupos que forman parte de otros primarios.
   
Eche un vistazo al siguiente ejemplo, en el que Sandra, Sheila y el grupo del departamento de ventas están asignados a un complemento. Como el departamento de ventas de la Costa Occidental es un grupo anidado, Bert y Fred no están asignados a un complemento.
  
![Diagrama del departamento de ventas](../../media/683094bb-1160-4cce-810d-26ef7264c592.png)

   
### <a name="find-out-if-a-group-contains-nested-groups"></a>Averiguar si un grupo contiene grupos anidados

La forma más sencilla de detectar si un grupo contiene grupos anidados es ver la tarjeta de contacto del grupo en Outlook. Si escribe el nombre  del grupo en el campo Para de un correo electrónico y, a continuación, selecciona el nombre del grupo cuando se resuelve, se mostrará si contiene usuarios o grupos anidados. En el ejemplo siguiente, la pestaña **Miembros** de la tarjeta de contacto de Outlook del grupo de pruebas no muestra usuarios, solo dos subgrupos. 
  
![Pestaña Miembros de la tarjeta de contacto de Outlook](../../media/d9db88c4-d752-426c-a480-b11a5b3adcd6.png)
  
Puede realizar la consulta opuesta para comprobar si un grupo es miembro de cualquier otro. En el ejemplo siguiente, puede ver en la pestaña **Miembros** de la tarjeta de contacto de Outlook que el Subgrupo 1 es miembro del grupo de pruebas. 
  
![Pestaña Pertenencia de la tarjeta de contacto de Outlook](../../media/a9f9b6ab-9c19-4822-9e3d-414ca068c42f.png)
  
De forma alternativa, puede usar la API de Graph Azure Active Directory para ejecutar consultas para encontrar una lista de grupos dentro de un grupo. Para obtener más información, vea [Operaciones en grupos | Referencia de API de Graph](https://go.microsoft.com/fwlink/p/?linkid=846342).
  
### <a name="contacting-microsoft-for-support"></a>Ponerse en contacto con Microsoft para obtener soporte técnico

Si usted o sus usuarios tienen problemas para cargar el complemento mientras usan aplicaciones de Office para la web (Word, Excel, etc.), que se implementaron de forma centralizada, es posible que deba ponerse en contacto con el soporte técnico de Microsoft (obtenga información[sobre](../contact-support-for-business-products.md)cómo). Proporcione la siguiente información sobre su entorno de Microsoft 365 en el vale de soporte técnico.
  
|**Plataforma**|**Información de depuración**|
|:-----|:-----|
|Office  <br/> | Registros Charles/Fiddler  <br/>  Id. del espacio empresarial ( [más información](https://docs.microsoft.com/onedrive/find-your-office-365-tenant-id.aspx))      <br/>  CorrelationID. Vea el origen de una de las páginas de Office y busque el valor del identificador de correlación y envíelo a soporte técnico:  <br/>`<input name=" **wdCorrelationId**" type="hidden" value=" **{BC17079E-505F-3000-C177-26A8E27EB623}**">`  <br/>  `<input name="user_id" type="hidden" value="1003bffd96933623"></form>`  <br/> |
|Clientes enriquecidos (Windows y Mac)  <br/> | Registros Charles/Fiddler  <br/>  Crear números de la aplicación cliente (preferiblemente como captura de pantalla de **Archivo/Cuenta)**  <br/> |
   
