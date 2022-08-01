---
title: Definición de entidad de número de tarjeta de crédito
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
search.appverid: MET150
ms.topic: reference
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContainsSensitiveInformation
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
hideEdit: true
feedback_system: None
recommendations: false
description: Definición de entidad de tipo de información confidencial de número de tarjeta de crédito.
ms.openlocfilehash: 0d75c0af6c67c1d617db9f7f28fbc63c27e4d05a
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "66999467"
---
# <a name="credit-card-number"></a>Número de tarjeta de crédito

## <a name="format"></a>Formato

De 14 a 19 dígitos con formato o sin formato (ddddddddd) y que deben superar la prueba de Luhn.

## <a name="pattern"></a>Patrón

Detecta tarjetas de todas las principales marcas de todo el mundo, incluyendo Visa, MasterCard, Discover Card, JCB, American Express, tarjetas de regalo, tarjetas de comedor, Rupay y China UnionPay.

## <a name="checksum"></a>Suma de comprobación

Sí, la comprobación de Luhn

## <a name="definition"></a>Definición

Una política de DLP tiene una gran confianza en que ha detectado este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_credit_card` encuentra contenido que coincide con el patrón.
- Se cumple una de las condiciones siguientes:
  - Se encuentra una palabra clave de `Keyword_cc_verification`.
  - Se encuentra una palabra clave de `Keyword_cc_name`.
  - La función `Func_expiration_date` busca una fecha en el formato de fecha correcto.
- Se supera la suma de comprobación.

Una directiva DLP tiene poca confianza en que se detecta este tipo de información confidencial si, dentro de una proximidad de 300 caracteres:

- La función `Func_credit_card` encuentra contenido que coincide con el patrón.
- Se supera la suma de comprobación.

```xml
<!-- Credit Card Number -->
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_credit_card" />
        <Any minMatches="1">
          <Match idRef="Keyword_cc_verification" />
          <Match idRef="Keyword_cc_name" />
          <Match idRef="Func_expiration_date" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_credit_card" />
  </Pattern>
</Entity>
```

## <a name="keywords"></a>Palabras clave

### <a name="keyword_cc_verification"></a>Keyword_cc_verification

- card verification
- card identification number
- Cvn
- cid
- cvc2
- cvv2
- pin block
- security code
- security number
- security no
- issue number
- issue no
- cryptogramme
- numéro de sécurité
- numero de securite
- kreditkartenprüfnummer
- kreditkartenprufnummer
- prüfziffer
- prufziffer
- sicherheits Kode
- sicherheitscode
- sicherheitsnummer
- verfalldatum
- codice di verifica
- Bacalao. Sicurezza
- cod sicurezza
- n autorizzazione
- código
- codigo
- Bacalao. seg
- cod seg
- código de segurança
- codigo de seguranca
- codigo de segurança
- código de seguranca
- cód. Segurança
- Bacalao. Seguranca
- Bacalao. Segurança
- cód. Seguranca
- cód segurança
- cod seguranca
- cod segurança
- cód seguranca
- número de verificação
- numero de verificacao
- ablauf
- gültig bis
- gültigkeitsdatum
- gultig bis
- gultigkeitsdatum
- scadenza
- data scad
- fecha de expiracion
- fecha de venc
- vencimiento
- válido hasta
- valido hasta
- vto
- data de expiração
- data de expiracao
- data em que expira
- validade
- valor
- vencimento
- Transacción
- número de transacción
- número de referencia
- セキュリティコード
- セキュリティ コード
- セキュリティナンバー
- セキュリティ ナンバー
- セキュリティ番号

### <a name="keyword_cc_name"></a>Keyword_cc_name

- Amex
- american express
- americanexpress
- americano espresso
- Visa
- Mastercard
- master card
- Mc
- Mastercard
- master cards
- diner's Club
- diners club
- dinersclub
- Descubrir
- discover card
- discovercard
- discover cards
- JCB
- Brandsmart
- japanese card bureau
- carte blanche
- carteblanche
- credit card
- Cc #
- cc#:

- expiration date
- exp date
- expiry date
- fecha de expiración
- date d'exp
- date expiration
- bank card
- Bankcard
- card number
- card num
- cardnumber
- cardnumbers
- card numbers
- Creditcard
- credit cards
- tarjetas de crédito
- Ccn
- card holder
- Titular
- card holders
- Titulares
- check card
- checkcard
- check cards
- tarjetas de verificación
- debit card
- tarjeta de débito
- debit cards
- tarjetas de débito
- atm card
- atmcard
- atm cards
- atmcards
- enroute
- en route
- card type
- Cardmember Acct
- cuenta de cardmember
- Cardno
- Tarjeta corporativa
- Tarjetas corporativas
- Tipo de tarjeta
- número de cuenta de tarjeta
- cuenta de miembro de la tarjeta
- Cardmember Acct.
- card no.
- tarjeta no
- card number
- carte bancaire
- carte de crédit
- carte de credit
- numéro de carte
- numero de carte
- nº de la carte
- nº de carte
- kreditkarte
- Karte
- karteninhaber
- karteninhabers
- kreditkarteninhaber
- kreditkarteninstitut
- kreditkartentyp
- eigentümername
- kartennr
- kartennummer
- kreditkartennummer
- kreditkarten-nummer
- carta di credito
- carta credito
- N. carta
- n carta
- Nr. carta
- nr carta
- numero carta
- numero della carta
- numero di carta
- tarjeta credito
- tarjeta de credito
- tarjeta crédito
- tarjeta de crédito
- tarjeta de atm
- tarjeta atm
- tarjeta debito
- tarjeta de debito
- tarjeta débito
- tarjeta de débito
- nº de tarjeta
- No. de tarjeta
- no de tarjeta
- numero de tarjeta
- número de tarjeta
- tarjeta no
- tarjetahabiente
- cartão de crédito
- cartão de credito
- cartao de crédito
- cartao de credito
- cartão de débito
- cartao de débito
- cartão de debito
- cartao de debito
- débito automático
- debito automatico
- número do cartão
- numero do cartão
- número do cartao
- numero do cartao
- número de cartão
- numero de cartão
- número de cartao
- numero de cartao
- nº do cartão
- nº do cartao
- nº. do cartão
- no do cartão
- no do cartao
- No. do cartão
- No. do cartao
- Rupay
- pago del sindicato
- Unionpay
- diner's
- Comensales
- クレジットカード番号
- クレジットカードナンバー
- クレジットカード＃
- クレジットカード
- クレジット
- クレカ
- カード番号
- カードナンバー
- カード＃
- アメックス
- アメリカンエクスプレス
- アメリカン エクスプレス
- Visaカード
- Visa カード
- マスターカード
- マスター カード
- マスター
- ダイナースクラブ
- ダイナース クラブ
- ダイナース
- 有効期限
- 期限
- キャッシュカード
- キャッシュ カード
- カード名義人
- カードの名義人
- カードの名義
- デビット カード
- デビットカード
- 中国银联
- 银联