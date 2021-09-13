---
title: Sincronización de hash de contraseñas para el entorno de prueba de Microsoft 365
f1.keywords:
- NOCSH
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 05/26/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLG
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: ''
description: 'Resumen: configure y muestre la sincronización de hash de contraseñas e inicie sesión en su entorno de prueba de Microsoft 365.'
ms.openlocfilehash: dbf4b2ca694ee9dc81a5b02ebd0f7cf3820d0f1d
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2021
ms.locfileid: "59213820"
---
# <a name="password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Sincronización de hash de contraseñas para el entorno de prueba de Microsoft 365

*Esta Guía del laboratorio de pruebas se puede usar tanto Microsoft 365 entornos de prueba empresariales como Office 365 Enterprise de prueba.*

Muchas organizaciones utilizan la sincronización de hash de Azure AD Connect y contraseña para sincronizar el conjunto de cuentas de su bosque de cuentas en su Active Directory Domain Services (AD DS) local para el conjunto de cuentas en el inquilino de Azure AD de sus suscripciones a Microsoft 365. 

En este artículo se describe cómo agregar la sincronización de hash de contraseña a su Microsoft 365 de prueba, lo que da como resultado esta configuración:
  
![La empresa simulada con el entorno de prueba de sincronización de hash de contraseña.](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)
  
