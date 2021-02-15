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
ms.openlocfilehash: 3c20d1997be2ff47f0b449cbba3afb1e6edcd59a
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487463"
---
# <a name="password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Sincronización de hash de contraseñas para el entorno de prueba de Microsoft 365

*Esta Guía del entorno de pruebas se puede usar tanto para entornos de prueba de Microsoft 365 para empresas como de Office 365 Enterprise.*

Muchas organizaciones utilizan la sincronización de hash de Azure AD Connect y contraseña para sincronizar el conjunto de cuentas de su bosque de cuentas en su Active Directory Domain Services (AD DS) local para el conjunto de cuentas en el inquilino de Azure AD de sus suscripciones a Microsoft 365. 

En este artículo se describe cómo agregar la sincronización de hash de contraseña a su entorno de prueba de Microsoft 365, lo que da como resultado esta configuración:
  
![La empresa simulada con el entorno de prueba con la sincronización de hash de contraseñas](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)
  
La configuración de este entorno de prueba consta de tres fases:
- [Fase 1: crear el entorno de pruebas empresarial simulado de Microsoft 365.](#phase-1-create-the-microsoft-365-simulated-enterprise-test-environment)
- [Fase 2: crear y registrar el dominio de laboratorio de pruebas](#phase-2-create-and-register-the-testlab-domain)
- [Fase 3: instalar Azure AD Connect en APP1](#phase-3-install-azure-ad-connect-on-app1)
    
> [!TIP]
> Para obtener un mapa visual de todos los artículos de la pila de guía del entorno de pruebas de Microsoft 365 para empresas, vaya a La pila de guía del laboratorio de pruebas de [Microsoft 365 para empresas.](../downloads/Microsoft365EnterpriseTLGStack.pdf)
  
## <a name="phase-1-create-the-microsoft-365-simulated-enterprise-test-environment"></a>Fase 1: crear el entorno de pruebas empresarial simulado de Microsoft 365.

Siga las instrucciones de [la configuración básica empresarial simulada para Microsoft 365.](simulated-ent-base-configuration-microsoft-365-enterprise.md) La configuración resultante tiene este aspecto:
  
![La configuración básica empresarial simulada](../media/password-hash-sync-m365-ent-test-environment/Phase1.png)
  
Esta configuración se compone de:
  
- Una suscripción de prueba o de pago de Microsoft 365 E5.
- Intranet de una organización simplificada conectada a Internet, que consta de las máquinas virtuales DC1, APP1 y CLIENT1 en una red virtual de Azure. DC1 es un controlador de dominio para el testlab.<nombre de dominio *público*> dominio de AD DS.

## <a name="phase-2-create-and-register-the-testlab-domain"></a>Fase 2: crear y registrar el dominio de laboratorio de pruebas

En esta fase, agregue un dominio DNS público y, a continuación, agrégrélo a la suscripción.

En primer lugar, trabaje con su proveedor de registro DNS público para crear un nuevo nombre de dominio DNS público basado en su nombre de dominio actual y, a continuación, agrégrélo a la suscripción. Se recomienda usar el nombre **testlab.<*dominio público.* >** Por ejemplo, si el nombre de dominio público es **<span>contoso</span>.com**, agregue el nombre de dominio público: **<span>testlab</span>.contoso.com**.
  
A continuación, agregue **testlab.< >** dominio público a su suscripción de prueba o de pago de Microsoft 365 mediante el proceso de registro de dominio. Esto consiste en agregar registros DNS adicionales al **testlab.<*dominio* >** público. Para obtener más información, [vea Agregar un dominio a Microsoft 365](../admin/setup/add-domain.md).

La configuración resultante tiene este aspecto:
  
![El registro del nombre de dominio del laboratorio de pruebas](../media/password-hash-sync-m365-ent-test-environment/Phase2.png)
  
Esta configuración se compone de:

- Una suscripción de prueba o de pago de Microsoft 365 E5 con el dominio DNS testlab.<*nombre* de dominio público> registrado.
- Una intranet de organización simplificada conectada a Internet, que consta de las máquinas virtuales DC1, APP1 y CLIENT1 en una subred de una red virtual de Azure.

Observe cómo el archivo testlab.<el nombre de *dominio>* es ahora:

- Compatible con los registros DNS públicos.
- Registrado en las suscripciones de Microsoft 365.
- El dominio de AD DS de la intranet simulada.
     
## <a name="phase-3-install-azure-ad-connect-on-app1"></a>Fase 3: instalar Azure AD Connect en APP1

En esta fase, instale y configure la herramienta Azure AD Connect en APP1 y, a continuación, compruebe que funciona.
  
En primer lugar, instale y configure Azure AD Connect en APP1.

1. Desde el [Azure Portal](https://portal.azure.com), inicie sesión con su cuenta de administrador global y conéctese a APP1 con la cuenta TESTLAB\\Usuario1.
    
2. Desde el escritorio de APP1, abra un símbolo del sistema de Windows PowerShell con el nivel de administrador y ejecute estos comandos para deshabilitar la seguridad mejorada de Internet Explorer:
    
   ```powershell
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A7-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A8-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Stop-Process -Name Explorer -Force
   ```

3. En la barra de tareas, **seleccione Internet Explorer** y vaya a [https://aka.ms/aadconnect](https://aka.ms/aadconnect) .
    
4. En la página Microsoft Azure Active Directory Connect, seleccione **Descargar** y, a continuación, **seleccione Ejecutar**.
    
5. En la **página Principal de Azure AD Connect,** seleccione **Acepto** y, a continuación, **seleccione Continuar.**
    
6. En la **página Configuración express,** seleccione **Usar configuración expresa.**
    
7. En la **página Conectarse a Azure AD,** escriba el nombre de la cuenta de administrador global en Nombre de **usuario,** escriba su contraseña en Contraseña y, a continuación, **seleccione Siguiente**.
    
8. En la **página Conectarse a AD DS,** escriba **TESTLAB \\ User1** en Nombre de **usuario,** escriba su contraseña en **Contraseña** y, a continuación, **seleccione Siguiente.**
    
9. En la **página Listo para configurar,** seleccione **Instalar**.
    
10. En la **página Configuración completada,** seleccione **Salir**.
    
11. En Internet Explorer, vaya al Centro de administración de Microsoft 365 ([https://portal.microsoft.com](https://portal.microsoft.com)).
    
12. En el panel de navegación izquierdo, seleccione **Usuarios > Usuarios activos.**
    
    Observe la cuenta llamada **Usuario1**. Esta cuenta pertenece al dominio de AD DS de TESTLAB y es una prueba de que la sincronización de directorios funcionó correctamente.
    
13. Seleccione la **cuenta Usuario1** y, a continuación, **seleccione Licencias y aplicaciones.**
    
14. En **Licencias de productos,** seleccione su ubicación (si es necesario), deshabilite la licencia de **Office 365 E5** y, a continuación, habilite la licencia de **Microsoft 365 E5.** 

15. Seleccione **Guardar** en la parte inferior de la página y, a continuación, **seleccione Cerrar**.
    
A continuación, pruebe la capacidad de iniciar sesión en su suscripción con **user1@testlab.< >** nombre de dominio de la cuenta User1:

1. Desde APP1, cierre la sesión y vuelva a iniciarla, pero esta vez especifique una cuenta diferente.

2. Cuando se le solicite un nombre de usuario y una contraseña, **especifique user1@testlab.<*nombre* >** de dominio y la contraseña de Usuario1. Debería poder iniciar sesión como User1.
 
Tenga en cuenta que, aunque User1 tiene permisos de administrador de dominio para el dominio TESTLAB AD DS, no es un administrador global. Por lo tanto, no verá el icono de **administrador** como opción. 

La configuración resultante tiene este aspecto:

![La empresa simulada con el entorno de prueba con la sincronización de hash de contraseñas](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)

Esta configuración se compone de: 
  
- Suscripciones de prueba o de pago de Microsoft 365 E5 u Office 365 E5 con el dominio DNS TESTLAB.<*nombre* de dominio> registrado.
- Una intranet de organización simplificada conectada a Internet, que consta de las máquinas virtuales DC1, APP1 y CLIENT1 en una subred de una red virtual de Azure. Azure AD Connect se ejecuta en APP1 para sincronizar periódicamente el dominio DE AD DS TESTLAB con el inquilino de Azure AD de su suscripción a Microsoft 365.
- La cuenta User1 en el dominio AD DS de TESTLAB se ha sincronizado con la cuenta empresarial de Azure AD.

## <a name="next-step"></a>Paso siguiente

Explorar características de [identidad](m365-enterprise-test-lab-guides.md#identity) adicionales y funcionalidades en su entorno de prueba.

## <a name="see-also"></a>Vea también

[Guías de entornos de pruebas de Microsoft 365 para empresas](m365-enterprise-test-lab-guides.md)

[Información general de Microsoft 365 Enterprise](microsoft-365-overview.md)

[Documentación para Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
