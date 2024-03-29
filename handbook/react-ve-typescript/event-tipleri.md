# Event Tipleri

Event tanımlaması yaparken, IDE miz den faydalanarak kolayca event tanımlaması yapabiliriz. Örneğin aşağıdaki gibi bir formumuz olsun.   **onSubmit** yazısının üzerine gelelim.

```typescript
<form onSubmit={handleSubmit}>
//...
</form>
```

![](../../.gitbook/assets/ekran-resmi-2021-07-21-18.38.57.png)

IDE miz \(Ekran görüntüleri WebStorm dan alınmıştır\) **onSubmit** için bize tip tanımlaması olarak `React.FormEventHandler<HTMLFormElement>` olarak onSubmit in tipini gösterir. Buradan hareketle event tipimizi aşağıdaki gibi tanımlayabiliriz.

```typescript
const handleSubmit = (e: React.FormEvent<HTMLFormElement>) {
    e.preventDefault();
}
```

 Event tip tanımlamaları hakkında detaylı bilgi almak için [şu](https://react-typescript-cheatsheet.netlify.app/docs/basic/getting-started/forms_and_events/) sayfayı inceleyebilirsiniz.

