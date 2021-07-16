# TypeScript nedir, ne işe yarar ?

**TypeScript**, JavaScript üzerine inşa edilmiş bir programlama dilidir. JavaScript superset idir. **TypeScript** in temel amacı **static type checking** yaparak geliştirme aşamasında tip kontrolünü sağlamaktır.

Static Type sistemler, programlarımızı çalıştırdığımızda değerlerimizin ne olacağını ve davranışlarını tanımlar. TypeScript bu bilgiyi kullanır ve bize ne zaman hata alacağımızı söyler.

```javascript
const message = "hello!";

message();

/* This expression is not callable.
Type 'String' has no call signatures. */
```

Yukarıda ki kod bloğunu çalıştırdığımızda hata mesajı karşımıza çıkacaktır. TypeScript ise kodu çalıştırmadan önce bize bir hata mesajı verecektir.

TypeScript aynı zamanda çalışma öncesi hataları yakalamamızı da sağlar. Örneğin aşağıdaki kod bloğunu çalıştırdığımızda console a **undefined** değerini yazar.

```javascript
const user = {
  name: "Daniel",
  age: 26,
};

console.log(user.location);
```

TypeScript kullandığımız takdirde kullandığımız IDE de karşımıza aşağıdaki hata mesajı çıkacaktır.

{% hint style="danger" %}
Property 'location' does not exist on type '{ name: string; age: number; }'.
{% endhint %}

TypeScript aşağıdaki gibi basit logic hataları geliştirme aşamasında karşılaşmamızı sağlar.

```javascript
const value = Math.random() < 0.5 ? "a" : "b";
if (value !== "a") {
  // ...
} else if (value === "b") {
  // ...
}

/*This condition will always return
 'false' since the types '"a"' and '"b"' have no overlap.*/
```

### 

### Kaynakça

* [TypeScript Documentation - The Basics](https://www.typescriptlang.org/docs/handbook/2/basic-types.html)





