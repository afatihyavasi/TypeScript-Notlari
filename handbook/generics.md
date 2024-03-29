# Generics

Dinamik ve yeniden kullanılabilir kod yazmak söz konusu olduğunda **Kendini Tekrar Etme \(DRY\)** ilkesine uymak önemlidir. **Generic**, **TypeScript** de bunu yapmamızı sağlar.

 `<type1,type2...typeN>` içerisine yapacağımız tip tanımlamaları ile generic tip tanımlamaları yapabiliriz.

Örneklerle açıklamaya çalışalım.

```typescript
function displayUser<T, U>(name: T, id: U) {
    console.log(`${name} ${id}`)
}

displayUser<string, string>("John", "1");

```

Fonksiyonumuzun isminin hemen yanında `<T,U>` şeklinde bir generic görüyoruz. **T** name tipini, **U** ise id  tipini belirtmektedir. id tipini **number** yapmak istediğimizde tek yapmamız gereken fonksiyonumuzu çağırdığımız yerdeki generic tipini değiştirmektir.

```typescript
function displayUser<T, U>(name: T, id: U) {
    console.log(`${name} ${id}`)
}

displayUser<string, number>("John", 1);
```

 Başka bir örnekte [interface](interfaces.md) ve [type](type.md) ile generic kullanımını inceleyebilirsiniz.

```typescript
interface Fullname<T, U> {
    (name: T, surname: U):void
}

type Name = "ahmet" | "fatih";
type Surname = "yavasi";

const getFullName: Fullname<Name, Surname> = (name: Name, surname: Surname) => {
    console.log(`${name} + ${surname}`)
}

getFullName('ahmet','yavasi')
```

 

