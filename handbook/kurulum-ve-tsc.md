# Kurulum ve tsc

### Kurulum

TypeScript i global olarak sistemimize kurmak için terminalimizde aşağıdaki komutu çalıştırmamız yeterlidir.

```text
npm install -g typescript
```

### tsc \(TypeScript CLI\)

Oluşturduğunuz proje dizininde **main.ts** isimli dosya oluşturup TypeScript kodlarımız yazdıktan sonra terminalde 

```text
tsc main.ts
```

kodunuz çalıştırdığımız takdirde ilgili TypeScript dosyamız compile edilip **main.js** çıktısını vericektir. 

{% hint style="info" %}
Tarayıcılar, sadece JavaScript i derleyebilir. Html dosyamıza

```markup
<script src="main.ts"></script>
```

şeklinde TypeScript dosyamızı eklediğimiz takdirde hata alırız 
{% endhint %}

{% hint style="info" %}
Local projenizde kurulum yaptığınızda **npx tsc** komutuyla local projenizde **tsc** i kullabilirsiniz.
{% endhint %}

TypeScript dosyamızda her değişiklik yaptığımızda **tsc main.ts** yazmak yerine,

```text
tsc main.ts --w
```

 yazdığımızda TypeScript dosyamızda her değişik yaptığımızda otomatik olarak compile edilecektir.

