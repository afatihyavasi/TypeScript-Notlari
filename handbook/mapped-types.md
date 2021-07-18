# Mapped Types

{% hint style="info" %}
**Mapped Types** konusunu öğrenmeden önce [Generics](generics.md),  [keyof](keyof.md#keyof), [readonly](readonly.md) ve [optional params](optional-params-opsiyonel-parametreler.md) konuları hakkında bilgi sahibi olmak gerekir.
{% endhint %}

Diyelim ki elimizde aşağıdaki gibi bir tip objesi var

```typescript
interface Artist {
    id?: number;
    name?: string;
    bio?: string;
    birthDate?: string;
    country?: string;
}
```

ve bu biz objedeki tüm optional parametre ifadesi olan `?` lerini kaldırmak istiyoruz. Ne yaparsınız ? Tek tek mi değiştirirsiniz ? Yoksa bunu yapan bir yöntem var mıdır ? İşte TypeScript in **mapped types** özelliği burada devreye giriyor.

`[Propery in Type ] : type` syntax i ile tip nesnesi  içerisinde property lerini map edebiliyoruz. Okuyunca çok karışık oldu haklısınız. En iyi yine örnekler açıklayalım.

```typescript
type Properties = 'a' | 'b' | 'c';
```

Şeklinde bir [union tip](union-type-coklu-tipler.md) tanımlamamız olsun. Yeni bir tip tanımlamak istiyorum, **key** leri **Properties** objesinde ki keyler olsun, tip değerleri de **number** olmasını istiyorum. Bunu yapmak için **Mapped type** özelliğini kullanabilirim. 

Aşağıdaki örneği inceleyelim.

```typescript
type NewType = { [P in Properties]: number };
```

**NewType** tipinin karşılığı aşağıdaki gibidir.

```typescript
type NewType = {
  a: number;
  b: number;
  c: number;
 }
```

Gelelim işleri biraz daha karıştırmaya. Sayfanın en başında aşağıdaki [interface](interfaces.md) i oluşturmuştuk. **Mapped Type** özelliğini kullanarak [optional parametre](optional-params-opsiyonel-parametreler.md) özelliğini [interface](interfaces.md) içerisindeki tüm elemanlardan kaldırmak istiyorum. 

```typescript
interface Artist {
    id?: number;
    name?: string;
    bio?: string;
    birthDate?: string;
    country?: string;
}
```

Öncelikle **mapped type** özelliğini kullanabileceğim bir [generic](generics.md) type oluşturuyorum ve burada mapped type özelliğini kullanıyorum. Ardından oluşturduğum **generic** tip e , **generic** olarak **Artist** tip ini vererek yeni bir tip oluşturuyorum. Gelin adım adım nasıl çalıştığını anlatalım.

```typescript
type MyPartialType<T> = {
    [P in keyof T]-?: T[P];
};

type MappedArtistForEdit = MyPartialType<Artist>;
```

* Daha önceden [keyof](keyof.md#keyof) ile tip objesi içerisindeki key leri elde edebildiğimizi öğrenmiştik.**`[ P in keyof T]`** nin karşılığı aşağıdaki gibidir.

```typescript
[id ?, name ?, bio ?, birthDate ?, country ?]
```

* **`[P in keyof T]`**nin hemen yanında `-?` var. `-?` optional parametre özelliğini kaldırmamıza yarıyor. 
* **`T[P]`** ise type objemizde ki keylerin sırasıyla karşılığındaki tipleri bize veriyor. Örneğin aşağıdaki gibi bir **I** isimli **interface** miz olsun.

```typescript
interface I {
  a: string;
  b: number;
}
```

**`type PropertyA: I['a']`** nın karşılığı nedir ? Doğru cevap gözlerinizi aşağıya kaydırmanız yeterli 😀

```typescript
type PropertyA = string;
```

Tekrardan **`T[P]`** i açıklamaya dönelim. Bu durumda **`T[P]`** karşılığı, **T** objesinde ki her **key** in tip karşılığı olucaktır.

Yapılan işlem sonrası **`type MappedArtistForEdit`** in karşılığı aşağıdaki gibi olacaktır.

```typescript
type MappedArtistForEdit = {
    id: number;
    name: string;
    bio: string;
    birthDate: string;
    country: string;
}
```







