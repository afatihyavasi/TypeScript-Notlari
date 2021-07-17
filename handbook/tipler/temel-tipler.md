---
description: >-
  Bu sayfada TypeScript ile tanımlanabilen temel primitive tipler hakkında
  bilgiler vardır.
---

# Temel Tipler

TypeScript ile değişkenleri tanımlarken yaygın olarak **string**, **number** ve **boolean** tip tanımlamalarını değişkenlere tanımlayabiliriz.

```typescript
let age:number;
age = 22;

let name:string;
name = 'Osman';

let isCompleted:boolean = true;
```

Örneğin **age** değişkenimizin tipini **number** olarak belirledikten sonra **string** bir değer atadığımızda editör **age** değişkeninin altını çizer ve hata verir.

{% hint style="info" %}
Değişken tanımlamalarında, değişkenin tipini belirlemeden değer atandığı taktirde **TypeScript** değişkenin ilk atandığı değerin tipini, değişken tipi olarak belirler.  
  
Örneğin

```typescript
let age = 22;
age = '22'
```

şeklinde bir atama yaptığımızda **TypeScript** hata verir. **age** değişkenine ilk atamada **number** bir değer atadığımız için daha sonra **string** bir değer atadığımız için hata almış oluruz.
{% endhint %}

### Yaygın olmayan diğer tipler

**bigint** ve **symbol** tip tanımlamaları yaygın olmayan diğer primitive  tip tanımlamalarıdır.

```typescript
const oneHundred: bigint = BigInt(100);

const firstName = Symbol("name");
```

  


