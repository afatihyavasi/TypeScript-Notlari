# Modül Yapısı

**TypeScript** ES Module yapısını destekler. Örneğin tip tanımlamalarını yaptığımız **types.ts** adında bir dosyamız olsun. 

{% code title="types.ts" %}
```typescript
type User = {
    name: string;
    id: number;
}

export {User};
```
{% endcode %}

 Oluşturduğumuz **User** isimli tip objesini projemizin farklı yerlerinde kullanmak istiyoruz. Kullanmak için tek yapmamız gereken **User**'ı dosyamıza import etmek.

{% code title="index.js" %}
```typescript
import {User} from "./types";

let users:User;
users = {name:'Osman',id:142}
```
{% endcode %}

 

