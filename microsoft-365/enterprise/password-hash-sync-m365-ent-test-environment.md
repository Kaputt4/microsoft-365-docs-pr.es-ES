---
title: Sincronización de hash de contraseñas para el entorno de prueba de Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/26/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLG
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: ''
description: 'Resumen: configure y muestre la sincronización de hash de contraseñas e inicie sesión en su entorno de prueba de Microsoft 365.'
ms.openlocfilehash: 2d5fbd3ed2a2afb994fc36f5ba3a15a8c55a274e
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819393"
---
# <a name="password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Sincronización de hash de contraseñas para el entorno de prueba de Microsoft 365

*Esta guía del laboratorio de pruebas puede usarse tanto para entornos de prueba de Microsoft 365 Enterprise como de Office 365 Enterprise.*

Muchas organizaciones utilizan la sincronización de hash de Azure AD Connect y contraseña para sincronizar el conjunto de cuentas de su bosque de cuentas en su Active Directory Domain Services (AD DS) local para el conjunto de cuentas en el inquilino de Azure AD de sus suscripciones a Microsoft 365. En este artículo se describe cómo puede añadir la sincronización hash de contraseñas al entorno de pruebas de Microsoft 365, dando como resultado la configuración siguiente:
  
![La empresa simulada con el entorno de prueba con la sincronización de hash de contraseñas](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)
  
Existen dos fases para configurar el entorno de pruebas:
  
1. Crear el entorno de pruebas empresarial simulado de Microsoft 365.
2. Instalar y configurar Azure AD Connect en APP1.
    
> [!TIP]
> Haga clic en [Microsoft 365 Enterprise Test Lab Guide Stack](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) para ver un mapa visual de todos los artículos de la pila de guías de laboratorio de pruebas de Microsoft 365 Enterprise.
  
## <a name="phase-1-create-the-microsoft-365-simulated-enterprise-test-environment"></a>Fase 1: crear el entorno de pruebas empresarial simulado de Microsoft 365.

Siga las instrucciones de la [configuración básica empresarial simulada para Microsoft 365](simulated-ent-base-configuration-microsoft-365-enterprise.md). Esta la configuración resultante.
  
![La configuración básica empresarial simulada](../media/password-hash-sync-m365-ent-test-environment/Phase1.png)
  
Esta configuración se compone de: 
  
- Suscripciones de prueba o de pago de Microsoft 365 E5 u Office 365 E5.
- La intranet de una organización simplificada conectada a Internet, que consta de las máquinas virtuales DC1, APP1 y CLIENTE1 en una red virtual de Azure. DC1 es un controlador de dominio para el dominio de AD DS testlab.\<your public domain name> .

## <a name="phase-2-create-and-register-the-testlab-domain"></a>Fase 2: crear y registrar el dominio de laboratorio de pruebas

En esta fase agregará un dominio DNS público y a su suscripción.

En primer lugar, trabaje con proveedor de registro DNS público para crear un nuevo nombre de dominio DNS público en función de su nombre de dominio actual y agréguelo a su suscripción. Le recomendamos usar el nombre **testlab.**\<your public domain>. Por ejemplo, si el nombre de dominio público es <span>**** contoso</span>. com, agregue el nombre de dominio público **<span>testlab</span>. contoso.com**.
  
