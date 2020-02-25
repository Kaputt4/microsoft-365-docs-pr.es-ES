---
title: Determinar si la implementación centralizada de complementos funciona para su organización
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b4527d49-4073-4b43-8274-31b7a3166f92
description: Determine si el inquilino de Office 365 y los usuarios cumplen los requisitos, de modo que pueda usar la implementación centralizada para implementar complementos de Office.
ms.openlocfilehash: 4351658f2637b86c9b3233f55916d8e0ac0f8cfb
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2020
ms.locfileid: "42255049"
---
# <a name="determine-if-centralized-deployment-of-add-ins-works-for-your-organization"></a>Determinar si la implementación centralizada de complementos funciona para su organización

Implementación centralizada es la forma recomendada y con más funciones para que los clientes implementen complementos de Office para los usuarios y grupos de su organización de Office 365. Si es administrador, use esta guía para determinar si el inquilino y los usuarios cumplen los requisitos para que pueda usar la implementación centralizada.
La implementación centralizada es compatible con Windows, Mac, iOS, Android y aplicaciones de Office en línea.
Un complemento puede tardar hasta 12 horas en mostrarse para el cliente para todos los usuarios.
  
## <a name="requirements"></a>Requisitos

La implementación centralizada de complementos requiere que los usuarios usen Office 365 ProPlus (y que hayan iniciado sesión en Office con su identificador de organización), y que tengan buzones de correo de Exchange Online y activos de Exchange Online. El directorio de la suscripción debe estar en el o en un federado de Azure Active Directory.
Puede ver los requisitos específicos para Office y Exchange, o usar el [Comprobador de compatibilidad de implementación centralizada de office 365](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins?view=o365-worldwide#office-365-centralized-deployment-compatibility-checker).

La implementación centralizada no es compatible con lo siguiente:
  
- Complementos que tengan como objetivo Word, Excel o PowerPoint en Office 2013
    
- Un servicio de directorio local
    
- Implementación de complemento a SharePoint  

- Aplicaciones de Teams
   
- Implementación complementos de modelo de objetos componentes (COM) o de Visual Studio Tools para Office (VSTO)
    
- Implementaciones de Office 365 que no incluyen Exchange, como Office 365 Empresa

### <a name="office-requirements"></a>Requisitos de Office

- Para los complementos de Word, Excel y PowerPoint, los usuarios deben usar una de las siguientes opciones:
  - En un dispositivo Windows, versión 1704 o posterior de Office 365 ProPlus.
  - En un equipo Mac, versión 15,34 o posterior.
      - En iOS (solo iPad), versión 2.9.18010804 o posterior.
- Para Outlook, los usuarios deben usar una de las siguientes opciones: 
  - Versión 1701 o posterior de Office 365 ProPlus.
  - La versión 1808 o posterior de Office Professional Plus 2019 u Office Standard 2019.
  - Versión 16.0.4494.1000 o posterior de Office Professional Plus 2016 (MSI) u Office Standard 2016 (MSI)\*
  - Versión 15.0.4937.1000 o posterior de Office Professional Plus 2013 (MSI) u Office Standard 2013 (MSI)\*
  - Versión 16.0.9318.1000 o posterior de Office 2016 para Mac 
- Versión 2.75.0 o posterior de Outlook Mobile para iOS 
- Versión 2.2.145 o posterior de Outlook Mobile para Android 
    
    * Las versiones MSI de Outlook muestran complementos instalados por el administrador en la cinta de Outlook correspondiente, no en la sección "mis complementos".
    

#### <a name="find-out-if-office-365-proplus-is-installed"></a>Averiguar si Office 365 ProPlus está instalado

Para usar Office 365 ProPlus, un usuario debe tener una cuenta de Office 365 y debe tener una licencia asignada. Para obtener más información, vea [Información general sobre Office 365 ProPlus](https://go.microsoft.com/fwlink/p/?linkid=846328).

La forma más sencilla de detectar si un usuario tiene Office 365 ProPlus instalado y lo ha usado recientemente es usar el informe de activaciones de Microsoft Office, que está disponible en el centro de administración de Microsoft 365. El informe proporciona una lista de todos los usuarios que han activado Office 365 ProPlus en los últimos 7 días, 30 días, 90 días o 180 días. Con fines de implementación centralizada, las activaciones de escritorio para Windows o Mac son las columnas importantes del informe. Puede exportar el informe a Excel. Para más información acerca del informe, vea [Informes de Office 365 en el Centro de administración: activaciones de Microsoft Office](../activity-reports/microsoft-office-activations.md).
  
Si no desea usar el informe de activaciones, puede pedir a un usuario que abra una aplicación de Office, como Word en su equipo y, a continuación, elija **cuenta**de **archivo** \> . En **Información del producto**, debería ver **Producto de suscripción** y **Microsoft Office 365 ProPlus**, como se muestra en la siguiente imagen.

![Información de producto en una aplicación de Office](../media/4bff2bb8-0690-4d22-ac1f-b8881807fa39.png)
  
Para obtener ayuda con Office 365 ProPlus, vea [Consejos de solución de problemas para Office 365 ProPlus](https://go.microsoft.com/fwlink/p/?linkid=846339).


### <a name="exchange-requirements"></a>Requisitos de Exchange

Microsoft Exchange almacena los manifiestos de complemento dentro del inquilino de su organización. El administrador que implementa los complementos y los usuarios que los reciben deben estar en una versión Exchange Server compatible con autenticación OAuth. De forma predeterminada, las implementaciones multiinquilino y VNext dedicadas de Exchange son compatibles con OAuth. Las implementaciones locales heredadas dedicadas e híbridas de Exchange pueden configurarse para ser compatibles con OAuth. Sin embargo, no es su configuración predeterminada.
  
Póngase en contacto con el administrador de Exchange de su organización para averiguar qué configuración está en uso. La conectividad de OAuth por usuario puede comprobarse usando el cmdlet de PowerShell [Test-OAuthConnectivity](https://go.microsoft.com/fwlink/p/?linkid=846351). 


### <a name="office-365-centralized-deployment-compatibility-checker"></a>Comprobador de compatibilidad de Implementación centralizada de Office 365

Con el Comprobador de compatibilidad de Implementación centralizada de Office 365, puede comprobar si los usuarios de su espacio empresarial están configurados para usar la Implementación centralizada para Word, Excel y PowerPoint. El Comprobador de compatibilidad no es necesario para la compatibilidad con Outlook. Descargue el Comprobador de compatibilidad [aquí](https://aka.ms/officeaddindeploymentorgcompatibilitychecker).
  
#### <a name="run-the-compatibility-checker"></a>Ejecutar el comprobador de compatibilidad
  
1. Inicie una ventana de PowerShell. exe con privilegios elevados.
    
2. Ejecute el siguiente comando:

```powershell
Import-Module O365CompatibilityChecker
```
    
3. Ejecute el comando **Invoke-CompatabilityCheck** :

```powershell
Invoke-CompatibilityCheck
```
   le solicita *_TenantDomain_* (por ejemplo, *TailspinToysIncorporated. en Microsoft</span> . com*) y *_TenantAdmin_* (use las credenciales de administrador global) y, a continuación, solicite el consentimiento.
    
> [!NOTE]
> Según el número de usuarios de su espacio empresarial, el comprobador puede tardar minutos u horas en realizar la comprobación. 
  
Cuando la herramienta completa el proceso, genera un archivo de salida en formato delimitado por comas (.csv). El archivo se guarda en **C:\windows\system32** de forma predeterminada. El archivo de salida contiene la información siguiente:
  
- Nombre de usuario
    
- Id. de usuario (dirección de correo electrónico del usuario)
    
- Preparado para la Implementación centralizada: si los elementos restantes son ciertos
    
- Plan de Office: el plan de Office para el que se tiene licencia
    
- Office activado: si Office está activado
    
- Buzón compatible: si están en un buzón habilitado para OAuth


  
## <a name="user-and-group-assignments"></a>Asignaciones de usuario y de grupo

La característica de implementación centralizada es compatible actualmente con la mayoría de los grupos compatibles con Azure Active Directory, incluidos grupos de Office 365, listas de distribución y grupos de seguridad.
  
> [!NOTE]
> Los grupos de seguridad no habilitados para correo no son compatibles en estos momentos. 
  
La implementación centralizada admite asignaciones a usuarios individuales, grupos y a todos los miembros del espacio empresarial. La implementación centralizada es compatible con usuarios en grupos de nivel superior o grupos sin grupo primario, pero no con usuarios en grupos anidados o grupos que forman parte de otros primarios.
   
Eche un vistazo al siguiente ejemplo, en el que Sandra, Sheila y el grupo del departamento de ventas están asignados a un complemento. Como el departamento de ventas de la Costa Occidental es un grupo anidado, Bert y Fred no están asignados a un complemento.
  
![Diagrama del Departamento de ventas](../media/683094bb-1160-4cce-810d-26ef7264c592.png)

   
### <a name="find-out-if-a-group-contains-nested-groups"></a>Averiguar si un grupo contiene grupos anidados

La forma más sencilla de detectar si un grupo contiene grupos anidados es ver la tarjeta de contacto del grupo en Outlook. Si escribe el nombre de grupo en el campo **para** de un correo electrónico y, a continuación, selecciona el nombre del grupo cuando se resuelve, mostrará si contiene usuarios o grupos anidados. En el ejemplo siguiente, la pestaña **Miembros** de la tarjeta de contacto de Outlook del grupo de pruebas no muestra usuarios, solo dos subgrupos. 
  
![Pestaña miembros de la tarjeta de contacto de Outlook](../media/d9db88c4-d752-426c-a480-b11a5b3adcd6.png)
  
Puede realizar la consulta opuesta para comprobar si un grupo es miembro de cualquier otro. En el ejemplo siguiente, puede ver en la pestaña **Miembros** de la tarjeta de contacto de Outlook que el Subgrupo 1 es miembro del grupo de pruebas. 
  
![Ficha pertenencia de la tarjeta de contacto de Outlook](../media/a9f9b6ab-9c19-4822-9e3d-414ca068c42f.png)
  
De forma alternativa, puede usar la API de Graph Azure Active Directory para ejecutar consultas para encontrar una lista de grupos dentro de un grupo. Para obtener más información, vea [Operaciones en grupos | Referencia de API de Graph](https://go.microsoft.com/fwlink/p/?linkid=846342).
  
### <a name="contacting-microsoft-for-support"></a>Ponerse en contacto con Microsoft para obtener soporte técnico

Si usted o sus usuarios experimentan problemas al cargar el complemento mientras usan aplicaciones de Office para la web (Word, Excel, etc.), que se implementaron de forma centralizada, es posible que deba ponerse en contacto con el soporte técnico de Microsoft ([obtenga información](../contact-support-for-business-products.md)). Proporcione la siguiente información sobre el entorno de Office 365 en el vale de soporte.
  
|**Plataforma**|**Información de depuración**|
|:-----|:-----|
|Office  <br/> | Registros Charles/Fiddler  <br/>  Id. del espacio empresarial ( [más información](https://support.office.com/article/6891b561-a52d-4ade-9f39-b492285e2c9b.aspx))      <br/>  CorrelationID. Vea el origen de una de las páginas de Office y busque el valor del identificador de correlación y envíelo a soporte técnico:  <br/>`<input name=" **wdCorrelationId**" type="hidden" value=" **{BC17079E-505F-3000-C177-26A8E27EB623}**">`  <br/>  `<input name="user_id" type="hidden" value="1003bffd96933623"></form>`  <br/> |
|Clientes enriquecidos (Windows y Mac)  <br/> | Registros Charles/Fiddler  <br/>  Números de compilación de la aplicación cliente (preferiblemente como una captura de pantalla de **archivo/cuenta**)  <br/> |
   