La configuración de este entorno de prueba implica tres fases:
- [Fase 1: crear el entorno de pruebas empresarial simulado de Microsoft 365.](#phase-1-create-the-microsoft-365-simulated-enterprise-test-environment)
- [Fase 2: crear y registrar el dominio de laboratorio de pruebas](#phase-2-create-and-register-the-testlab-domain)
- [Fase 3: instalar Azure AD Connect en APP1](#phase-3-install-azure-ad-connect-on-app1)
    
> [!TIP]
> Para obtener una asignación visual a todos los artículos de la pila Microsoft 365 guía del laboratorio de pruebas de empresa, vaya a Microsoft 365 enterprise [Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).
  
## <a name="phase-1-create-the-microsoft-365-simulated-enterprise-test-environment"></a>Fase 1: crear el entorno de pruebas empresarial simulado de Microsoft 365.

Siga las instrucciones de [configuración base de empresa simulada para Microsoft 365](simulated-ent-base-configuration-microsoft-365-enterprise.md). La configuración resultante tiene este aspecto:
  
![La configuración base de empresa simulada.](../media/password-hash-sync-m365-ent-test-environment/Phase1.png)
  
Esta configuración se compone de:
  
- Una suscripción de prueba o de pago de Microsoft 365 E5.
- Una intranet de organización simplificada conectada a Internet, formada por las máquinas virtuales DC1, APP1 y CLIENT1 de una red virtual de Azure. DC1 es un controlador de dominio para el testlab.<*nombre de* dominio público> dominio de AD DS.

## <a name="phase-2-create-and-register-the-testlab-domain"></a>Fase 2: crear y registrar el dominio de laboratorio de pruebas

En esta fase, agregue un dominio DNS público y, a continuación, agrégrelo a la suscripción.

En primer lugar, trabaje con el proveedor de registro DNS público para crear un nuevo nombre de dominio DNS público basado en el nombre de dominio actual y, a continuación, agrégrelo a la suscripción. Se recomienda usar el nombre **testlab.<*dominio público* >**. Por ejemplo, si el nombre de dominio público es **<span>contoso</span>.com**, agregue el nombre de dominio público: **<span>testlab</span>.contoso.com**.
  
A continuación, agregue **el testlab.<*dominio* >** público a su Microsoft 365 de prueba o de pago mediante el proceso de registro de dominio. Esto consiste en agregar registros DNS adicionales al **testlab.<*dominio público.* >** Para obtener más información, [vea Agregar un dominio a Microsoft 365](../admin/setup/add-domain.md).

La configuración resultante tiene este aspecto:
  
![El registro del nombre de dominio de testlab.](../media/password-hash-sync-m365-ent-test-environment/Phase2.png)
  
Esta configuración se compone de:

- Una Microsoft 365 E5 de prueba o de pago con el dominio DNS testlab.<*su nombre de* dominio público> registrado.
- Una intranet de organización simplificada conectada a Internet, formada por las máquinas virtuales DC1, APP1 y CLIENT1 en una subred de una red virtual de Azure.

Observe cómo el testlab.<*el nombre de* dominio> es ahora:

- Compatible con los registros DNS públicos.
- Registrado en las suscripciones de Microsoft 365.
- El dominio de AD DS de la intranet simulada.
     
## <a name="phase-3-install-azure-ad-connect-on-app1"></a>Fase 3: instalar Azure AD Connect en APP1

En esta fase, instale y configure la herramienta de Conectar azure AD en APP1 y, a continuación, compruebe que funciona.
  
En primer lugar, instale y configure Azure AD Conectar app1.

1. Desde el [Azure Portal](https://portal.azure.com), inicie sesión con su cuenta de administrador global y conéctese a APP1 con la cuenta TESTLAB\\Usuario1.
    
2. Desde el escritorio de APP1, abra un símbolo del sistema de Windows PowerShell con el nivel de administrador y ejecute estos comandos para deshabilitar la seguridad mejorada de Internet Explorer:
    
   ```powershell
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A7-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A8-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Stop-Process -Name Explorer -Force
   ```

3. En la barra de tareas, **seleccione Internet Explorer** y vaya a [https://aka.ms/aadconnect](https://aka.ms/aadconnect) .
    
4. En la Microsoft Azure Active Directory Conectar, seleccione **Descargar** y, a continuación, **seleccione Ejecutar**.
    
5. En la **página Bienvenido a Azure AD Conectar,** seleccione **Acepto** y, a continuación, **seleccione Continuar**.
    
6. En la **página Configuración** express, seleccione Usar **configuración express**.
    
7. En la **Conectar a Azure AD,** escriba el nombre de la cuenta de administrador global en Nombre de **usuario,** escriba su contraseña en **Contraseña** y, a continuación, **seleccione Siguiente**.
    
8. En la **Conectar a AD DS,** escriba **TESTLAB \\ User1** en **Username,** escriba su contraseña en **Password** y, a continuación, **seleccione Next**.
    
9. En la **página Listo para configurar,** seleccione **Instalar**.
    
10. En la **página Configuración completada,** seleccione **Salir**.
    
11. En Internet Explorer, vaya al Centro de administración de Microsoft 365 ([https://portal.microsoft.com](https://portal.microsoft.com)).
    
12. En el panel de navegación izquierdo, seleccione **Usuarios > usuarios activos.**
    
    Observe la cuenta llamada **Usuario1**. Esta cuenta pertenece al dominio de AD DS de TESTLAB y es una prueba de que la sincronización de directorios funcionó correctamente.
    
13. Selecciona la **cuenta User1** y, a continuación, **selecciona Licencias y aplicaciones.**
    
14. En **Licencias de productos,** seleccione su ubicación (si es necesario), deshabilite la **licencia** Office 365 E5 y, a continuación, **habilite Microsoft 365 E5** licencia. 

15. Seleccione **Guardar** en la parte inferior de la página y, a continuación, **seleccione Cerrar**.
    
A continuación, pruebe la capacidad de iniciar sesión en la suscripción con **el  > user1@testlab.<** nombre de usuario de nombre de dominio de la cuenta User1:

1. Desde APP1, cierre la sesión y vuelva a iniciarla, pero esta vez especifique una cuenta diferente.

2. Cuando se le pida un nombre de usuario y una contraseña, **especifique user1@testlab.<*nombre* >** de dominio y la contraseña user1. Debería poder iniciar sesión como User1.
 
Tenga en cuenta que, aunque User1 tiene permisos de administrador de dominio para el dominio TESTLAB AD DS, no es un administrador global. Por lo tanto, no verá el icono de **administrador** como opción. 

La configuración resultante tiene este aspecto:

![La empresa simulada con el entorno de prueba de sincronización de hash de contraseña.](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)

Esta configuración se compone de: 
  
- Microsoft 365 E5 o Office 365 E5 de prueba o de pago con el dominio DNS TESTLAB.<*el nombre* de dominio> registrado.
- Una intranet de organización simplificada conectada a Internet, formada por las máquinas virtuales DC1, APP1 y CLIENT1 en una subred de una red virtual de Azure. Azure AD Conectar se ejecuta en APP1 para sincronizar periódicamente el dominio de TESTLAB AD DS con el inquilino de Azure AD de la Microsoft 365 suscripción.
- La cuenta User1 en el dominio AD DS de TESTLAB se ha sincronizado con la cuenta empresarial de Azure AD.

## <a name="next-step"></a>Paso siguiente

Explorar características de [identidad](m365-enterprise-test-lab-guides.md#identity) adicionales y funcionalidades en su entorno de prueba.

## <a name="see-also"></a>Vea también

[Guías de entornos de pruebas de Microsoft 365 para empresas](m365-enterprise-test-lab-guides.md)

[Información general de Microsoft 365 para empresas](microsoft-365-overview.md)

[Documentación para Microsoft 365 Enterprise](/microsoft-365-enterprise/)