Después, agregue el dominio **testlab.**\<your public domain> a su suscripción de prueba o de pago de Office 365 o Microsoft 365 durante el proceso de registro del dominio. Esto consiste en añadir más registros DNS al dominio **testlab.**\<your public domain> . Para obtener más información, vea [Agregar un dominio a Office 365](https://docs.microsoft.com/office365/admin/setup/add-domain). 

Este es el resultado de la configuración.
  
![El registro del nombre de dominio del laboratorio de pruebas](../media/password-hash-sync-m365-ent-test-environment/Phase2.png)
  
Esta configuración se compone de:

- Suscripciones de prueba o de pago de Office 365 E5 o Microsoft 365 E5 con el dominio DNS testlab.\<your public domain name> registrado.
- La intranet de una organización simplificada conectada a Internet, que consta de las máquinas virtuales DC1, APP1 y CLIENTE1 en una subred de una red virtual de Azure.

Observe el estado de testlab.\<your public domain name> ahora:

- Compatible con los registros DNS públicos.
- Registrado en las suscripciones de Microsoft 365.
- El dominio de AD DS de la intranet simulada.
     
## <a name="phase-3-install-azure-ad-connect-on-app1"></a>Fase 3: instalar Azure AD Connect en APP1

En esta fase, instalará y configurará la herramienta Azure AD Connect en APP1 y, después, comprobará que funciona correctamente.
  
Primero, instale y configure Azure AD Connect en APP1.

1. Desde el [Azure Portal](https://portal.azure.com), inicie sesión con su cuenta de administrador global y conéctese a APP1 con la cuenta TESTLAB\\Usuario1.
    
2. Desde el escritorio de APP1, abra un símbolo del sistema de Windows PowerShell con el nivel de administrador y ejecute estos comandos para deshabilitar la seguridad mejorada de Internet Explorer:
    
   ```powershell
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A7-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A8-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Stop-Process -Name Explorer -Force
   ```

3. En la barra de tareas, haga clic en **Internet Explorer** y vaya a [https://aka.ms/aadconnect](https://aka.ms/aadconnect).
    
4. En la página de Microsoft Azure Active Directory Connect, haga clic en **Descargar** y, después, en **Ejecutar**.
    
5. En la página **Bienvenido a Azure AD Connect**, haga clic en **Acepto** y, después, en **Continuar**.
    
6. En la página **Configuración rápida**, haga clic en **Usar configuración rápida**.
    
7. En la página **Conectar a Azure AD**, escriba el nombre de la cuenta de administrador global en **Nombre de usuario**, escriba la contraseña en **Contraseña** y, después, haga clic en **Siguiente**.
    
8. En la página **Conectarse a AD DS**, escriba **TESTLAB\\Usuario1** en **Nombre de usuario**, escriba la contraseña en **Contraseña** y después haga clic en **Siguiente**.
    
9. En la página **Listo para configurar**, haga clic en **Instalar**.
    
10. En la página **Configuración completada** de página, haga clic en **Salir**.
    
11. En Internet Explorer, vaya al Centro de administración de Microsoft 365 ([https://portal.microsoft.com](https://portal.microsoft.com)).
    
12. En el panel de navegación izquierdo, haga clic en **Usuarios > Usuarios activos**.
    
    Observe la cuenta llamada **Usuario1**. Esta cuenta pertenece al dominio de AD DS de TESTLAB y es una prueba de que la sincronización de directorios funcionó correctamente.
    
13. Haga clic en la cuenta **Usuario1** y después, haga clic en **Licencias y aplicaciones**.
    
14. En **Licencias de producto**, seleccione su ubicación (si es necesario), deshabilite la licencia de **Office 365 E5** y habilite la licencia de **Microsoft 365 E5**. 

15. Haga clic en **Guardar** en la parte inferior de la página y después haga clic en **Cerrar**.
    
A continuación, probará la capacidad de iniciar sesión en su suscripción con el nombre de usuario<strong>user1@testlab.</strong>\<your domain name> de la cuenta User1.

1. Desde APP1, cierre la sesión y vuelva a iniciarla, pero esta vez especifique una cuenta diferente.

2. Cuando se le pida el nombre de usuario y la contraseña, especifique <strong>user1@testlab.</strong>\<your domain name> y la contraseña de User1. Debería poder iniciar sesión como User1. 
 
Tenga en cuenta que, aunque User1 tiene permisos de administrador de dominio para el dominio TESTLAB AD DS, no es un administrador global. Por lo tanto, no verá el icono de **administrador** como opción. 

Este es el resultado de la configuración.

![La empresa simulada con el entorno de prueba con la sincronización de hash de contraseñas](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)

Esta configuración se compone de: 
  
- Suscripciones de prueba o de pago de Office 365 E5 o Microsoft 365 E5 con el dominio DNS TESTLAB.\<your domain name> registrado.
- La intranet de una organización simplificada conectada a Internet, que consta de las máquinas virtuales DC1, APP1 y CLIENTE1 en una subred de una red virtual de Azure. Azure AD Connect se ejecuta en APP1 para sincronizar periódicamente el dominio TESTLAB de AD DS con el espacio empresarial de Azure AD de sus suscripciones de Microsoft 365.
- La cuenta User1 en el dominio AD DS de TESTLAB se ha sincronizado con la cuenta empresarial de Azure AD.

## <a name="next-step"></a>Paso siguiente

Explorar características de [identidad](m365-enterprise-test-lab-guides.md#identity) adicionales y funcionalidades en su entorno de prueba.

## <a name="see-also"></a>Vea también

[Guías de laboratorio de pruebas de Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Implementar Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Documentación y recursos de Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)


