---
title: Recomendaciones de directiva de contraseñas
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: high
ms.collection:
- ContentEngagementFY23
- scotvorg
- highpri
- Adm_O365
- Adm_NonTOC
ms.custom:
- VSBFY23
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9fa2539a-2211-41fd-85a0-bc37b9619ca4
description: Haga que su organización sea más segura contra ataques a contraseñas y prohíba las contraseñas comunes y habilite la autenticación multifactor basada en riesgos.
ms.openlocfilehash: 3971fc981046dc3e3e3b2741705053c5e3d52430
ms.sourcegitcommit: 50da6f1f6ef2274c17ed9729e7ad84395b0a9be2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/08/2022
ms.locfileid: "68503168"
---
# <a name="password-policy-recommendations-for-microsoft-365-passwords"></a>Recomendaciones de directiva de contraseñas para contraseñas de Microsoft 365

Como administrador de una organización, usted es el responsable de establecer la directiva de contraseñas para los usuarios de su organización. El establecimiento de la directiva de contraseñas puede resultar complicado y confuso, y en este artículo se proporcionan recomendaciones para que la organización sea más segura frente a ataques de contraseñas.

Las cuentas basadas solo en la nube de Microsoft tienen una directiva de contraseña predefinida que no se puede cambiar. Los únicos elementos que puede cambiar son el número de días hasta que expire una contraseña y si las contraseñas expiran o no.
  
Para determinar con qué frecuencia expiran las contraseñas de Microsoft 365 en la organización, vea [Establecer la directiva de expiración de contraseñas para Microsoft 365](../manage/set-password-expiration-policy.md).

Para obtener más información acerca de las contraseñas de Microsoft 365, vea:

[Restablecer contraseñas](../add-users/reset-passwords.md) (artículo)

[Establecer la contraseña de un usuario individual para que nunca expire](../add-users/set-password-to-never-expire.md) (artículo)

[Permitir que los usuarios puedan restablecer sus propias contraseñas](../add-users/let-users-reset-passwords.md) (artículo)

[Volver a enviar la contraseña de un usuario: ayuda para administradores](../add-users/resend-user-password.md) (artículo)

