---
title: Escritura diferida de contraseña para el entorno de prueba de Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLGS
- Ent_TLGs
ms.assetid: ''
description: 'Resumen: configure la escritura diferida de contraseña para el entorno de prueba de Microsoft 365'
ms.openlocfilehash: 98838bd61fb5664e0b8c8aed4f4b20dee39e0dec
ms.sourcegitcommit: 7ae0389cf06e2f481ee646556720ab3f3e93ea32
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2019
ms.locfileid: "38757687"
---
# <a name="password-writeback-for-your-microsoft-365-test-environment"></a>Escritura diferida de contraseña para el entorno de prueba de Microsoft 365

*Esta guía del laboratorio de pruebas solo se puede usar para entornos de prueba de Microsoft 365 Enterprise.*

La escritura diferida de contraseña permite que los usuarios actualicen sus contraseñas a través de Azure Active Directory (Azure AD), que se replica después en la instancia local de Active Directory Domain Services (AD DS). Con la escritura diferida de contraseñas, los usuarios no necesitan actualizar sus contraseñas a través de la instancia local de AD DS donde se almacenan las cuentas de usuario originales. Esto resulta útil para los usuarios remotos o en itinerancia que no tengan una conexión de acceso remoto a la red local.

En este artículo, se describe cómo configurar el entorno de prueba de Microsoft 365 para la escritura diferida de contraseña.

Hay dos fases de configuración:

1.  Crear el entorno de prueba de la empresa simulada de Microsoft 365 con la sincronización de hash de contraseñas.
2.  Habilitar la escritura diferida de contraseña para el dominio TESTLAB de AD DS.
    
![Guías de laboratorio de pruebas para Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Haga clic [aquí](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) para ver un mapa visual de todos los artículos de la pila Guía de laboratorio de pruebas de Microsoft 365 Enterprise.
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Fase 1: configurar la sincronización de hash de contraseñas para el entorno de prueba de Microsoft 365

Primero, siga las instrucciones de [Sincronización de hash de contraseñas](password-hash-sync-m365-ent-test-environment.md). Esta es la configuración resultante.
  
![La empresa simulada con el entorno de prueba con la sincronización de hash de contraseñas](media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
Esta configuración se compone de: 
  
- Suscripciones de prueba o de pago de Microsoft 365 E5 u Office 365 E5.
- La intranet de una organización simplificada conectada a Internet, que consta de las máquinas virtuales DC1, APP1 y CLIENTE1 en una subred de una red virtual de Azure. 
- Azure AD Connect se ejecuta en APP1 para sincronizar el dominio TESTLAB de AD DS con el espacio empresarial de Azure AD de sus suscripciones de Microsoft 365 u Office 365.

## <a name="phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain"></a>Fase 2: Habilitar la escritura diferida de contraseña para el dominio TESTLAB de AD DS.

En primer lugar, configure la cuenta del Usuario 1 con el rol de administrador global.

1. Desde el [Centro de administración de Microsoft 365](https://portal.microsoft.com), inicie sesión con su cuenta de administrador global.

2. Haga clic en **Usuarios activos**.
 
3. En la página **Usuarios activos**, haga clic en la cuenta **usuario1**.

4. En el panel **usuario1**, haga clic en **Editar** junto a **Roles**.

5. En el panel **Editar roles de usuario** de usuario1, haga clic en **Administrador global**. Haga clic en **Guardar** y, a continuación, haga clic en **Cerrar**.

A continuación, configure la cuenta de Usuario 1 con la configuración de seguridad que le permite cambiar las contraseñas en nombre de otros usuarios en el dominio de TESTLAB AD DS.

1. Desde el [Azure Portal](https://portal.azure.com), inicie sesión con su cuenta de administrador global y, a continuación, conéctese a APP1 con la cuenta TESTLAB\Usuario1.

2.  Desde el escritorio de APP1, haga clic en **Inicio**, escriba **active** y, después, haga clic en **Usuarios y equipos de Active Directory**.

3. Haga clic en **Vista** en la barra de menús. Si **Características avanzadas** no está habilitado, haga clic para habilitarlo.

4. En el panel de árbol, haga clic derecho en su dominio, haga clic en **Propiedades** y, a continuación, haga clic en la pestaña **Seguridad**.

5. Haga clic en **Avanzadas**.

6. En la pestaña **Permisos**, haga clic en **Agregar**.

7. Haga clic en **Seleccionar una entidad de seguridad**, escriba **Usuario1** y, a continuación, haga clic en **Aceptar**.

8. En **Se aplica a**, seleccione **Objetos de usuario descendiente**.

9. En **Permisos**, seleccione lo siguiente:

    - Cambiar contraseña
    - Restablecer contraseña

10. En **Propiedades**, seleccione lo siguiente:
    - Escribir lockoutTime
    - Escribir pwdLastSet

11. Haga clic tres veces en **Aceptar** para guardar los cambios.

12. Cierre **Usuarios y equipos de Active Directory**.

A continuación, configure Azure AD Connect en APP1 para la escritura diferida de contraseña.

1. Si es necesario, conéctese a APP1 con la cuenta TESTLAB\Usuario1.

2. Desde el escritorio de APP1, haga doble clic en **Azure AD Connect**.

3. En la página de **Bienvenida**, haga clic en **Configurar**.

4. En la página **Tareas adicionales**, haga clic en **Personalizar las opciones de sincronización** y, a continuación, haga clic en **Siguiente**.

5. En la página **Conectar a Azure AD**, escriba las credenciales de la cuenta de administrador global y, después, haga clic en **Siguiente**.

6. En las páginas **Conectar directorios** y **Filtrado de dominios y unidades organizativas**, haga clic en **Siguiente**.

7. En la página **Características opcionales**, seleccione **Contraseña con escritura diferida** y haga clic en **Siguiente**. 

8. En la página **Preparado para configurar**, haga clic en **Configurar** y espere a que finalice el proceso.

9. Cuando vea finalizar la configuración, haga clic en **Salir**.

Ya está listo para probar la escritura diferida de contraseñas para los usuarios de equipos que no estén conectados a la red virtual de la intranet simulada.

Esta es la configuración resultante:

![La empresa simulada con el entorno de prueba con la autenticación de paso a través](media/pass-through-auth-m365-ent-test-environment/Phase1.png)

Esta configuración se compone de:

- Suscripciones de prueba o de pago de Microsoft 365 E5 u Office 365 E5 con el dominio DNS TESTLAB.\<su nombre de dominio > registrado.
- La intranet de una organización simplificada conectada a Internet, que consta de las máquinas virtuales DC1, APP1 y CLIENTE1 en una subred de una red virtual de Azure. 
- Azure AD Connect se ejecuta en APP1 para sincronizar la lista de cuentas y grupos desde el espacio empresarial de Azure AD de sus suscripciones de Microsoft Office 365 u Office 365 con el dominio de TESTLAB AD DS. 
- La escritura diferida de contraseña está habilitada para que los usuarios puedan cambiar sus contraseñas a través de Azure AD sin tener que estar conectados a la intranet simplificada.

Vea el paso [Simplificar las actualizaciones de contraseña](identity-add-user-accounts.md#identity-pw-writeback) en la fase Identidad para obtener información y vínculos sobre cómo configurar la escritura diferida de contraseña en un entorno de producción.

## <a name="next-step"></a>Siguiente paso

Explorar características de [identidad](m365-enterprise-test-lab-guides.md#identity) adicionales y funcionalidades en su entorno de prueba.

## <a name="see-also"></a>Vea también

[Guías de laboratorio de pruebas de Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Implementar Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Documentación y recursos de Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)