[Hora de repensar los cambios obligatorios de contraseña](https://go.microsoft.com/fwlink/p/?linkid=861018).
  
## <a name="understanding-password-recommendations"></a>Comprender las recomendaciones de contraseña

Los procedimientos recomendados para las contraseñas se dividen en algunas amplias categorías:
  
- **Resisten los ataques comunes** esto implica la elección del lugar donde los usuarios introducen las contraseñas (dispositivos conocidos y de confianza con una detección de malware, sitios validados) y la elección de la contraseña que debe elegir (longitud y unicidad).

- **Refrenan ataques exitosos** el contener ataques de hackers satisfactoriamente consiste en limitar la exposición a un servicio específico, o bien evitar que se produzcan daños, en caso de que se robe la contraseña de un usuario. Por ejemplo, si se asegura de que una infracción de las credenciales de la red social no haga que su cuenta bancaria sea vulnerable, o no permita que una cuenta guardada mal protegida acepte vínculos de restablecimiento de una cuenta importante.

- **Entender la naturaleza humana** muchos de los procedimientos válidos de contraseñas no se encuentran en el comportamiento humano natural. Entender la naturaleza humana es fundamental, ya que la investigación muestra que casi todas las reglas que se imponen a los usuarios tendrán como resultado debilitar la calidad de la contraseña. Los requisitos de longitud, los requisitos de caracteres especiales y los requisitos de cambio de contraseña todos provocan la normalización de las contraseñas, lo que hace que resulte más fácil averiguar o descifrar contraseñas.

## <a name="password-guidelines-for-administrators"></a>Instrucciones de contraseña para administradores

El principal objetivo de un sistema de contraseña más seguro es la diversidad de las contraseñas. Desea que la Directiva de contraseñas contenga una gran cantidad de contraseñas distintas y difíciles de adivinar. Estas son algunas recomendaciones para mantener su organización lo más segura posible.

- Mantener el requisito de longitud mínima de 14 caracteres

- No solicite requisitos de composición de caracteres. Por ejemplo, \*&amp;(^%$

- No requiera una configuración de contraseña periódica obligatoria para cuentas de usuario.

- Prohíba las contraseñas comunes para evitar el uso de las contraseñas más vulnerables en el sistema. 

- Instruya a los usuarios para que no usen las contraseñas de la organización para propósitos no relacionados con el trabajo

- Exija el registro para la [autenticación multifactor](../security-and-compliance/set-up-multi-factor-authentication.md)

- Permitir desafíos de autenticación multifactor basada en riesgos

### <a name="password-guidance-for-your-users"></a>Guía de contraseñas para los usuarios

Here's some password guidance for users in your organization. Make sure to let your users know about these recommendations and enforce the recommended password policies at the organizational level.
  
- No use una contraseña igual o similar a una que use en otros sitios web

- No use una sola palabra, por ejemplo, **contraseña** o una frase habitual como **Iloveyou**

- Haga que las contraseñas sean difíciles de adivinar, incluso las personas que sepan mucho sobre usted, como el nombre y el cumpleaños de sus amigos y familiares, sus bandas favoritas y las frases que quiera usar.

## <a name="some-common-approaches-and-their-negative-impacts"></a>Algunos métodos comunes y sus repercusiones negativas

Éstas son algunas de las prácticas de administración de contraseñas más usadas, pero la búsqueda nos avisa sobre las consecuencias negativas que tienen.
  
### <a name="password-expiration-requirements-for-users"></a>Requisitos de expiración de contraseña para usuarios

Los requisitos de expiración de contraseñas no ayudan, ya que estos requisitos hacen que los usuarios seleccionen contraseñas predecibles, compuestas de palabras secuenciales y números estrechamente relacionados entre sí. En estos casos, la contraseña siguiente puede predecirse en función de la contraseña anterior. Los requisitos de expiración de contraseñas no ofrecen ventajas de contención, ya que los ciberdelincuentes casi siempre usan las credenciales en cuanto las obtienen. 
  
### <a name="minimum-password-length-requirements"></a>Requisitos mínimos de longitud de contraseña

<!--Password length requirements (greater than about 10 characters) can result in user behavior that is predictable and undesirable. For example, users who are required to have a 16-character password may choose repeating patterns like **fourfourfourfour** or **passwordpassword** that meet the character length requirement but aren't hard to guess. Additionally, length requirements increase the chances that users will adopt other insecure practices, such as writing down their passwords, reusing them, or storing them unencrypted in their documents.-->

Para animar a los usuarios a pensar en una contraseña única, se recomienda mantener un requisito de longitud mínima razonable de 14 caracteres.
  
### <a name="requiring-the-use-of-multiple-character-sets"></a>Requerir el uso de varios juegos de caracteres

Los requisitos de complejidad de las contraseñas reducen el espacio clave y provocan que los usuarios actúen de formas predecibles, que hacen más daño que bien. La mayoría de los sistemas aplican algunos niveles de complejidad de contraseña. Por ejemplo, las contraseñas necesitan caracteres de las tres categorías siguientes:
  
- Caracteres en mayúsculas 

- Caracteres en minúsculas

- Caracteres no alfanuméricos

La mayoría de los usuarios usa patrones similares, por ejemplo, una letra mayúscula en la primera posición, un símbolo en la última y un número las últimas 2. Los ciberdelincuentes lo saben, por lo que ejecutan sus ataques de diccionario usando las sustituciones más comunes: "$" para "s", "@" para "a", "1" para "l". Obligar a sus usuarios a elegir una combinación de letras en mayúsculas, minúsculas, dígitos y caracteres especiales tiene un efecto negativo. Algunos requisitos de complejidad incluso evitan que los usuarios usen contraseñas seguras y fáciles de recordar, y obligan a que se encuentren con contraseñas menos seguras y menos fáciles de recordar.
  
## <a name="successful-patterns"></a>Patrones correctos

En cambio, estas son algunas recomendaciones para favorecer la diversidad de contraseñas.
  
### <a name="ban-common-passwords"></a>Prohibir contraseñas comunes

The most important password requirement you should put on your users when creating passwords is to ban the use of common passwords to reduce your organization's susceptibility to brute force password attacks. Common user passwords include: **abcdefg**, **password**, **monkey**.
  
### <a name="educate-users-to-not-reuse-organization-passwords-anywhere-else"></a>Instruya a los usuarios para que no usen las contraseñas de la organización en otro sitio

Uno de los mensajes más importantes que debe darle a los usuarios de su organización es el de no usar la contraseña de la organización en ningún otro sitio. El uso de las contraseñas de la organización en sitios web externos aumenta considerablemente la probabilidad de que los ciberdelincuentes obtengan esas contraseñas.
  
### <a name="enforce-multi-factor-authentication-registration"></a>Exigir registro de Multi-Factor Authentication

Asegúrese de que los usuarios actualizan la información de contacto y seguridad, como una dirección de correo electrónico alternativa, un número de teléfono o un dispositivo registrado para las notificaciones de inserción, de modo que pueden responder a los desafíos de seguridad y recibir notificaciones de eventos de seguridad. La información actualizada de contacto y seguridad ayuda a los usuarios a verificar su identidad si alguna vez olvidan su contraseña o si alguien más intenta hacerse cargo de su cuenta. También proporciona un canal de notificación fuera de banda en caso de eventos de seguridad como intentos de inicio de sesión o cambio de contraseñas. 
  
Para obtener más información, consulte [configurar la autenticación multifactor](../security-and-compliance/set-up-multi-factor-authentication.md).
  
### <a name="enable-risk-based-multi-factor-authentication"></a>Habilitar la autenticación multifactor basada en riesgos

La autenticación multifactor basada en riesgos garantiza que, cuando nuestro sistema detecta actividad sospechosa, puede poner a prueba al usuario para asegurarse de que es el propietario legítimo de la cuenta. 
  
## <a name="next-steps"></a>Siguientes pasos

¿Quiere obtener más información acerca de la administración de contraseñas? Estas son algunas lecturas recomendadas:

- [Olvide las contraseñas, elija una opción sin contraseñas](https://www.microsoft.com/security/business/identity-access-management/passwordless-authentication)

- [Directrices de contraseñas de Microsoft](https://www.microsoft.com/research/wp-content/uploads/2016/06/Microsoft_Password_Guidance-1.pdf)

- [¿Las contraseñas de web seguras realizan alguna acción?](https://go.microsoft.com/fwlink/p/?linkid=861008)

- [Carteras de contraseñas y el usuario de esfuerzo finito](https://go.microsoft.com/fwlink/p/?linkid=861014)

- [Prevenir contraseñas vulnerables leyendo las mentes de los usuarios](https://go.microsoft.com/fwlink/p/?linkid=861015)

- [Elegir contraseñas seguras](https://go.microsoft.com/fwlink/p/?linkid=861016)

- [Tiempo para reconsiderar los cambios en la contraseña obligatoria](https://go.microsoft.com/fwlink/p/?linkid=861018)

- [Las peores contraseñas de 2015](https://go.microsoft.com/fwlink/p/?linkid=861020)

## <a name="related-content"></a>Contenido relacionado

[Restablecer contraseñas](../add-users/reset-passwords.md) (artículo)\
[Establecer la contraseña de un usuario individual para que nunca expire](../add-users/set-password-to-never-expire.md) (artículo)\
[Permitir que los usuarios puedan restablecer sus propias contraseñas](../add-users/let-users-reset-passwords.md) (artículo)\
[Volver a enviar la contraseña de un usuario: ayuda para administradores](../add-users/resend-user-password.md) (artículo)
